```

$env:GIT_AUTHOR_DATE="2026-06-13 18:30:00 +0530"
$env:GIT_COMMITTER_DATE="2026-06-13 18:30:00 +0530"
git add .
git commit -m "commit-name"
git push
Remove-Item Env:GIT_AUTHOR_DATE
Remove-Item Env:GIT_COMMITTER_DATE
```
