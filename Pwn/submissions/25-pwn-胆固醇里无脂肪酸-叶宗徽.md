1.test_your _nc

虚拟机终端中输入

```plain
nc node5.buuoj.cn 27013
cat flag
```

得到flag{c4c17bc5-3195-4b4e-b815-1b3827abac44}

2.door

首先把door文件复制进虚拟机，终端

```plain
checksec door
```

得到是64位。主机拖入IDA Pro64位，反编译得到c语言![](https://cdn.nlark.com/yuque/0/2025/png/61872331/1760847180160-b9c6157c-ae0a-4309-9ebd-e10afb3a6513.png)

回到虚拟机，终端输入

![](https://cdn.nlark.com/yuque/0/2025/png/61872331/1760849408859-c36efee6-d7da-4411-952e-04763bffbb61.png)

得到flag

3.INTbug

将INTbug复制于虚拟机，输入

```plain
checksec 	INTbug
```

得到64位，导入64位IDA Pro，得到![](https://cdn.nlark.com/yuque/0/2025/png/61872331/1760857550321-c5d1263d-837e-45a3-a134-31b927b9b18c.png)

双击func()，得到![](https://cdn.nlark.com/yuque/0/2025/png/61872331/1760857612121-ea96537c-6804-4ac6-96f9-70ad9f17ceab.png)

得知需要使用补码，是v1整数溢出满足if条件，于是返回虚拟机，输入![](https://cdn.nlark.com/yuque/0/2025/png/61872331/1760857706641-eef4d633-1ab2-4b5b-8ef8-bf60ae1f8e84.png)

