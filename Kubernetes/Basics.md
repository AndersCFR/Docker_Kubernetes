# Kubernetes

## Arquitectura

Principalmente se distinguen dos componentes:

- Control Plane o Master

    Se puede tener más de un master, se inicializa a partir de un archivo yaml que define
    al maestro.

    - Api server
    - Controller
        - Node controller
        - Replication controller
        - Endpoints controller
        - Service account y token controllers
    - Scheduler
    - ETCD: Base de datos clave valor que almacena la información requerida
    - Cloud controller manager

- Nodo
    - Container runtime: Administra los POD
    - kubelet: corazón de cada nodo
    - kube-proxy: provee de la red para interconexión de los contenedores

### Instalaciones 

##### Instalaciones en local

- minikube: Es la más usada

- kind, un solo nodo dentro de Docker

- K3s: Creado por Rancher, enfocados a iot por ser ligero

- Microk8s

- Kubernetes: La herramienta de docker Desktop permite crear un k8 de un solo nodo

##### Instalaciones manuales

- Kudeadm es una herramienta que permiter crear un cluster e ir agregando nodos

##### Instalaciones automáticas

Permiten hacer instalaciones en un entorno cloud o en on-promise

- Kubespary: Es un playbook de tipo ansible y mantenido por la comunidad de kubernetes.

- Kops: Permite en local como en nubes

- RKE: Creado por Rancher permite una instalación completa

##### Instalaciones gestionada por un proveedor

- Manejo de cloud, es decir infraestructura como servicio

- Se puede dar tanto en AWS, Azure, GCP, etc

**Kubectl** es una herramienta cli que permite ejecutar comandos para los clusters

Es un cli para ejecutar comandos sobre despliegues clusterizados de k8s

**Kubectl** Descargar kubectl y minikube desde sus páginas oficiales

*versión de kubectl:* `kubectl version`

*versión de minikube:* `minikube version`

## Comandos de minikube

> Arrancar minikube con driver de docker
>> minikube start --driver=docker

> Verificar estado de minikube
>> minikube status

> Mirar los logs del cluster con minikube
>> minikube logs

> Ver ip para acceso a servicios
>> minikube ip

> Arrancar cluster
>> minikube start

> Detener cluster
>> minikube stop

> Borrar cluster
>> minikube delete

> Pausar cluster
>> minikube pause

> Ingresar a minikube
>> minikube ssh

> Listar los clusters
>> minikube profile list

> Crear un cluster
>> minikube start --driver=docker -p nombre-cluster --nodes=2

> Agregar configutaciones
>> minikube config set memory 4G -p nombreCluster

> Saber con que cluster estoy trabajando
>> minikube profile

> Cambiar de profile (cambiar a otro cluster)
>> minikube profile nombreClusterProfile

> Visualizar en entorno gráfico
>> minikube dashboard

> Borrar cluster
>> minikube delete -p nombreClusterProfile


## Comandos kubectl

> Obtener nodos activos
>> kubectl get nodes