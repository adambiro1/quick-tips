# oc_pwsh_setup
- create some folder and add it to you windows path:
- add oc.exe to that folder
- explorer -> path -> Click EnvironmentVariables -> select Path click edit -> click new -> click browse and add your folder


create psProfile:
```
New-Item -Path "C:\Users\$Env:UserName\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1" -ItemType File -Force
```

add there oc completion:
```
oc completion powershell >> $PROFILE
```

# vim setup for yaml
```
autocmd FileType yaml setlocal ai ts=2 sw=2 et
```

# adjust terminal for OCP
```
export PS1="[\u@\h] OCP User: \$(oc whoami 2>'/dev/null') OCP Project: \$(oc project --short 2>'/dev/null') \n\W $> "
```

# ps alias for cgroup
```
alias psc='ps xawf -eo pid,user,cgroup,args'
```
