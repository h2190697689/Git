### git hooks (简单理解为:生命周期)


#### 尝试: eslint校验
1. npm install -D eslint
2. npx eslint --init
3. 找到 pre-commit.sample文件， 编辑bash脚本
-  备注: git commit --no-verify  则不会执行pre-commit 钩子脚本


#### 前端配置
1. npm install husky -D
2. 修改package.json
```hooks配置
    "husky": {
        "hooks": {
            "pre-commit": "eslint ."
        }
    }
```
3. 额外: 单独文件配置
- .huskyrc 或 .huskyrc.json 或 .huskyrc.js 或 husky.config.js
```
    {
        "hooks": {
            "pre-commit": "git restore -W -S dist examples/dist"
        }
    }
```

#### vue-cli中配置
1. package.json
```
    {
        "gitHooks": {
            "pre-commit": "lint-staged"
        },
        "lint-staged": {
            "*.{js,vue}": [
                "vue-cli-service lint",
                "git add"
            ]
        }
    }
```
