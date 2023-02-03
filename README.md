# Electron Lazy Package

## Build Setup  
before run
```cmd
npm install
```
run
```cmd
npm start
```

## Note
從無到有建構整個Project

### Environment Settings
1. install [Node.js](https://nodejs.org)
3. install Electron
    `npm init`  
    資料夾會build出一個package.json  
    `npm i -D electron`  
    在`package.json`內填入electron啟動方法
    ```diff
      "scripts": {
    +   "start": "electron .",
        "test": "echo \"Error: no test specified\" && exit 1"
      },
    ```
3. add necessary files for Electron
- `package.json`
- `main.js`
- `index.html`
- `preload.js`
4. install Electron Packager 打包專案成免安裝檔
    `npm i -D electron-packager`
    在`package.json`內填入打包指令
    ```diff
      "scripts": {
        "start": "electron .",
    +   "package": "electron-packager . Thermal-tool --platform=win32 --arch=x64 -–icon=icons/Mushroom.ico --out=build"
        "test": "echo \"Error: no test specified\" && exit 1"
      },
    ```
    打包
    `npm package`

### npm
NPM是一個Node.js的套件管理工具


`npm i module_name -S` = `npm install module_name --save`  
寫入到package.json的dependencies  
`npm i module_name -D` = `npm install module_name --save-dev`  
寫入到package.json的devDependencies  



A basic Electron application needs just these files:

- `package.json` - Points to the app's main file and lists its details and dependencies.
- `main.js` - Starts the app and creates a browser window to render HTML. This is the app's main process.
- `index.html` - A web page to render. This is the app's renderer process.
- `preload.js`



### electron-packager
electron-packager . PackageName: 將目前全部資料打包成PackageName這個名字  


–platform = darwin(Mac),win32(Windows),linux(LINUX)  
–arch = ia32,x64,all  
–version = Electron版本  
–icon = icon路徑  
–asar = true or false,設定trun是把程式文件封裝,比較不容易被看到原始碼  
–out = 輸出文件名稱(dist)  
–ignore = 忽略檔案不要打包,建議把electron都忽略掉,因為打包後裡面就有了,可以減少檔案大小  







## ref
[electron-quick-start](https://github.com/electron/electron-quick-start)
[[ Day 3 ] - 桌面小圖示(二) - Electron 架構說明](https://ithelp.ithome.com.tw/articles/10233853)
[史上最強套件管理  - NPM ， npm init 與 npm install (Day11)](https://ithelp.ithome.com.tw/articles/10191682)
[利用 electron.js 建立桌面 APP ( Windows ) - HackMD](https://hackmd.io/@c36ICNyhQE6-iTXKxoIocg/BJXGRjI4I)
