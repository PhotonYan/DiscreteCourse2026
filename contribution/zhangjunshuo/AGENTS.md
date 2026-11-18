# Scope Lock：zhangjunshuo 工作区

本目录及其子目录（`contribution/zhangjunshuo/**`）是**唯一允许修改、暂存、提交**的范围。

## 硬性规则

1. 只允许新增、修改、删除 `contribution/zhangjunshuo/` 下的文件。
2. 禁止修改或暂存：
   - `contribution/` 下其他同学的目录；
   - 仓库根目录的 `README.md`、`AGENTS.md`、配置文件；
   - `main_notes/`、脚本、CI、`.git/` 配置（本目录专属规则文件除外）。
3. 禁止使用 `git add -A`、`git add .`、`git commit -a`；只能显式指定 `contribution/zhangjunshuo/...` 路径。
4. 提交前必须检查：
   ```bash
   git diff --cached --name-only | grep -v '^contribution/zhangjunshuo/'
   ```
   有任何输出就停止，不要提交。
5. 其他同学的目录即使看起来“乱了”、重名、格式不一致，也不属于本工作区，**不能删除、移动或整理**。
6. 如果用户要求修改本目录之外的路径，先说明这违反 scope lock，并等待用户明确授权；不要先改后说。

## 说明

- `contribution/DanJoshua`、`RuizeDu`、`XianranWang`、`XinpingBao`、`XiongZiyu`、`YuxiHuang`、`zhengzhuo` 等目录来自其他贡献者，不是本工作区创建的，也不由本工作区维护。
- 本工作区只负责 `contribution/zhangjunshuo/` 的课程笔记。
