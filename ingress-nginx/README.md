helm repo add nginx-stable https://helm.nginx.com/stable
helm repo update
helm install --create-namespace --namespace ingress-nginx ingress-nginx-release nginx-stable/nginx-ingress --set controller.extraArgs.default-ssl-certificate="cert-manager/wildcard"
helm pull --untar nginx-stable/nginx-ingress