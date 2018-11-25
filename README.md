# cache
简单模拟一个浏览器缓存机制


max-age: 定义浏览器的缓存时间 在http 1.1中定义   优先级高于expirse http 1.0 
s-maxage: 定义为共享缓存（例如代理服务器cdn） 优先级高于max-age

private： 针对个人用户浏览器的私有缓存
public：针对共享缓存： cdn

no-cache：不设置浏览器缓存，可以与服务端协商定义缓存策略
no-store：完全不设置缓存


max-age存在的问题：是设置浏览器的缓存的时间，在缓存时间内如果服务端的文件更新了，浏览器是感知不到，依旧读取浏览器端的缓存

基于客户端和服务端协商的缓存机制
last-modified——response header
if-modified-since—— request header
需要与cache-control共同使用 

last-modified缺点：
1.某些服务端不能获取精确的修改时间
2.文件修改时间改变了，但是文件内容却没有变。

etag / if-none-match

文件内容的hash值
etag —— response header
if-none-match ——requset-header
需要与cache-control共同使用


