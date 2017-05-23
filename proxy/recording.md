### 记录设置/recording setting

##### "options"中可以限制记录的文件大小；也可以限制记录的数量；

注意：限制记录意味着当限制被触发时，旧的记录将自动从会话中清除,请确保限制设置的足够高，否则会意外的丢失数据;

##### "include" 允许记录表：这里可以指定哪些会被记录

只有与你设置的HOST匹配的请求才会被记录，如果你没有设置，除非另有排除（exclude里设置），否则将记录所有请求;

这可以用来抓取某些特定的域名下的包文件；当然如果不想这么绝对，也可以设置focus，也可以达到同样集中注意力的效果;

##### "exclude" 排除记录表：这里指定哪些HOST会被排除，从而不记录

所有与你设置的HOST(一般是域名)相匹配的请求，都将不出现在记录面板;

如果你不小心把同一个HOST,同时设置为"允许记录表"和"排除记录表"中，该域名不会被记录；