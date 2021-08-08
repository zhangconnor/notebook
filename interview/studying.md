# java常见面试题：学习中

## java基础

### BIO、NIO、AIO 有什么区别？

BIO：Block IO 同步阻塞式 IO，就是我们平常使用的传统 IO，它的特点是模式简单使用方便，并发处理能力低。  
NIO：New IO 同步非阻塞 IO，是传统 IO 的升级，客户端和服务器端通过 Channel（通道）通讯，实现了多路复用。  
AIO：Asynchronous IO 是 NIO 的升级，也叫 NIO2，实现了异步非堵塞 IO ，异步 IO 的操作基于事件和回调机制。  

### Files的常用方法都有哪些？

Files.exists()：检测文件路径是否存在。  
Files.createFile()：创建文件。  
Files.createDirectory()：创建文件夹。  
Files.delete()：删除一个文件或目录。  
Files.copy()：复制文件。  
Files.move()：移动文件。  
Files.size()：查看文件个数。  
Files.read()：读取文件。  
Files.write()：写入文件。  


## 容器

