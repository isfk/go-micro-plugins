# go-micro v3 使用 nacos 作为注册中心

## 使用说明

```go
import "github.com/isfk/go-micro-plugins/registry/nacos"

registry := nacos.NewRegistry(func(options *registry.Options) {
    options.Addrs = []string{"127.0.0.1:8848"}
})
service := micro.NewService(
    micro.Name("go.micro.src.demo"),
    micro.Registry(registry),
)
service.Run()
```

## 感谢

- sanxun0325
  - https://github.com/sanxun0325/go-micro-nacos-demo
  - https://github.com/sanxun0325/go-plugins/tree/nacos/registry/nacos