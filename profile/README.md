## open-wxa

**为微信小程序打造开放的开发与测试工具链。**

小程序的运行环境长期只存在于微信开发者工具和微信客户端里：调试离不开桌面应用，自动化测试难以接入 CI，
前端社区成熟的工具（Chrome DevTools、Playwright……）也用不上。open-wxa 希望改变这一点——
让小程序可以在开放的环境中运行、调试和测试，同时保持与官方行为一致。

### 项目

| 项目 | 说明 |
| --- | --- |
| [**wxa-runner**](https://github.com/open-wxa/wxa-runner) | 在浏览器中用微信官方基础库运行小程序，支持 Chrome DevTools 调试与 Playwright E2E 测试 |

### 我们的原则

- **与官方一致**：优先复用微信官方的运行时与编译器，而不是重新实现，避免「工具里能跑、真机上出错」
- **为测试而设计**：可以无头运行、可以在 CI 中使用、可以 mock 任意原生接口
- **尊重版权**：不分发微信的基础库、编译器等专有代码，只在运行时读取用户本机已安装的副本

### 参与

欢迎通过 Issue 反馈问题、提出想法，或直接提交 PR。参与前请阅读[贡献指南](https://github.com/open-wxa/.github/blob/main/CONTRIBUTING.md)和[行为准则](https://github.com/open-wxa/.github/blob/main/CODE_OF_CONDUCT.md)。

---

<sub>open-wxa is a community project building open tooling for WeChat Mini Programs. It is not affiliated with Tencent or WeChat.</sub>
