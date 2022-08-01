# Development Workflow
- version: 0.0.1 

# TL;DR
1. 四种类型看板
    - **Assignable:** 可分配，主管分配或者自己选取
    - **Doing:** 正式开始做该 issues 时，将 issues 移动到这里
    - **Reviewable:** 做完的 issues 放这里
    - **Closable:** 测试人员完成功能测试之后移动到这里（暂时无用）
2. 基本流程
    1. 检查 Assignable 看板有无分配到自己的 issue
    3. 确定想做的 issue，移动到 Doing 看板
    4. 项目拉取一次代码，按照 issue 的类型（issue 标签 T 后面的内容，小写）新建分支，分支名格式 `<issue_type>/#issue_num`
    5. 开始编写代码实现功能
    6. 功能实现，提交分支到 GitLab 仓库，创建 MergeRequest
        > 提交分支：`git push origin <issue_type>/#issue_num`
    7. 主管 Code Review 代码，如有问题则继续提交来修复，无问题则由主管合并到 master 分支
    8. 合并完成意味着该 issue 生命周期已结束
3. 注意事项
    1. 根据 Code Review 发现的问题进行的修改，涉及到代码修改的必须新建 commit 来修改，不可以直接修改原 commit；仅仅只是 message 修改才允许直接修改
        
        目的：Code Review 者无需重复查阅已查阅过的 commit
    2. 根据 Code Review 发现的问题进行修改，新建 commit 的 message 的 head 和原 commit message head 相同，body 可改
        
        目的：方便后期 Code Review 合并这两个 commit

# References
