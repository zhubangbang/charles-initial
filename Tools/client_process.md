### 客户端进程工具/client_process

显示使每个请求的本地客户端进程;

客户端进程工具显示负责进行每个请求的本地客户端进程的名称。

客户端进程通常是您的Web浏览器，例如firefox.exe，但客户端进程工具可以帮助您发现许多可能未知的HTTP客户端。

客户端进程名称显示在每个请求的“备注”区域中。

如果您可以在Charles中看到您不确定起始过程的请求，则客户端进程工具很有用。 它仅适用于在运行Charles的计算机上发出的请求。

该工具将在Charles接受每个连接之前引入一个短暂的延迟。 延迟通常不明显或显着。

**指定域名**

该工具可以针对每个请求启用，也可以仅对选定的位置启用。 当用于所选位置时，可以将工具的效果限制在指定的主机和使用简单而强大的模式匹配的路径上。