本地开发环境搭建
```bash
1.
git clone https://github.com/hran315/loongside.git
cd loongside
2.启动基础设施
docker-compose up -d postgres neo4j
3.构建项目
cargo build --workspace
4.数据库迁移
cargo run --bin daemon -- migrate
5.启动
cargo run --bin daemon -- serve

---

开发与提交规范
新功能： feature/新增功能名称 

Bug 修复： fix/修复问题描述 

文档更新： docs/更新文档名称 
 
feat: 新增用户登录功能 

fix: 修复数据库连接失败问题 

docs: 添加开发者快速入门指南

---

如何提交PR
1.  创建分支（本地/网页均可）
      ```bash
      git checkout -b docs/developer-quickstart
      ```

2.  提交修改
    ```bash
    git add DEVELOPER_QUICKSTART.md
    git commit -m "docs: add DEVELOPER_QUICKSTART.md for new contributors"
    git push origin docs/developer-quickstart
    ```

3.  发起 PR 请求
    1.  回到你 Fork 的 `loongside` 仓库主页
    2.  顶部会出现提示条：Your recently pushed branches: docs/developer-quickstart，点击旁边的 Compare & pull request 按钮
    3.  确认目标仓库是 `xuanli520/loongside`，目标分支是 `main`

4.  填写 PR 信息（关键）
    标题：写清楚你的修改内容，例如：
       add DEVELOPER_QUICKSTART.md 
    描述：说明你做了什么，比如：
       本次提交新增了 DEVELOPER_QUICKSTART.md 文档，包含了项目简介、环境依赖、本地开发步骤、提交规范和 PR 指南，帮助新贡献者快速上手项目。

5.  提交并等待审核
    - 点击绿色的 「Create pull request」 按钮，PR 就提交成功了
    - 项目维护者会查看你的修改，可能会提一些修改意见，你按要求调整后即可合并


