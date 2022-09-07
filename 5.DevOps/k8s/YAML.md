# YAML

### YAML이란?

-   데이터 직렬화에 쓰이는 포맷/양식 중 하나
-   다른 데이터 직렬화 포맷으로는 XML, JSON이 있음
-   파일 포맷 `.yaml`, `.yml`

### YAML의 특징

-   가독성
    -   YAML은 사람이 읽기 쉽도록 디자인되었다.

```YAML
apiVersion: v1
kind: Pod
metadata:
  name: example
spec:
  containers:
    - name: busybox
      image: busybox:1.25
```

```JSON
{
  "apiVersion": "v1",
  "kind": "Pod",
  "metadata": {
    "name": "example"
  },
  "spec": {
    "containers": [
      {
        "name": "busybox",
        "image": "busybox:1.25"
      }
    ]
  }
}
```
