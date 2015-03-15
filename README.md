# Memento

## Add sub project to your main project
In case of new project create directory for it:
```
mkdir memento
cd memento
git init
```
or clone it from existing repository:
```
git clone https://github.com/jarekkozak/memento.git
cd memento
```

Add location of your project:
```
git remote add memento-a https://github.com/jarekkozak/memento-a.git
```

Add *memento-a* as you subproject
```
git subtree add —-prefix=memento-a memento-a master
```

Please notice --prefix option is obligatory, shows subdirectowy in which sub-project will be saved.

Let's make a change in parent
```
touch memento-a/fileParent
```
In *memento-a* dir file *fileParent* has been created

and next commit it to the parent
```
git add .
git commit -m"File created in parent"
git push origing
```
notic that file has been created only in parent project and pushed to remote. Just created file did not appeared in *memento-a* project.

To push changes into *memento-a* use command
```
git subtree push --prefix=memento-a memento-a master
```

if you do changes in *memento-a* project (I assume that changes have been commited & pushed) you can update your parent project subtree
```
git subtree pull --prefix=memento-a memento-a master --squash
git commit -a
git push origin
```
