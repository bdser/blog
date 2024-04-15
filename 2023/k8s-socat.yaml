
### socat 
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: tcp-socat
  namespace: tcp-proxy-test
spec:
  replicas: 1
  selector:
    matchLabels:
      app: tcp-socat
  template:
    metadata:
      labels:
        app: tcp-socat
    spec:
      containers:
        - name: tcp-socat
          image: alpine/socat:latest
          args: 
            - "TCP-LISTEN:443,fork"
            - "TCP:sase.geely.com:443"
          ports:
            - containerPort: 443
              name: https
              protocol: TCP

              
apiVersion: v1
kind: Service
metadata:
  name: tcp-socat
  namespace: tcp-proxy-test
spec:
  selector:
    app: tcp-socat
  ports:
    - protocol: TCP
      port: 443
      targetPort: 443
```
