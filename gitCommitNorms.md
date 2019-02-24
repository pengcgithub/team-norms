# git commit 规范

## 辅助插件

[git-commit-template](http://plugins.jetbrains.com/plugin/9861-git-commit-template)

备注：如果使用的是IDEA编辑器，可直接下载辅助插件。


## 提交模板

**提交公式：**

```
<type>(<scope>): <subject>
<closed>
```

![](https://i.imgur.com/AQhQ6ci.png)

**type：**

用于说明 commit 的类别，只允许使用下面7个标识。

1. feat：新功能（feature）

2. fix：修补bug

3. docs：文档（documentation）

4. style： 不影响代码运行的变动（css，空格，格式，缺少分号等）

5. refactor：重构（即不是新增功能，也不是修改bug的代码变动）

6. test：增加测试

7. chore：构建过程或辅助工具的变动，对构建过程或辅助工具和库（如文档生成）的更改 

8. build： 源码构建配置文件的变动

9. test： 添加缺失或更正现有测试 ，单元（集成）测试的源码提交

10. revert:   代码还原的变动

11. ci:   持续集成工具的变动

12. perf:   代码更改可提高性能，软件性能分析工具的变动

    [^可单个或多个标识组合使用：]: 例：fix+style(*): 修改了去除定位偏移的bug+背景样式修改

**scope：**

用于说明 commit 影响的范围，比如数据层、控制层、视图层等等，视项目不同而不同，逗号分隔。

1. 说明哪个模块受到影响，子模块斜杠分割，多个模块逗号分隔。

   例：feat(品牌大全/列表页，新机大全/详情页)：添加xxx

   例：feat(.eslintrc.js,某个单文件文件名)：更新xx配置

2. 当更改影响多个范围时，您可以使用*。 
   *例：feat(*\*):  更新远端dev仓库代码

**subject：**

是 commit 目的的简短描述，不超过50个字符。

> 开头请使用： 添加xxx  移出(清空)xxx  升级(更新)xxx  覆盖xxx 改变xxx 切换xxx为xxx  修复xxx 

1. 以动词开头，使用第一人称现在时，比如change，而不是changed或changes
2. 第一个字母小写
3. 结尾不加句号（.）

**closed：**

标记项目管理工具中的bug版本.