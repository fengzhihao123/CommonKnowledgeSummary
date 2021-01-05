### 异步加载图片

### 内存和磁盘缓存图片

### 图片绘制

### 如何实现支持的特性
* 异步下载缓存图片
    - 下载图片的函数调用栈：setImage -> retrieveImage -> loadAndCacheImage -> downloadImage -> resume
    - 使用 NSLock 来保证线程安全。
* 可加载网络和本地的图片
    - 加载网络图片使用👆的步骤。
    - loadAndCacheImage 函数中，case 为 provider ，则会调用 provideImage 设置本地的图片并缓存。
* 支持内存和磁盘缓存
    - 缓存图片的函数调用栈：cacheImage -> store -> storeNoThrow/syncStoreToDisk(队列异步执行)。
    - 内存缓存：MemoryStorage，底层数据结构使用的 NSCache。
    - 磁盘缓存：DiskStorage，使用 FileManager 方式管理。
    - 移除策略：
    - 为什么将 MemoryStorage、DiskStorage 声明为 enum ？