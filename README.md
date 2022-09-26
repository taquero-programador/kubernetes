## Kubernetes - K8s.

### Instalación de kubectl.
kubectl es una herramienta CLI que permite conectar con un clúster de Kubernetes.
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
Validar el binario.
```bash
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```
Comprobar el hash y deve devolver un `ok`.
```bash
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```
Instalar kubectl.
```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
Comprobar y validar la versión.
```bash
kubectl version --client=true
```
Usar `--client=true` o de lo contrarío intentara conectarse a un clúster externo.

### Instalar minikube.
minikube permite tener un clúster de Kubernetes localmente: por defecto solo soporta un clúster(equipo que ejecuta Kubernetes); un nodo/worker, grupo de uno o varios equipos fisicos o virtuales donde se ejecutan un clúster de Kubernetes.
### Requisitos minimos.
- 2 CPU's.
- 2 GB ram.
- 20 GB de espacio en disco.
- Conexión a internet.
- En Linux se ejecuta haciendo uso de un contenedor en Docker. Para Windows y Mac: se debe hacer uso de un hypervisor; en ese caso minikube creá automáticamente la maquina virtual donde ejecutara Kubernetes.
