# TravelOS

React + TypeScript + Vite，Dexie IndexedDB 本地存储。数据仅保存在当前浏览器，不会自动跨设备同步；清理网站数据或卸载浏览器可能删除数据，请定期导出 JSON 备份并在另一设备恢复。预置酒店是一笔总额；如需拆分，编辑原账单金额并新增其他部分，避免重复。

## 运行

```sh
npm install
npm run dev
npm test
npm run build
npm run preview
```

生产环境将 `dist` 部署至 HTTPS 静态托管。Vercel：导入项目，构建命令 `npm run build`，输出目录 `dist`。Cloudflare Pages：连接仓库，构建命令 `npm run build`，输出目录 `dist`。使用根路径部署。首次联网加载后，应用资源被缓存以供离线使用。iPhone Safari 打开 HTTPS 地址，点击分享，然后选择“添加到主屏幕”。各设备分别备份与恢复，不会通过 PWA 自动同步。

## 结构

`src/model.ts`：数据模型、固定精度金额和统计；`src/main.tsx`：界面与 IndexedDB；`src/style.css`：响应式主题；`public`：PWA 资源；`src/model.test.ts`：统计测试。

## 限制

没有云同步、实时汇率、独立的八达通余额账本或酒店自动拆分功能。默认汇率仅为手动初始值，不代表实时汇率。清单重置仅重置完成状态。日期未知的预付账单在总览展示并计入全程统计；每日图表只展示旅行六天，累计趋势包括预付。数据版本为 1，未来版本需要添加迁移。Safari 的离线缓存和本地存储可能被系统清理。
