### DESAFIO ESIG -CARLOS SIGMUND
A proposta desse desafio era poder subir alguns serviços em nuvem para facilitar a comunicação interna, bem como melhorar a documentos dos processos internos. Para atender a essa necessidade foi solicitado duas ferramentas que atendem aos requisitos: O RocketChat e o WikiJS . Tudo para texte aprisionado em um kubernete local (aqui foi utilizado o minikube)

### Descrição do Projeto Prático
 - Primeira etapa: Instalação do kubernetes local (Minikube)
    - verifique se a sua máquina suporta virtualização. No GNU/Linux, isto pode ser realizado com:
								grep -E --color 'vmx|svm' /proc/cpuinfo

	Caso a saída do comando não seja vazia, o resultado é positivo.

	- instalar o `kubectl` com os seguintes comandos:
	
           curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s 		https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
	chmod +x ./kubectl
	sudo mv ./kubectl /usr/local/bin/kubectl
	kubectl version --client
	 - Instalando o virtualbox
  https://github.com/sigmund2015/Oracle-VMBox-no-Debian-10
   - Quando operando em conjunto com um _hypervisor_, o Minikube cria uma máquina virtual, onde dentro dela estarão todos os componentes do k8s para execução. Para realizar a inicialização desse ambiente, antes de executar o minikube, precisamos setar o VirtualBox como padrão para subir este ambiente, para que isso aconteça execute o comando:

```
             minikube config set driver virtualbox
```
             minikube start


🎉  minikube 1.10.0 is available! Download it: https://github.com/kubernetes/minikube/releases/tag/v1.10.0
💡  To disable this notice, run: 'minikube config set WantUpdateNotification false'

🙄  minikube v1.9.2 on Darwin 10.11

✨  Using the virtualbox driver based on existing profile

👍  Starting control plane node m01 in cluster minikube

🔄  Restarting existing virtualbox VM for "minikube" ...

🐳  Preparing Kubernetes v1.19.1 on Docker 19.03.8 ...

🌟  Enabling addons: default-storageclass, storage-provisioner

🏄  Done! kubectl is now configured to use "minikube"


- Segunda etapa: Criando os arquivos de Manifestos formato yaml
	- wikiJS
	![docker-compose-wikijs.yaml 	](https://drive.google.com/file/d/19zWeojD7u2W3mtkejyxhwr5ChaM_-QjK/view?usp=sharing)

	- RocketChat
	![docker-compose-rocketchat.yaml  ](https://drive.google.com/file/d/1RgnuIw64fP44mG4Qv9q3l8K6_WPNMb0I/view?usp=sharing)

#### Requisitos técnicos
- Debian 10
- Minikube
- Visual Studio Code
- VirtualBox
