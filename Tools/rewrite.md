### 重写工具/rewrite Srttings and rewrite rule

功能：在通过charles时修改请求和响应

**重写工具**

重写工具使 可以让你在 有请求响应的时候,修改请求和响应的规则。

规则：例如添加或更改标题或替换响应体中的一些文本。

**重写集**
重写集可以单独激活和停用。每个集合包含位​​置和规则的列表。这些位置选择规则将要运行的请求和响应。

**重写规则**
每个规则描述单个重写操作。规则可能会影响请求URL的标题，正文或部分内容;它可以根据请求和/或响应来操作;那么它可以定义搜索和替换或者只是替换样式重写。
重写规则编辑对话框中提供了有关重写规则的更多文档。

**位置匹配**
每个位置匹配可能包含协议，主机，端口和路径模式，以匹配特定的URL。位置可能包括通配符。当您将新位置添加到此工具时，可能会找到有关创建位置匹配的更多帮助。

**调试**
当您的重写操作无法正常工作时，重写工具可能难以调试。如果您有麻烦，请尝试添加一个非常基本的规则，例如添加明显标题的规则，以便您可以看到您的规则是否与请求匹配。还可以在错误日志中打开调试，以获取从Charles窗口菜单访问的错误日志中打印的一些调试信息。



### 规则重写 rewrite rule

每个规则描述单个重写操作。

##### Type 类型

该类型指定要执行的重写操作的类型。

重写规则类型有四种不同类别;标题规则，URL规则，查询参数规则，响应状态规则和正文规则。

头和查询参数规则分别影响头字段和查询字符串参数;添加，修改或删除标头和参数。 

URL和主体规则执行查找和替换URL和主体的不同部分。响应状态规则执行查找和替换响应状态代码和描述，

例如。 200 OK

Where

选择应用重写规则的位置;在请求，响应或两者上。

Match

匹配字段包含请求或响应中要匹配的文本，以决定是否触发此规则。您可以将名称或值留空或同时保留，以匹配任何值。如果您将名称和值字段都留空，您将匹配所有请求/响应。

可以启用正则表达式支持，为您的匹配提供Perl风格的正则表达式。如果您在正则表达式中包含组，则可以在匹配字段中使用它们。
除非正则表达式启用，否则名称字段是完全匹配字段，在这种情况下，它支持部分匹配。名称字段对于正则表达式和正常匹配都不区分大小写。如果要创建不需要的重写规则类型，则可能会禁用该名称字段。

值字段是部分匹配，除非您打开匹配整数值，在这种情况下，它是完全匹配的。值字段对于正则表达式和标头和查询参数规则的正常匹配都不区分大小写，并且对URL和正文规则区分大小写。

**新建/替换**

新/替换字段包含在触发此规则时在请求或响应中添加或替换的文本。将名称或值留空，以使它们与匹配的名称或值相同。

如果为匹配启用了正则表达式支持，则可以使用$1，$2等引用匹配组。

名称和值字段的行为取决于匹配。如果存在相应的匹配，则该字段将作为匹配文本的替代，否则如果匹配为空，则字段将替换整个名称或值。

值字段支持替换第一个或替换所有模式。如果名称匹配是正则表达式，则名称字段始终以替换优先模式运行，否则是完全匹配并替换整个名称。

如果要创建不需要的重写规则类型，则可以禁用名称或值字段。

**建议**

如果不按预期工作，重写规则可能难以调试。经常测试，最好慢慢建立一个规则。