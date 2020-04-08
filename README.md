# nikolaykhomenko_infra
nikolaykhomenko Infra repository

Подключение к машине:
ssh -J nhomenko@34.77.235.197 nhomenko@10.132.0.5

Конфигурация Test App:
``` 
    testapp_IP = 34.76.182.245
    testapp_port = 9292
 ```
  
  
  

Создание VM

gcloud compute instances create reddit-app \
--boot-disk-size=10GB \
--image-family ubuntu-1604-lts \
--image-project=ubuntu-os-cloud \
--machine-type=g1-small \
--tags puma-server \
--restart-on-failure

Правило фаервола:

gcloud compute firewall-rules create default-puma-server \
      --allow tcp:9292 \
      --source-ranges="0.0.0.0/0" \
      --target-tags=puma-server
