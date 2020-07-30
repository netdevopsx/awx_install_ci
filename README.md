# awx_install_ci
The repo contains pipelines which let us install AWX

fly --target netdevopsx login --team-name main \
    --concourse-url https://ci.netdevopsx.com

fly -t netdevopsx set-pipeline \
    --pipeline awx_deploy \
    --config pipelines/awx_deploy.yml

fly -t netdevopsx set-pipeline \
    --pipeline concourse_images \
    --config pipelines/concourse_images.yml

# Create kube_config
cd ~/.kube
kubectl -n concourse-main create secret generic kube-config --from-file=value=~/.kube/config