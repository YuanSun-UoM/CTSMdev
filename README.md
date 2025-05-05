# CTSMdev

This repository stores CTSM development code. 

## Development log

| Branch  | Tag                          | Summary                                     | Description                                           |
| ------- | ---------------------------- | ------------------------------------------- | ----------------------------------------------------- |
| 5.0.30  | release-clm5.0.30            | upload original release-clm5.0.30 code      | https://github.com/ESCOMP/CTSM/tree/release-clm5.0.30 |
| 5.0.30  | 5.0.30-transient_albedo      | transient albedo based on release-clm5.0.30 | Implementing transient urban albedo                   |
| 5.0.30  |                              |                                             |                                                       |
| 5.2.005 | ctsm5.2.005                  | upload original ctsm5.2.005 code            | https://github.com/ESCOMP/CTSM/tree/ctsm5.2.005       |
| 5.2.005 | 5.2.005-lcz                  | urban LCZ based on ctsm5.2.005              | Implementing urban LCZ                                |
| 5.2.005 | 5.2.005-dewpoint_temperature | Dew point temperature based on ctsm5.2.005  | Export dew point temperature                          |



## Git action

### Initial and ssh

```
ls -al ~/.ssh
ssh-keygen -t ed25519 -C "sunyuanzju@outlook.com"
cat ~/.ssh/id_ed25519.pub

# copy the key and paste them in the github settings to add a New SSH key

ssh -T git@github.com
# returns Hi YuanSun-UoM! You've successfully authenticated, but GitHub does not provide shell access.

git init
cd /Users/user/Desktop/YuanSun-UoM/CTSMdev/
# update the remote URL
git remote set-url origin git@github.com:YuanSun-UoM/CTSMdev.git
```

### branch management

- check existing branch

```
git branch
```

- create branch for model downloaded from CTSM official repo

```
git checkout -b 5.0.30 # CLM version for CESM2.1.3
git checkout -b 5.2.005

# automatically switched to the new branch '5.0.30'

# upload 'release-clm5.0.30' downloaded from CTSM official repo
```

- after making changes, push the branch to github

```
git push -u origin '5.0.30'
```

- delet a branch

```
# delet a branch
git switch main
git branch -d clm5.0.30-transient_urban
```

### tag management

- add tag for model modification based on specific branches

```
git tag
```



```
# switch to a specific branch 
git switch 5.0.30

# add tag
git tag release-clm5.0.30
git push origin release-clm5.0.30

git tag 5.0.30-transient_albedo
git push origin 5.0.30-transient_albedo

---------------------------------------
git switch 5.2.005

git tag ctsm5.2.005
git push origin ctsm5.2.005

git tag 5.2.005-lcz
git push origin 5.2.005-lcz

git tag 5.2.005-dewpoint_temperature
git push origin 5.2.005-dewpoint_temperature


# delete a tag locally
git tag -d 5.0.30-transient_albedo
```



