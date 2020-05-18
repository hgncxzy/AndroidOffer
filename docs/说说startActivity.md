面试官：说说 startActivity 吧

🤔️：startActivity 主要就是应用进程与 system_server 进程的 AMS 通信，AMS 是实际来管理 Activity 组件的，负责处理启动模式，维护 Activity 栈等工作。startActivity 的大概流程就是由应用进程 IPC 调用到 AMS，AMS 处理完这些工作后再 IPC 回到应用进程，创建 Activity 的实例，回调 Activity 的生命周期。

面试官：通过什么实现跨进程的呢？

🤔️：都是通过 AIDL 接口，App 进程到 systemserver 进程是通过 IActivityServerManager.aidl ，systemserver 到 App 进程通过 IApplicationThread.aidl

面试官：startActivity 时前后 Activity 的生命周期是怎样的？

🤔️：旧 Activity 的 onPause 会先执行，然后新 Activity 依次执行 onCreate、onStart、onResume，随后再执行旧 Activity 的 onStop...

面试官：旧 Activity 的 onPause 一定会先执行吗，为什么？

🤔️：这主要是 AMS 来控制的，它会先后将前一个 Activity 的 onPause 事务和新 Activity 的启动事务发送给 App 进程，而在 App 端由 IApplicationThread.aidl 接受到后，会入队到 ActivityThread.H 的消息队列中，这个也是主线程消息队列，在队列上自然就实现了先后顺序的控制

面试官：了解插件化吗，知道怎么启动一个插件中的 Activity 吗？

🤔️：主要需要解决的问题是 Activity 未在 manifest 中注册的问题，因为在 AMS 中会检查 Activity 是否注册，而这个检查逻辑处于 systemserver 进程，我们是无法 hook 的，可以在 manifest 中提前注册一个占位 Activity，然后 startActivity 时进入到 systemserver 进程之前，hook 把未注册的 Activity 改为占位 Activity，AMS 检测就可以通过，然后再回到 App 进程后，把这个占位 Activity 再换成插件 Activity