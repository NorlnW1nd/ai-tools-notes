在安装OpenCode后，选择openai ChatGPT Plus/Pro(browser) 授权后 网页正确弹出如下页面  

![](.\image\authorization successful.png)

但opencode客户端中提示报错
![](.\image\41278efdf6ded6ce868061550eadab9d.png)



**核心原因：**

**浏览器访问的localhost:1455端口为默认成功页面，实际认证为opencode后台向**[**<font style="color:rgb(9, 105, 218);">https://opencode.ai/zen/v1</font>**](https://opencode.ai/zen/v1)**<font style="color:rgb(31, 35, 40);"> 换 token，这一步返回了 HTTP 403，所以 opencode 内部显示失败。</font>**

**<font style="color:rgb(31, 35, 40);">此处会报错 ： "Token exchange failed: 403" </font>**

> <font style="color:rgb(31, 35, 40);">浏览器看到的"成功"只是 callback 页面渲染成功，真正的 token 交换在 opencode后端返回了 403。</font>
>

**<font style="color:rgb(31, 35, 40);">解决方案：</font>**

**<font style="color:rgb(31, 35, 40);">VPN Client 使用 TUN模式/虚拟网卡模式。</font>**

