# kubernetes-tips

Assuntos abordados por dia:

2º dia:

```markdown
- Init Container
- Parametrização de memória e CPU para os PODs/Containers
- Deployment Multi Container
- Service
- Ingress
- Secret
- Volume EmptyDir
```

```markdown
- Metric Server
- Nginx Ingress Controller
```

Materiais de Apoio:

- [Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
- [Init Container](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/)
- [Multi Container](https://kubernetes.io/docs/concepts/workloads/pods/#how-pods-manage-multiple-containers)
- [Service](https://kubernetes.io/docs/concepts/services-networking/service/)
- [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)
- [Secrets](https://kubernetes.io/docs/concepts/configuration/secret/)
- [Volume EmptyDir](https://kubernetes.io/docs/concepts/storage/volumes/#emptydir)

Addons Kubernetes:

- [Metric Server](https://github.com/kubernetes-sigs/metrics-server)
- [Nginx Ingress Controller](https://kubernetes.github.io/ingress-nginx/)

Neste Segundo dia, foi apresentado:
- O uso de configmaps como variáveis de ambiente, bem como as diversas formas de uso dentro do deployment.
- O uso de secrets.
- Como funciona o service e como é sua interação com os cloud Providers.
- Como funciona um ingress, bem como todas as peças que o compõem.
- Em uso prático, vimos como fazer roteamento de requisições a partir de politicas definidas no Ingress.
- Como funciona a comunicação e compartilhamento dentro de um pod com mais de 1 container.
- Subimos uma aplicação NodeJS para uso em Multi Container
