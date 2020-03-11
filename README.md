### 安装 nodejs、vue3.0脚手架

1. **安装node.js**

   https://nodejs.org/en/download/

   查看版本号 `node -v`、`npm -v`出现版本号即安装成功。（如未出现，请重启电脑后再试）node8.9或以上版本。

2. **管理nodejs版本（非必装）**

   执行命令安装：`npm install -g n`

   `n latest`：升级node.js到最新版

   `n stable`：升级node.js到最新稳定版

   `n`后面也可以跟随版本号，例如：`n 11.12.0`

3. **全局安装vue-cli3.0脚手架**

   卸载：如果已经全局安装了旧版本的 vue-cli (1.x 或 2.x)，需要先卸载：`npm uninstall vue-cli -g`

   安装：`npm install -g @vue/cli`

   查看版本号：`vue -V`，出现版本号即安装成功

   3.0对2.0版本的桥接：`npm install -g @vue/cli-init`

4. **安装淘宝镜像cnpm（非必装，网络慢的情况可安装）**

   `npm install -g cnpm --registry=https://registry.npm.taobao.org`

### 建立项目仓库 (Github 或 Coding 或 Gitlab)

1. **Github**

   Github: <https://github.com/> (免费)

   Coding: <https://coding.net/> (免费)

   Gitlab: https://gitlab.com (免费30天)

2. **GIT基本命令**

   拷备项目：`git clone <仓库地址>`

   创建分支：`git branch <name>`

   创建并进入分支：`git checkout -b <name>`

   切换分支 `git checkout <name>`

   查看状态 `git status`

   添加所有文件 `git add .`

   提交：`git commit -m '提交描述'`

   拉取：`git pull`

   推送：`git push`

   查看分支：`git branch --list`

   查看分支 (包含远程分支)：`git branch -a`

3. **工作中的项目分支管理**

   `master`：主分支，一般都不会在此分支上开发项目

   `dev`：开发分支，一般在此分支上开发

   **版本分支：**建立于dev分支下面

   feature-vueAdmin-V1.0.0-2020311：分支完整名称

   	feature：描述当前分支类型（需求）

   	vueAdmin：项目名称

   	V1.0.0：版本号

   	2020311：建立分支日期

   **BUG分支:** 建立于当前版本分支下面

   	bug-101241-2020410：bug分支完整名称

   	bug：分支类型

   	101241：bug的ID

   	2020410：建立分支的日期	

   ### 构建项目

   1. **构建项目**

      `vue create vue-admin`

   2. 配置信息

      1. 本地存在相同名称目录

         - `Overwrite`：重写，删除本地目录，重新创建文件夹
         - `Merge`：合并
         - `Cancel`：取消

      2. 配置方式

         - `default`：默认配置
         - `Manually select features`：自定义配置

      3. 项目需要什么东西

         - `Babel`：编译 ES6 to ES5
         - `TypeScript`：js超集
         - `Progressive Web App (PWA) Support`：渐进式web应用
         - `Router`：VUE路由
         - `Vuex`：VUE状态管理(仓库)
         - `CSS Pre-processors`：CSS预编译器
         - `Linter / Formatter`：代码检测和格式化
         - `Unit Testing`：单元测试
         - `E2E Testing`：端对端测试，属于黑盒测试，通过编写测试用例，自动化模拟用户操作，确保组件间通信正常，程序流数据传递如预期

      4. 是否采用 history 模式

         **路由模式有两种：hash、history**

         hash - 即地址栏URL中的#符号；例如：http://www.abc.com/#/help

         history - 利用了 HTML5 History Interface 中新增的 pushState() 和 replaceState() 方法。（这个方法就是面试中常问到的，怎么去除URL中的"#"号，此方法需要后端 Apache 或 Nginx 进行简单的路由配置，否则会报404）

         注：这两个配置就是解决 URL 有没有 "#" 号的问题，如果不在意 "#" 号，就用 hash，在意就用 history

      5. CSS预编译器

         - Sass/SCSS (with dart-sass)：SASS dart-sass 编译模式
         - Sass/SCSS (with node-sass)：SASS node-sass 编译模式
         - Less：Less编译模式
         - Stylus：stylus编译模式

      6. 选择 ESLint 的代码规范

         - ESLint with error prevention only
         - ESLint + Airbnb config
         - ESLint + Standard config
         - ESLint + Prettier

      7. 选择何时进行代码检测

         - Lint on save：保存时进行检查
         - Lint and fix on commit：提交时进行检查

      8. 选择Babel、PostCSS、ESLint配置文件存放位置

         - In Dedicated config files：单独保存在各自的配置文件中
         - In package.json：保存在package.json文件中

      9. 是否保存选择的配置

         是：下次构建项目时，可选择此次配置

         否：不保存