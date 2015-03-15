# Memento

## Add sub project to your main project

Add repository with my subproject project:
```

git remote add my-sub-projectname git@github.com:username/my-subproject.git

```

Add sub project to my project
```

git subtree add —-prefix=vendor/ my-sub-projectname master

```

Please notice --prefix option, you can omit it then your sub project will be cloned in *my-sub-projectname* directory. In example above your project will be created in *./vendor/my-sub-projectname*.

Detach sub project
```
rm -rf my-sub-projectname
git add -A .
git commit -m "Detached subproject"
git push origin master
```
