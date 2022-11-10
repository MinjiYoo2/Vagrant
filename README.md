# Vagrant

- ubuntu

oracle virtual box 설치 한 뒤에 vagrant 설치한다. (vmware 써도되는데 그러면 스크립트 알아서 바꾸기)

ubuntu에서 설치시 홈페이지들어가서 다운로드하는 짓 하지말기~ (별도 커널사이닝필요함)

sudo apt ~~로 설치 vbox, vagrant 둘다

- windows

홈페이지들어가서 다운로드

### 사용법

사용할 dir에서 

```bash
vagrant init
```

=> `.vagrant` 와 `Vagrantfile` 생기는데 이때 Vagrantfile 수정





 ```bash
vagrant up
 ```

=> Vagrantfile에 명시된대로 vm 기동, virtual box키면 기동된거 확인가능





```bash
vagrant halt
```

=> vm 멈춤





```
vagrant help
```

=> 명령어궁금하면





```bash
vagrant reload
```

=> 재기동





```bash
vagrant destroy
```

=> 받은 vm 삭제