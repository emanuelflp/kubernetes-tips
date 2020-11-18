# kubernetes-tips

Este repositório é um componente adicional ao treinamento de kubernetes.

Assuntos abordados por dia:

1º dia:

```markdown
- O que é docker
- O que é Kubernetes
- Proposta da plataforma Kubernetes
- POD
- ReplicaSet
- Deployment
- Deployment usando configMap como volume
```

Criar namespace:

```shell script
kubectl create namespace new_namespace
```

Template para Deployment nginx [nginx-deployment.yaml](./nginx-deployment.yaml):

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.15.0
        imagePullPolicy: Always
        ports:
        - containerPort: 80
        livenessProbe:
          httpGet:
            port: 80
            path: /
            scheme: HTTP
        readinessProbe:
          httpGet:
            port: 80
            path: /
            scheme: HTTP
        volumeMounts:
          - name: nginx-html
            mountPath: /usr/share/nginx/html
      volumes:
        - name: nginx-html
          configMap:
            name: nginx-configmap
```

Para criar um novo objeto ou conjunto de objetos:

```shell script
kubectl create -f NOME_ARQUIVO
kubectl create -f ./
```

Para atualizar um objeto ou conjunto de objetos já existente:

```shell script
kubectl apply -f NOME_ARQUIVO
kubectl apply -f ./ 
```

**OBS: Os comandos acima valem para qualquer tipo de objeto(deployment, service, configmap, etc...)**

Template para ConfigMap nginx [nginx-configmap.yaml](./nginx-configmap.yaml):

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: nginx-configmap
data:
  index.html: |
    <!DOCTYPE html>
    <html>
    <head>
    <title>Bem vindo ao curso de Kubernetes!</title>
    <style>
        body {
            width: 35em;
            margin: 0 auto;
            font-family: Tahoma, Verdana, Arial, sans-serif;
        }
    </style>
    </head>
    <body>
    <h1>Bem vindo ao curso de Kubernetes!</h1>
    <p>If you see this page, the nginx web server is successfully installed and
    working. Further configuration is required.</p>

    <p>For online documentation and support please refer to
    <a href="http://nginx.org/">nginx.org</a>.<br/>
    Commercial support is available at
    <a href="http://nginx.com/">nginx.com</a>.</p>

    <p><em>Thank you for using nginx.</em></p>
    </body>
    </html>
```