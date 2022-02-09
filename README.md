# git commit 提交模板和规范

Git每次提交代码，都要写 `Commit message`（提交说明），否则就不允许提交。但是，一般来说，commit message 应该清晰明了，说明本次提交的目的。当出现问题或者查看提交记录的时候也能`快速的定位`到该次提交, 不正当的提交,即不能体现出改动的`要点`,也不能体现改动的`模块`,除了给排查增加难度,让人一头雾水,😳再😳,没有任何优点可言。

    1.测试提交?
    2.中英混合?
    3.no no no 是什么?
![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16442911885101.jpg) ![16442911476031](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16442911476031.jpg)



再看下`前端框架Angular.js` 采用的`规范`提交记录
![](media/16442909885985/16443037205067.jpg)
会不会清晰很多😀, (好像英文看起来没中文的简洁😂, 当然这只是语言问题, 我们自己开发项目提交记录还是用中文)

# commit message 模板配置

规范带来的好处就不再多说,使用提交模板和钩子可以规范提交,这里不在信息说明,具体可参考[Git 钩子](https://www.git-scm.com/book/zh/v2/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-Git-%E9%92%A9%E5%AD%90) 直接上干货, 文章末尾会附上脚本, 可根据自身需求`更改模板`
### 1.下载脚本到本地

下载脚本, 或者创建一个文件复制文末脚本到文件, 修改文件名后缀以.sh结尾即可, 下载或者创建目录没有限制, 任意位置即可

### 2. 到需要配置git 提交规范的项目根目录

![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443042557546.jpg)


### 3. 执行脚本

- 直接把脚本拖入终端,回车执行即可, 因为是第一次执行脚本,可能没有`权限`,会报错

![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443042874846.jpg)

- 直接输入用户密码进行授权
```
sudo chmod u+x 脚本
```
![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443043400898.jpg)

- 授权完成, 执行脚本

![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443043904263.jpg)


这里会再次让输入密码确认

![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443044310871.jpg)

最后执行成功, 提交规范配置成功👏👏👏
- 看下配置成功后的sourcetree 提交模板
![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443046600463.jpg )

### 4.重启Sourcetree 提交改动
重启Sourcetree生效,如果本地已暂存的文件重启sourcetree也是不能带出已配置的模板,提交后下次生效

直接在相关类型的后面填写信息, 会自动转化成规范的提交格式
![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443094386501.jpg)

再看下不规范的提交
![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443065548457.jpg)
直接提交失败, 可根据弹窗中提示进行修改提交信息

## 使用终端提交
以上说明的都是基于`sourcetree`提交,如果使用终端则不能带出配置的`提交模板`,所以需要`注意`提交的信息格式, 错误的提交也会直接拦截, 按照文档修改后提交即可

> eg:   feat(租房详情页): 增加无尽流

错误的提交格式:
![错误的提交格式](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443069705737.jpg)

正确的提交格式:
![](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/16443078903151.jpg)


## 脚本参数说明
脚本执行支持`配置参数`
以下为参数说明
>
> <font color=#f00>install</font>  安装默认提交模板
<font color=#f00>uninstall</font>   卸载提交模板和规范钩子
<font color=#f00>uninstallTemp</font>   卸载默认提交模板,保留规范钩子 
<font color=#f00>installAll</font>      为目录中所有包含 git 的项目添加规范钩子和提交模板
<font color=#f00>uninstallAll</font>    为目录中所有包含 git 的项目卸载规范钩子和提交模板
<font color=#f00>help</font>    帮助
    
- 脚本执行不带参数默认直接安装(`install`)
- 使用熟练之后如果感觉模板冗余可以直接卸载(`uninstallTemp`),卸载之后任需要按照正确的格式提交 eg: `feat(租房详情页): 增加无尽流`
- 后续不想使用模板和钩子,直接卸载`uninstall`

点击下载配置脚本 [gitcommit.sh](https://kbmore-1257101624.cos.ap-beijing.myqcloud.com/2022/02/09/gitcommit.sh)

