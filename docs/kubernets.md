# Guia Básico de Comandos do Kubernetes

Este guia fornece uma visão geral dos comandos básicos para gerenciar recursos no Kubernetes, como pods e serviços.

## Pré-requisitos

- **kubectl** instalado e configurado para se conectar ao seu cluster Kubernetes.
- Um cluster Kubernetes em execução (por exemplo, Minikube).

## 1. Criando um Pod

Para criar um pod no Kubernetes, você pode usar um arquivo YAML de configuração. Aqui está um exemplo para criar um pod com NGINX:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
  - name: nginx
    image: nginx:latest
    ports:
    - containerPort: 80
```

Para aplicar esta configuração e criar o pod:

```bash
kubectl apply -f nginx-pod.yaml
```

## 2. Listando Pods

Para listar todos os pods no cluster, use:

```bash
kubectl get pods
```

Para listar todos os pods em todos os namespaces:

```bash
kubectl get pods -A
```

## 3. Expondo um Pod com um Serviço

Para expor um pod através de um serviço, crie um arquivo YAML de configuração para o serviço:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: NodePort
```

Para aplicar esta configuração e criar o serviço:

```bash
kubectl apply -f nginx-service.yaml
```

## 4. Listando Serviços

Para listar todos os serviços no cluster, use:

```bash
kubectl get services
```

Para listar todos os serviços em todos os namespaces:

```bash
kubectl get services -A
```

## 5. Verificando o Status do Cluster

Para verificar o status do cluster:

```bash
kubectl cluster-info
```

## 6. Verificando Logs de um Pod

Para verificar os logs de um pod específico:

```bash
kubectl logs <nome-do-pod>
```

Exemplo:

```bash
kubectl logs nginx-pod
```

## 7. Deletando um Pod

Para deletar um pod específico:

```bash
kubectl delete pod <nome-do-pod>
```

Exemplo:

```bash
kubectl delete pod nginx-pod
```

## 8. Deletando um Serviço

Para deletar um serviço específico:

```bash
kubectl delete service <nome-do-servico>
```

Exemplo:

```bash
kubectl delete service nginx-service
```

## 9. Listando Todos os Recursos

Para obter uma visão geral de todos os recursos no cluster:

```bash
kubectl get all -A
```

## Recursos Adicionais

- [Documentação Oficial do Kubernetes](https://kubernetes.io/docs/home/)
- [Minikube Documentation](https://minikube.sigs.k8s.io/docs/)

Este guia cobre os comandos básicos para começar a trabalhar com Kubernetes. Para aprofundar seus conhecimentos, explore a documentação oficial e pratique com diferentes configurações e recursos.
