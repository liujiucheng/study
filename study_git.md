## Git 基础操作速查
## 日常工作流程示例：

```bash
# 1. 克隆项目
git clone https://github.com/用户名/仓库名.git

# 2. 创建功能分支
git checkout -b feature-new
== git branch feature-new 
   git checkout feature-new   

# 3. 开发、修改文件
# ... 编写代码 ...

# 4. 提交更改
git add .
git commit -m "添加新功能"

# 5. 推送到远程
git push origin feature-new

# 6. 切换回主分支
git checkout main

# 7. 获取最新代码
git pull origin main

# 8. 合并功能分支
#切换到主分支上，合并这个分支
git merge feature-new

# 9. 推送合并后的代码
git push origin main
```
### 1. **初始化仓库**
```bash
# 在当前目录创建新的 Git 仓库
git init

# 克隆远程仓库到本地
git clone <仓库地址>
```

### 2. **查看状态**
```bash
# 查看当前状态（哪些文件修改了/待提交）
git status
```

### 3. **添加文件到暂存区**
```bash
# 添加单个文件
git add 文件名

# 添加所有修改的文件
git add .

# 添加所有修改和删除的文件（不包括新增的）
git add -u
```

### 4. **提交到本地仓库**
```bash
# 提交并添加提交信息
git commit -m "提交说明"

# 提交所有已跟踪的修改（跳过 git add 步骤）
git commit -am "提交说明"
```

### 5. **推送/拉取远程仓库**
```bash
# 推送到远程仓库（首次推送需要指定分支）
git push origin 分支名
# 或设置上游后简写
git push -u origin 分支名

# 拉取远程更新
git pull origin 分支名

# 团队项目拉去应该使用，
# 拉取但不合并（只获取更新）
git fetch origin
# 查看远程有什么更新
git log origin/main --oneline -5  # 查看远程main分支最新提交
git diff main origin/main         # 对比本地和远程差异
# 3. 决定合并
git merge origin/main
```

### 6. **分支操作**
```bash
# 查看分支
git branch          # 本地分支
git branch -a       # 所有分支（包括远程）

# 创建分支
git branch 分支名

# 切换分支
git checkout 分支名
# 或
git switch 分支名

# 创建并切换到新分支
git checkout -b 分支名
# 或
git switch -c 分支名

# 合并分支
git merge 分支名
# 删除之前的分支,一般不用删除
git branch -d 分支名
```

### 7. **查看日志**
```bash
# 查看提交历史
git log
git log --oneline   # 简洁版
git log --graph     # 图形化显示
```

### 8. **撤销操作**
```bash
# 撤销暂存区的文件（回到工作区）
git reset 文件名

# 撤销工作区的修改（危险！会丢失修改）
git checkout -- 文件名

# 撤销最近一次提交（保留修改到工作区）
git reset --soft HEAD~1

# 完全撤销最近一次提交（删除修改）
git reset --hard HEAD~1
```

### 9. **远程仓库配置**
```bash
# 查看远程仓库
git remote -v

# 添加远程仓库
git remote add origin <仓库地址>

# 修改远程仓库地址
git remote set-url origin <新地址>
```

## 常用快捷命令：
```bash
# 状态简写
git status -s

# 提交并推送
git commit -am "消息" && git push

# 拉取并合并（等同 git pull）
git fetch && git merge

# 查看最后几次提交
git log -3
```

记住核心三部曲：**`add` → `commit` → `push`**