# Montique MVP Deployment Checklist

## 已部署

- GitHub Pages: `https://zengheisenberg-bit.github.io/sanqingshi-product/`
- `gift_boxes`：10 条记录，含 2 条茶饼礼盒。
- `询单收集`：飞书表单已创建，关键字段已设置为必填。
- `index.html`：选品台从 `data.json` 加载数据。
- `advisor.html`：名片页从 `CONFIG` 读取顾问信息，并跳转飞书表单。
- `sop-card.html`：A4 横版 SOP 卡，可浏览器打印或导入 Canva 重排。
- `assets/boxes/`：本地礼盒图和 Logo 区域图按 `MTQ-001` 到 `MTQ-010` 命名。
- 交付压缩包：项目根目录下的 `montique-mvp-deploy.zip`。

## 飞书信息

- Base URL: `https://ccni7miiwrh3.feishu.cn/base/Jf6zbAO8paZf6TsUY77cHiIhnwc`
- 表单公开 URL: `https://ccni7miiwrh3.feishu.cn/share/base/form/shrcnFBuojqdY0XmFZ9VSgoeI5c?source=mingpian`

## 仍需手动完成

- 飞书表单公开链接已写入 `advisor.html`。
- 在飞书自动化中配置：`询单收集` 新增记录后，发送消息到 `Montique 运营群`。
- 用真实微信/飞书账号提交一次测试询单，确认运营群收到微信号、预算、数量、来源。

## 本地运行

```bash
python3 -m http.server 4173 -d montique-mvp
```

打开：

```text
http://127.0.0.1:4173/index.html
http://127.0.0.1:4173/advisor.html
http://127.0.0.1:4173/sop-card.html
```

线上访问：

```text
https://zengheisenberg-bit.github.io/sanqingshi-product/
https://zengheisenberg-bit.github.io/sanqingshi-product/advisor.html
https://zengheisenberg-bit.github.io/sanqingshi-product/sop-card.html
```
