# Editor
리눅스에서 사용할 수 있는 에디터는 굉장히 많이 있습니다.
자신에게 맞는 에디터를 찾아보세요.

기본적으로 리눅스에는 vi, vim, gedit 가 설치되어있습니다.

### Gvim
```
# yum install gvim
```

### Emacs
```
# yum install emacs
```

### Visual Studio Code

```
# rpm --import https://packages.microsoft.com/keys/microsoft.asc
# sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
# yum check-update
# yum install code
```

- https://code.visualstudio.com/docs/setup/linux

### Sublime
```
# rpm -v --import https://download.sublimetext.com/sublimehq-rpm-pub.gpg
# yum-config-manager --add-repo https://download.sublimetext.com/rpm/stable/x86_64/sublime-text.repo
# yum install sublime-text
```

### Atom
- 홈페이지 : https://atom.io/
- 소스코드 : https://github.com/atom/atom

```
# wget https://github.com/atom/atom/releases/download/v1.32.2/atom.x86_64.rpm
# yum localinstall atom.x86_64.rpm -y
```