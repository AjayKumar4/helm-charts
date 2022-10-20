# Kaniko Helm Chart

## Get Repo Info

```console
helm repo add kaniko https://AjayKumar4.github.io/helm-charts
helm repo update
```

_See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation._

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm install my-release kaniko/kaniko
```

## Uninstalling the Chart

To uninstall/delete the my-release deployment:

```console
helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

| Parameter                                 | Description                                   | Default                                                 |
|-------------------------------------------|-----------------------------------------------|---------------------------------------------------------|
| `dockersecertname`                                | DockerHub Registry Secert Name                              | `dockerhub-registry`                                                     |
| `context`                                | Git Repo Url git://github.com/<username>/<repo>.git                               | ``                                                     |
| `dockerfile`                                | Path to Dockerfile in Git Repo                               | `DockerFile`                                                     |
| `destination`                                | Full Docker image Name                               | ``                                                     |

### Example ingress with path

```console
helm install kaniko kaniko/kaniko \
--set dockersecertname="docker secert" \
--set context=git://github.com/<github username>/<repo>.git \
--set dockerfile=Dockerfile \
--set destination=<dockerhub username>/<repo>:1.0.0
```