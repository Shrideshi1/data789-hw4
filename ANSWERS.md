# HW4 - Short Answers

## 1. Rolling-update safety

Using `maxUnavailable: 0` ensures that Kubernetes does not intentionally reduce the number of available replicas below the desired count during a rolling update. If it were set to `1`, Kubernetes could temporarily allow one replica to be unavailable, potentially reducing the service's capacity to handle requests.

## 2. Health probes

The `/health` endpoint provides a lightweight way to check whether the application is running and ready to serve traffic. The `/predict` endpoint performs model inference and requires transaction data, so using it for frequent health checks would create unnecessary processing overhead.

## 3. Autoscaling under load

If request volume doubled and CPU utilization increased above the 40% target, the HPA would attempt to add replicas to distribute the workload. Once the deployment reached the maximum of eight replicas, it could not scale further, potentially causing higher response times or failed requests if traffic continued to increase.

Generative AI Disclosure

I used ChatGPT (OpenAI) as a learning and troubleshooting assistant for this assignment. It helped me understand Kubernetes configurations, deployment strategies, autoscaling, and Azure Container Apps. I also used it for troubleshooting deployment issues. 
I executed the deployment and testing commands in my own GitHub Codespace and Azure environment, reviewed the results, and captured my own screenshots. I am responsible for understanding and verifying the submitted work.