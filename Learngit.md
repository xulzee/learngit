# 1.配置git的账号

```bash {.line-numbers}
git config --global user.email xulzee@163.com
git config --global user.name xulzee
```

# 2.把文件添加到版本库
```bash {.line-numbers}
#第一步，把文件添加到仓库
git add autopep8.md
#第二步，把文件提交到仓库
#简单解释一下git commit命令，-m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。
git commit -m "wrote files"
```

# 3.版本回退
git log命令显示从最近到最远的提交日志,如果嫌输出信息太多，看得眼花缭乱的，可以试试加上`--pretty=oneline`参数
```bash {.line-numbers}
git log
```
Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，也就是最新的提交3628164...882e1e0（注意我的提交ID和你的肯定不一样），上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。
```bash {.line-numbers}
git reset --hard HEAD^
git reset --hard 3628164
```
版本号没必要写全，前几位就可以了，Git会自动去找。当然也不能只写前一两位，因为Git可能会找到多个版本号，就无法确定是哪一个了。

Git提供了一个命令git reflog用来记录你的每一次命令：
```bash {.line-numbers}
git reflog
```

## 小结
- `HEAD`指向的版本就是当前版本，因此，Git允许我们在版本之间穿梭，使用命令 git reset --hard commit_id
- 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
- 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
