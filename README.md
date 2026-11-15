# 心动信号 · 每日心动

在线地址：**https://longjiang25.github.io/heart-signal/**

一个写给她的单页小站：极光星空、每天自动换新的心动签与情话、会爆爱心粒子的「想你了」按钮，还有藏在页脚的小彩蛋。

## 本地预览

双击 `index.html` 即可在浏览器打开。

## 在手机上打开（同一 WiFi）

在 `heart-signal` 文件夹里执行：

```powershell
python -m http.server 8000
```

手机浏览器访问 `http://电脑的局域网IP:8000`
（Windows 查 IP：命令行执行 `ipconfig`，找 IPv4 地址，如 192.168.1.5）

## 已部署到 GitHub Pages（免费）

- 线上地址：https://longjiang25.github.io/heart-signal/
- 仓库地址：https://github.com/longjiang25/heart-signal

以后修改页面后，在本文件夹打开 PowerShell 执行：

```powershell
powershell -ExecutionPolicy Bypass -File .\deploy.ps1
```

脚本会通过 GitHub API 上传最新文件（绕开 git push 网络问题），约 1 分钟后线上自动更新。

如果你的网络可以正常直连 github.com，也可以直接用常规的 git 流程：

```powershell
git add -A
git commit -m "更新内容"
git push
```

备用方案：也可以把整个 `heart-signal` 文件夹拖到 https://app.netlify.com/drop 免费部署。

## 个性化（可选）

打开 `index.html`，找到 `<script>` 开头附近的 `CONFIG`：

```js
const CONFIG = {
  herName: "",        // 她的昵称，例如 "小笨蛋"；留空则不显示
  anniversary: "",    // 在一起的日子，例如 "2024-05-20"；填了会显示"在一起的第 N 天"
};
```

每日签文和情话由日期自动决定：同一天打开内容固定，第二天零点自动换新，无需维护。

## 小彩蛋

页脚的 ✦ 星星，连续点 5 下试试。

## 页面包含

- 极光星云背景 + 星尘粒子 + 随机流星（Canvas）
- 每日时段问候（早安 / 午安 / 晚上好 / 夜深了）
- 今日心动签：3D 翻转，含签文、宜忌、幸运色、幸运数字
- 每日情话：打字机效果
- 「想你了」按钮：爱心粒子爆发，按下的次数会记住（当天有效）
- 隐藏彩蛋：流星雨 + 打字机情话
- 音效开关（合成音，无外部音频文件）
- 零外部依赖，断网也能打开
