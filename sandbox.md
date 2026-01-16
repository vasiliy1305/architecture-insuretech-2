---

python3 -m venv ~/venvs/locust

source ~/venvs/locust/bin/activate

---

docker pull ghcr.io/yandex-practicum/scaletestapp:sha256-eff20ae3ae2d596375f9ed6d612a78d149a35a66cd2907ea90d7175ca918c993.sig
docker pull ghcr.io/yandex-practicum/scaletestapp:latest
docker run --rm -p 8080:8080 ghcr.io/yandex-practicum/scaletestapp:latest


GET / — получение идентификатора пода;
GET /metrics — получение метрик в формате Prometheus.
Метрика http_requests_total возвращает количество запросов для метода получения идентификатора пода.
Оба метода приложения доступны по порту 8080.


minikube start
minikube addons enable metrics-server

kubectl get pods -n kube-system | grep metrics
kubectl top nodes
kubectl top pods --all-namespaces



kubectl apply -f Task2/service.yaml
minikube service pod-id-app-svc --url



kubectl apply -f Task2/hpa-memory.yaml

kubectl get hpa -w
kubectl describe hpa pod-id-app-hpa-mem
kubectl get pods -l app=pod-id-app


---