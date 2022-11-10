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



- 귀찮을때에는 그냥 minikube 쓰기(storage-provisioner있어서 내 클러스터에 ceph 안깔아도되고 Datastorage 때문에 간단하게 테스트하기 편함)

```bash
minikube start --vm-driver=virtualbox --nodes 3 -p multinode --memory=2048 --cpus=2 --disk-size=80GB --kubernetes-version=v1.19.1
```

=> 내가주로 쓰는 명령어, minikube도 노드여러개 쓸 수 있게 지원된다(master만 설치되는거라고 알고있는 사람이 많음), memory, cpu, disk-size, k8s version 적절히 설정해서 사용, pvc describe해봤더니 unbound다? memory늘려보기

=> cni 설정도 가능 

=> minikube도, kubectl도 설치하고 사용