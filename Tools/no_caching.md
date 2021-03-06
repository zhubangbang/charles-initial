### No caching Settings/无缓存工具的用法

弹窗面板上一句话概括了他的工作原理：通过修改请求和响应头来防止缓存;

**无缓存工具**

无缓存工具阻止客户端应用程序（如Web浏览器）缓存任何资源。因此，请求总是发送到远程站点，并且您始终看到最新版本。

![](http://i.imgur.com/QmJNuGK.png)

**适用范围**

该工具可以作用于每个请求（选中 Enable No Caching 即可），也可以仅对你配置的HOST启用（启用的nocaching同时，请选中 only for selected locations）;

当用于"only for selected locations"时，可以将no caching的效果限制在你所配置的主机上；

当然location配置也非常灵活；

**关于WEB缓存**

WWW是互联网上最受欢迎的应用之一，其快速增长造成网络拥塞和服务器超载，导致客户访问延迟增大，WWW服务质量日益显现出来。缓存技术被认为是减轻服务器负载、降低网络拥塞、增强WWW可扩展性的有效途径之一，其基本思想是利用客户访问的时间局部性（Temproral Locality）原理，将客户访问过的内容在Cache中存放一个副本，当该内容下次被访问时，不必连接到驻留网站，而是由Cache中保留的副本提供。

##### Web内容可以缓存在客户端、代理服务器以及服务器端。
研究表明，缓存技术可以显著地提高WWW性能，它可以带来以下好处：
- （1）减少网络流量，从而减轻拥塞。
- （2）降低客户访问延迟，其主要原因有：①缓存在代理服务器中的内容，客户可以直接从代理获取而不是从远程服务器获取，从而减小了传输延迟②没有被缓存的内容由于网络拥塞及服务器负载的减轻而可以较快地被客户获取。
- （3）由于客户的部分请求内容可以从代理处获取，从而减轻了远程服务器负载。
- （4）如果由于远程服务器故障或者网络故障造成远程服务器无法响应客户的请求，客户可以从代理中获取缓存的内容副本，使得WWW服务的鲁棒性得到了加强。
##### Web缓存系统也会带来以下问题：
- （1）客户通过代理获取的可能是过时的内容。
- （2）如果发生缓存失效，客户的访问延迟由于额外的代理处理开销而增加。因此在设计Web缓存系统时，应力求做到Cache命中率最大化和失效代价最小化。
- （3）代理可能成为瓶颈。因此应为一个代理设定一个服务客户数量上限及一个服务效率下限，使得一个代理系统的效率至少同客户直接和远程服务器相连的效率一样。

http://baike.baidu.com/item/%E7%BC%93%E5%AD%98

** No caching的运行原理**

无缓存工具通过操纵控制缓存响应的HTTP头来防止缓存;

从**请求中**删除If-Modified-Since和If-None-Match头，添加Pragma：no-cache和Cache-control：no-cache。

从**响应中**删除Expires，Last-Modified和ETag标头，添加Expires：0和Cache-Control: no-cache。
