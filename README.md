# Gitea PAT kubernetes credentials plugin

This is a [Kubernetes Credentials Provider](https://plugins.jenkins.io/kubernetes-credentials-provider/) adapter of [Gitea PAT Credential](https://docs.cloudbees.com/docs/cloudbees-jenkins-distribution/latest/distro-admin-guide/gitea-app-auth)

## A valid secret yaml file
```yaml
apiVersion: v1
kind: Secret
metadata:
  # this is the jenkins id.
  name: "giteapat-jenkins"
  labels:
    # so we know what type it is.
    "jenkins.io/credentials-type": "giteaPAT"
  annotations:
    # description - can not be a label as spaces are not allowed
    "jenkins.io/credentials-description": "credentials from Kubernetes"
type: Opaque
stringData:
  token: 0123456789012345678901234567890123456789
```
