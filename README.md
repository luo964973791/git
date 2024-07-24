### git开发环境下忽略配置文件.

```javascript
git update-index --assume-unchanged src/db.php        #忽略db.php更新
git ls-files -v | grep '^h\ '                         #查看忽略的文件,小h代表忽略，大H代表不忽略
echo "node_modules/" >> .gitignore                    #忽略安装依赖的目录
git ls-files -v | grep '^h\ ' | awk '{print $2}'   #取出所有忽略的文件
git ls-files -v | grep '^h' | awk '{print $2}'| grep db.php |xargs git update-index --no-assume-unchanged  #删除忽略db.php
git add . && git commit -m "ignore db.php" && git push origin main  #提交

git config --global credential.helper store #git clone https: 记住密码
```
