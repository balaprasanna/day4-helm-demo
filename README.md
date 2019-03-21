## Welcome to HEML workshop

#### Stage1: Create a helloworld helm chart

```
$ tree helloworld/
helloworld/
├── charts
├── Chart.yaml
├── templates
│   ├── deployment.yaml
│   ├── _helpers.tpl
│   ├── ingress.yaml
│   ├── NOTES.txt
│   ├── service.yaml
│   └── tests
│       └── test-connection.yaml
└── values.yaml

```

Locate the helloworld chart

```
 helm install helloworld/ --name helloworld --debug
[debug] Created tunnel using local port: '35635'

[debug] SERVER: "127.0.0.1:35635"

[debug] Original chart version: ""
[debug] CHART PATH: /home/std-user01/Projects/teaching/Containers/day04-helm/part1-helloworld/helloworld

NAME:   helloworld
REVISION: 1
RELEASED: Wed Mar 20 22:08:50 2019
CHART: helloworld-0.1.0
USER-SUPPLIED VALUES:
{}

COMPUTED VALUES:
app:
  name: demopythonapp
image:
  name: balanus/demopythonapp

HOOKS:
MANIFEST:

---
# Source: helloworld/templates/simplePod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: demopythonapp
  labels:
    name: demopythonapp
spec:
  containers:
  - name: demopythonapp
    image: balanus/demopythonapp
    resources:
      limits:
        memory: "128Mi"
        cpu: "100m"
    ports:
      - containerPort: 6000
LAST DEPLOYED: Wed Mar 20 22:08:50 2019
NAMESPACE: default
STATUS: DEPLOYED

RESOURCES:
==> v1/Pod
NAME           READY  STATUS    RESTARTS  AGE
demopythonapp  0/2    Init:0/1  0         1s


NOTES:
1. Get the application details run the following commands:

kubectl get pods demopythonapp

happy helming...

```

```
helm ls
```


#### Stage2: Take our pythonapp from day3 (istio) & write a helm chart for that

#### Stage3: Release the chart with different values (overwitter at release time with some default values_

#### Stage4: Do a simialr workshop for weather app (Refer to the handout for more details on this_
