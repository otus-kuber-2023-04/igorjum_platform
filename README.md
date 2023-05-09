# igorjum_platform
igorjum Platform repository

- Установка Minikube
- Установка k9s
ReplicaSet обнаруживает его отсутствие и создаёт новый.
kube-proxy управляется контроллером DaemonSet обнаруживает его отсутствие и создаёт новый.
- Создаем Dockerfile
- Собираем образ, запускаем, проверяем работу и выкладываем в Docker Hub
- Создаем манифест web-pod.yaml
- Тест pod указав в манифесте несуществующий тег образа web.
- Добавляем в наш pod init container
- Проверяем через kubectl port-forward
- Клонируем и собираем образ для frontend
pod frontend находится в статусе Error тк 
{sproot@MBP-sproot ~/g/O/i/kubernetes-intro (kubernetes-intro)> kubectl logs frontend
{"message":"Tracing disabled.","severity":"info","timestamp":"2023-05-09T20:15:35.117233478Z"}
{"message":"Profiling disabled.","severity":"info","timestamp":"2023-05-09T20:15:35.11750427Z"}
panic: environment variable "PRODUCT_CATALOG_SERVICE_ADDR" not set

goroutine 1 [running]:
main.mustMapEnv(0xc000000000, {0xc0771a, 0x1c})
#    /src/main.go:208 +0xb9
main.main()
#    /src/main.go:124 +0x5be
    
    
- Добавляем блок `env`
