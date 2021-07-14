# eslint-action-test
* 安装eslint模块，用`eslint --init`指定语法检查的规则，生成配置文件
* 在/.github/workflows下创建eslint.yml
  * `on: push`表示push时触发
  * `runs-on: ubuntu-latest`指定运行环境
  * 分为若干`steps`
    * `actions/checkout@v2`：下载代码到actions的服务器
    * `yarn`：安装eslint及其依赖
    * `yarn run eslint . --ext .js,.jsx,.ts,.tsx`：检查所有`.js,.jsx,.ts,.tsx`后缀的文件
* 上传.github文件夹与package.json，此时github action就可以自动对push上来的js代码进行语法检查
