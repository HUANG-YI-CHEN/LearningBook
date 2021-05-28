# Node.js 簡易教學
Node.js 可在伺服器端運行 JavaScript 的開放原始碼

---
# Getting Started
+ [Node.js](https://nodejs.org/en/download/)(語言)
+ 學習目錄
  + [1. Node.js](#1)
    + [1.1 安裝](#1-1)
    + [1.2 環境設定](#1-2)
    + [1.3 NPM (軟體包管理系統)](#1-3)
      + [1.3.1 package.json 內容](#1-3-1)
      + [1.3.2 npm 參數控制](#1-3-2)
      + [1.3.3 npm 安裝套件全局與本地概念](#1-3-3)
      + [1.3.4 npm 鏈接進階指令](#1-3-4)
    + [1.4 資料參考](#1-4)

---
# <h1 id="1">Node.js</h1>
## <h2 id="1-1">1. 安裝(圖庫搬運以下參考)</h2>
+ 參考 [Node.js+Express 安裝設置與簡單實作](https://medium.com/@charming_rust_oyster_221/node-js-express-%E5%AE%89%E8%A3%9D%E8%A8%AD%E7%BD%AE%E8%88%87%E7%B0%A1%E5%96%AE%E5%AF%A6%E4%BD%9C-5920e1d70d9d)<br>
參考 [Node.js 安装配置](https://www.runoob.com/nodejs/nodejs-install-setup.html)<br>
![安裝-1](https://www.runoob.com/wp-content/uploads/2014/03/download-page.jpg)
![安裝-2](https://www.runoob.com/wp-content/uploads/2014/03/install-node-msi-version-on-windows-step4.png)
![安裝-3](https://www.runoob.com/wp-content/uploads/2014/03/install-node-msi-version-on-windows-step5.png)
![安裝-4](https://www.runoob.com/wp-content/uploads/2014/03/install-node-msi-version-on-windows-step7.png)
![安裝-5](https://www.runoob.com/wp-content/uploads/2014/03/install-node-msi-version-on-windows-step8.png)

+ 確認 Node.js 是否已安裝成功，開啟 `CMD` 輸入下列訊息。
```cmd
node --version
```

---
## <h2 id="1-2">2. 環境設定(圖庫搬運以下參考)</h2>
+ [電腦] → [內容] → [進階環境設定] → [進階] → [環境變數]
  + 編輯 [Path] 加入 <u><font color=#FF6600>Node.js目錄</font></u>("C:\Program Files\nodejs")
![環境設定-1](https://miro.medium.com/max/700/1*99NsvhOdPY9GSONfGmCebA.png)
![環境設定-2](https://miro.medium.com/max/1000/1*koLBo9rLFhxlgVc9FxNqig.png)

---
## <h2 id="1-3">3. NPM (軟體包管理系統)</h2>
+ 參考 [NPM 使用介绍](https://www.runoob.com/nodejs/nodejs-npm.html)<br>
參考 [什麼是npm系列：一、npm簡介](https://kknews.cc/zh-tw/code/vlelyka.html)<br>
參考 [從零開始: 使用NPM套件](https://medium.com/html-test/%E5%BE%9E%E9%9B%B6%E9%96%8B%E5%A7%8B-%E4%BD%BF%E7%94%A8npm%E5%A5%97%E4%BB%B6-317beefdf182)<br>
參考 [更改npm global與cache資料夾路徑](https://yuugou727.github.io/blog/2017/05/01/npm-global-cache-folder/)<br>
參考 [[筆記] 建立自己的 npm, 以npm Orgs跟Verdaccio為例](https://ceall8650.medium.com/%E7%AD%86%E8%A8%98-%E5%BB%BA%E7%AB%8B%E8%87%AA%E5%B7%B1%E7%9A%84-npm-%E4%BB%A5npm-orgs%E8%B7%9Fverdaccio%E7%82%BA%E4%BE%8B-cfb83b2307e6)<br>


+ `更新` `npm` 最新版本
```cmd
npm install npm@latest -g
```

+ npm 專案創建`初始化`: `建置`一個專案模組資訊包，會產生一個 `package.json` 去使用者紀錄操作
```cmd
npm init
```
---
### <h2 id="1-3-1">※ `package.json` 內容</h2>
![package.json](https://miro.medium.com/max/3876/1*ZSx0OHapDPaevn5Edo1OrQ.png)
| 名稱 | 說明 |
| -------- | -------- |
| name | 專案的名稱 |
| version | 專案的版本 |
| description | 專案的描述 |
| homepage | 專案主頁 |
| author | 專案的作者 |
| contributors | 貢獻者到包的名字 |
| dependencies | 依賴關係的列表。NPM自動安裝所有在這裡的包node_module文件夾中提到的依賴關係 |
| repository | 專案的庫類型和URL |
| main | 專案的入口點 |
| keywords | 關鍵字 |
<br>

---
### <h2 id="1-3-2">※ ***npm 參數控制***</h2>
+ 會依使用者操作參數，而產生`package.json`的變化:
  + 註：--save 表示安裝包記錄在dependencies，package.json裡的dependencies會改變。
  + 再運行 npm install 會把所有依賴安裝下來。
  + 不加--save，什麼都不會安裝。
```cmd
npm install
```

| 參數 | 說明 |
| -------- | -------- |
| -P, --save, --save-prod | 記錄在dependencies |
| -D, --save-dev | 記錄在devDependencies |
| -O, --save-optional | 記錄在optionalDependencies |
| --no-save | 不會記錄在dependencies |
| -E, --save-exact | 版本號不會按照語義化記錄，會顯示具體的」1.2.3」 |
| -B, --save-bundle | 依賴也會記錄在bundleDependencies中 |

---
### <h2 id="1-3-3">※ ***npm 安裝套件 `全局`(gobal) 與 `本地`(local) 概念:***</h2>
+ `全局` gobal path : 通常指系統安裝預設目錄
  + Windows 7, 8, 10: `%USERPROFILE%\AppData\Roaming\npm\node_modules`
  + Windows XP - `%USERPROFILE%\AppData\npm\node_modules`
+ `本地` local path : 通常指使用者當下的專案目錄
  + `<project name>\node_modules`
  + example:  "`C:\Project\Test\modules`"
---

+ `安裝` 套件分兩種，`全局`與`本地`，開啟 `CMD` 輸入下列訊息。
```cmd
npm install express       # 本地安装
npm install express -g    # 全局安装
```

+ `移除` 套件分兩種，`全局`與`本地`，開啟 `CMD` 輸入下列訊息。
```cmd
npm uninstall express       # 本地安装
npm uninstall express -g    # 全局安装
```

+ `更新` 套件分兩種，`全局`與`本地`，開啟 `CMD` 輸入下列訊息。
```cmd
npm update express       # 本地安装
npm update express -g    # 全局安装
```

+ `列出` 套件分兩種，`全局`與`本地`，開啟 `CMD` 輸入下列訊息。
```cmd
npm list        # 本地安装
npm list -g     # 全局安装
```

+ `清空` npm 本地 cache，開啟 `CMD` 輸入下列訊息。
```cmd
npm cache clear
```

+ `發佈` npm 套件到 npm 官網，開啟 `CMD` 輸入下列訊息。
```cmd
npm publish
```

+ 從 npm 官網 `移除發佈` npm 套件，開啟 `CMD` 輸入下列訊息。
```cmd
npm unpublish
```

---
### <h2 id="1-3-4">***NPM LINK***</h2>
※ 若是有 `多個專案`，且同時參照到`相同套件包`，此情形可使用`全域安裝`，並配合指令`連結`串接
+ 資料參考 [npm 最佳實作的小技巧](https://andyyou.github.io/2016/10/04/node-best-practice/)
+ `建立連結`鏈接套件包，開啟 `CMD` 輸入下列訊息。
```cmd
npm install express -g
npm link express
```

+ `移除連結`鏈接套件包，開啟 `CMD` 輸入下列訊息。
```cmd
npm unlink express
```

---
## <h2 id="1-4">4. 資料參考</h2>
+ Node js 安裝
  + [Node.js+Express 安裝設置與簡單實作](https://medium.com/@charming_rust_oyster_221/node-js-express-%E5%AE%89%E8%A3%9D%E8%A8%AD%E7%BD%AE%E8%88%87%E7%B0%A1%E5%96%AE%E5%AF%A6%E4%BD%9C-5920e1d70d9d)
  + [Node.js 安装配置](https://www.runoob.com/nodejs/nodejs-install-setup.html)
+ NPM
  + [NPM 使用介绍](https://www.runoob.com/nodejs/nodejs-npm.html)
  + [什麼是npm系列：一、npm簡介](https://kknews.cc/zh-tw/code/vlelyka.html)
  + [從零開始: 使用NPM套件](https://medium.com/html-test/%E5%BE%9E%E9%9B%B6%E9%96%8B%E5%A7%8B-%E4%BD%BF%E7%94%A8npm%E5%A5%97%E4%BB%B6-317beefdf182)
  + [更改npm global與cache資料夾路徑](https://yuugou727.github.io/blog/2017/05/01/npm-global-cache-folder/)
  + [[筆記] 建立自己的 npm, 以npm Orgs跟Verdaccio為例](https://ceall8650.medium.com/%E7%AD%86%E8%A8%98-%E5%BB%BA%E7%AB%8B%E8%87%AA%E5%B7%B1%E7%9A%84-npm-%E4%BB%A5npm-orgs%E8%B7%9Fverdaccio%E7%82%BA%E4%BE%8B-cfb83b2307e6)
  + [npm 最佳實作的小技巧](https://andyyou.github.io/2016/10/04/node-best-practice/)
