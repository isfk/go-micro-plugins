# go-micro v3 使用 nacos 作为注册中心

## 使用说明

```go
import "github.com/isfk/go-micro-plugins/registry/nacos/v3"

registry := nacos.NewRegistry(func(options *registry.Options) {
    options.Addrs = []string{"127.0.0.1:8848"}
    // 支持 namespace
    options.Context = context.WithValue(context.Background(), &nacos.NacosContextKey{}, nacosNamespace)
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
