## open-wxa

**为微信小程序打造开放的开发与测试工具链。**

小程序只能在微信开发者工具和微信客户端里运行：调试离不开桌面应用，E2E 测试难以接入 CI，Chrome DevTools、Playwright 这些前端工具也用不上。
open-wxa 让小程序在普通浏览器里运行，跑的仍是微信官方基础库。

**本地调试和测试**：

```bash
npx wxa-runner dev ./dist/dev/mp-weixin   # 原生小程序目录，或 uni-app / Taro 编译产物
# → http://localhost:3000
```

**部署成网站**：把小程序打包，导出成纯静态站点，交给 Nginx、GitHub Pages、对象存储等任意静态托管，
不用开发服务器就能长期在线，发个链接别人就能打开。[在线预览](https://wxa-viewer.picfinder.workers.dev)就是这样部署的。

```bash
wxa-runner viewer pack ./dist/build/mp-weixin -o my-app.wxapack
wxa-runner viewer export ./viewer-export --pack my-app.wxapack
# → 把 viewer-export/site/ 放到 Nginx 等静态托管上
```

查看器不发布到 npm，要用的话拉取 [wxa-runner](https://github.com/open-wxa/wxa-runner) 仓库构建后使用，见[查看器文档](https://open-wxa.github.io/wxa-runner/viewer)。

**[文档](https://open-wxa.github.io/wxa-runner/)** · [在线预览](https://wxa-viewer.picfinder.workers.dev)

它不替代开发者工具：预览、上传、真机调试仍然要用开发者工具。

### 项目

| 项目 | 说明 |
| --- | --- |
| [**wxa-runner**](https://github.com/open-wxa/wxa-runner) | 在浏览器中用微信官方基础库运行小程序，支持 Chrome DevTools 调试、Playwright E2E 测试，以及打包部署成静态网站 |
| [**wxa-extensions**](https://github.com/open-wxa/wxa-extensions) | wxa-runner 的扩展与构建插件：元素检查器（点选元素打开源码），uni-app 编译时自动启动 wxa-runner |
| [**wxa-baselib**](https://github.com/open-wxa/wxa-baselib) | wxa-runner 的内置基础库，让没有开发者工具的环境（Linux、CI）也能运行小程序 |

### 我们的原则

- **与官方一致**：优先复用微信官方的运行时与编译器，而不是重新实现，避免「工具里能跑、真机上出错」
- **为测试而设计**：可以无头运行、在 CI 中使用；预置登录态、mock 原生 API、拦截网络请求，都不用改业务代码
- **尊重版权**：基础库、编译器是微信官方代码，版权归腾讯所有，不适用我们项目的 MIT 协议。装了开发者工具时优先用本机的副本；内置的基础库原样保存，不做修改

### 参与

欢迎通过 Issue 反馈问题、提出想法，或直接提交 PR。参与前请阅读[贡献指南](https://github.com/open-wxa/.github/blob/main/CONTRIBUTING.md)和[行为准则](https://github.com/open-wxa/.github/blob/main/CODE_OF_CONDUCT.md)。

---

<sub>open-wxa is a community project building open tooling for WeChat Mini Programs. It is not affiliated with Tencent or WeChat.</sub>
