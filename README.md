# Awesome Guidelines 
本仓库将会包含一系列业界常用的 guidelines，另可能包含个人实践过程的拓展。

## Development Environment 开发环境
### Git Commit
- [AngularJS Git Commit Guidelines](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commits) & [非官方中文](https://zhuanlan.zhihu.com/p/86535275)
    
    [自拓展](./extension/git-commit.md)
- [Angular Commit Guidelines](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#-commit-message-format)
    
    受 *AngularJS Git Commit Guidelines* 启发
- [Conventional Commits](https://www.conventionalcommits.org) & [官方中文-约定式提交](https://www.conventionalcommits.org/zh-hans/)

    在 *AngularJS Git Commit Guidelines* 的基础上增加了更加细致的要求

其他资料：
- [理解语义化 Commit](https://ssshooter.com/2020-09-30-commit-message/)
- [Git Commit Messages: Best Practices & Guidelines](https://initialcommit.com/blog/git-commit-messages-best-practices)
### Versioning
- [Semantic Versioning](https://semver.org/) & [官方中文-语义化版本](https://semver.org/lang/zh-CN/)
    
    上层应用：
    - [standard-version](https://github.com/conventional-changelog/standard-version) 自动生成版本和 CHANGELOG
    - [semantic-release](https://github.com/semantic-release/semantic-release) 自动打包发布，貌似只支持 JS
