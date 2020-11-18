# kubernetes-tips

Este repositório é um componente adicional ao treinamento de kubernetes.

Assuntos abordados por dia:

[Dia 1](./Dia%201):

```markdown
- O que é docker
- O que é Kubernetes
- Proposta da plataforma Kubernetes
- POD
- ReplicaSet
- Deployment
- Deployment usando configMap como volume
```

[Dia 2](./Dia%202):

```markdown
- Deployment Multi Container
- Init Container
- Parametrização de memória e CPU para os PODs/Containers
- Metric Server
- Service
- Ingress
- Secret
- Volume EmptyDir
```

Listar Contextos:

```shell script
kubectl config get-contexts
```

Selecionar o contexto como principal

```shell script
kubectl config use-context NOME_CONTEXTO
```


Comandos Basicos:

Criar Namespace:
```shell script
kubectl create namespace NAMESPACE
```

Criar ou atualizar qualquer Objeto a partir de um arquivo:
```shell script
kubectl create -f NOMEARQUIVO
kubectl apply -f NOMEARQUIVO
```

Deletar todos os objetos listados em arquivo
```shell script
kubectl delete -f NOMEARQUIVO
```