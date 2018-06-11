# GITPush.ps1
$comment = Read-Host -Prompt 'Comment your changes'
$user = "viral"
git add .;
git commit -m "$comment";
git push origin $user;
git checkout master;
git pull origin master;
git checkout -b staging_$user;
git merge $user;
git checkout master;
git merge staging_$user;
git push origin master;
git branch -d staging_$user
git checkout $user;
git branch -d $user_backup
git checkout -b $user_backup
git branch -d $user;
git checkout master;
git checkout -b $user;
