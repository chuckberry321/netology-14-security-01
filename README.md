# Домашнее задание к занятию "14.1 Создание и использование секретов"

## Задача 1: Работа с секретами через утилиту kubectl в установленном minikube

### Ответ:
ДЛя задания использовал деплои из заданий 13. Использовал немспэйс prod.
* ссылка на [frontend.yaml](prod/frontend.yaml)
* ссылка на [backend.yaml](prod/backend.yaml)

```
vagrant@vagrant:~/kubespray$ kubectl get deployments -n prod
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
backend    1/1     1            1           6d
frontend   1/1     1            1           6d
vagrant@vagrant:~/kubespray$ kubectl get po -n prod
NAME                        READY   STATUS    RESTARTS      AGE
backend-64969cddb6-9cnw4    1/1     Running   1 (51m ago)   6d
db-0                        1/1     Running   1 (51m ago)   6d
frontend-654946877b-v69ns   1/1     Running   1 (51m ago)   6d
vagrant@vagrant:~/kubespray$ kubectl get secrets -n prod
NAME          TYPE                DATA   AGE
domain-cert   kubernetes.io/tls   2      17m
vagrant@vagrant:~/kubespray$ kubectl get secret domain-cert -n prod
NAME          TYPE                DATA   AGE
domain-cert   kubernetes.io/tls   2      17m
vagrant@vagrant:~/kubespray$ kubectl describe secret domain-cert -n prod
Name:         domain-cert
Namespace:    prod
Labels:       <none>
Annotations:  <none>

Type:  kubernetes.io/tls

Data
====
tls.crt:  1944 bytes
tls.key:  3247 bytes
vagrant@vagrant:~/kubespray$
```
