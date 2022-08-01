# AngularJS Git Commit Guidelines - Extension
- version: 0.1.0
- description: 
  - 对易混淆的 type 增加说明
  - 增加 scope 的用法
  - 给出结合 [禅道](https://www.zentao.net/) 的用法

## Base Format 基础格式
```
<type-类型>[(scope-作用域)]: <subject-概述>

[body-详情]

[footer-脚注]
```

## Type 类型
常用的 type 有  `feat, fix, docs, style, refactor`

- **feat**: 提交新功能
- **fix**: 修复了 bug
- **docs**: 只修改了文档
- **style**: 调整代码格式，未修改代码逻辑
- **refactor**: 代码重构，既没修复bug也没有添加新功能
- **perf**: 性能优化，提高性能的代码更改
- **test**: 添加或修改代码测试
- **chore**: 对构建流程或辅助工具和依赖库（如文档生成等）的更改

issues 设置了类型的直接用 issues 的类型，禅道任务 title 有说明类型的使用已经说明的，没有的自行判断

### 易混淆的 Type
- **docs**: 只修改了文档
  - 修改项目非代码文件的文档（包括 README.md，部署文档，操作手册，实施手册等）
  - **单纯的** 修改代码文件内的注释，例如，补充所有类、所有函数、所有静态常量的 [Javadoc](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/javadoc.html) 注释（即使用 `/**` 创建的注释），普通注释
- **style**: 调整代码格式，未修改代码逻辑
  - 增删空格、空行
  - 代码格式调整，例如：超长换行、点操作符换行时运算符新行、二元运算符换行时运算符保留在旧行等
      ``` java
      int result = 1 + // 二元操作符
          1;
      
      String firstName = Person
          .getFirstName(); // 点操作符
      ```
  - 删除不必要的分号
  - 移除无用的 import
  
  > 建议 IntellJ IDEA 提交时的 *Reformat Code*, *Optimize imports*, *Cleanup* 尽量只操作自己提交的代码，可以参考 [这里](https://blog.csdn.net/qq_19922839/article/details/119808578) 配置
- **refactor**: 代码重构，既没修复 bug 也没有添加新功能
  - 代码重构（换种方式实现等）
  - 重命名类名、变量名
  - 模块名重命名
  - 代码文件移动（非代码类文件的移动归属 docs）

  > 以上四种类型最好分开提交，例如一次调整涉及到 `类名、变量名重命名`，`文件移动` 两个操作的，我们分开两次提交
- **chore**: 对构建流程或辅助工具和依赖库（如文档生成等）的更改
  - **单纯的** Maven 依赖的增删改
  - CI/CD 有关配置文件的修改，例如 dockerfile 这些

## Scope 作用域
> 基于没有使用 [Liquibase](https://www.liquibase.org/), [Flyway](https://flywaydb.org/) 等数据库版本工具的前提下，主要考虑到通知协作开发人员及时更新本地配置，否则 git pull 之后启动项目大概率报错

涉及到 **数据库结构变更**，**配置文件变更** 的必须在 header 的 scope 分别使用 `$database`, `$config` 说明

涉及到 **数据库结构变更** 的还需要在此次 commit 上传数据库变更 SQL

例子-01：
```
feat($database): 添加 xxx 功能
```

## Footer 脚注
- Gitlab 议题
  如果 commit 关联 issues，在 `footer` 使用 `relate: #议题编号` 关联

    ```
    feat: 实现 xxx 功能

    relate: #2233 
    ```
- 禅道任务
  `footer` 使用 `relate: t任务编号` 关联（与 Gitlab 区别在于编号前的 # 换成 t，是 `task 任务` 的意思）

    ```
    feat: 新增实体属性次序字段

    relate: t3203
    ```
- 禅道 BUG
  `footer` 使用 `relate: b任务编号` 关联（与 Gitlab 区别在于编号前的 # 换成 b，是 `bug 缺陷` 的意思）

    ```
    fix: 解决 【记录管理】 接口无法使用问题

    relate: b1097
    ```
