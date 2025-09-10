# 配置文件

在配置文件中，提供的方法有

> 获取 Voxesis 配置文件的全部配置\
> [GetAllAppConfig](#GetAllAppConfig)(): Promise<AppConfig | null>

> 获取 Voxesis 配置文件指定配置\
> [GetAppConfigByKey](#GetAppConfigByKey)(key: string): Promise<string>

> 获取 MC 配置文件全部配置\
> [GetMcAllConfig](#GetMcAllConfig)(): Promise<McServerConfig | null>

> 获取 MC 配置文件指定配置\
> [GetMcConfigByKey](#GetMcConfigByKey)(key: string): Promise<string>

> 修改 Voxesis 配置文件\
> [UpDataAppConfig](#UpDataAppConfig)(key: string, value: any): Promise<void>

> 修改 MC 配置文件\
> [UpDataMcConfig](#UpDataMcConfig)(key: string, value: string): Promise<void>

## #GetAllAppConfig

```typescript
GetAllAppConfig().then(conf => {
    console.log(conf) // -> { "key": "value", "key2": "value2" ... }
})
```

## #GetAppConfigByKey

```typescript
GetAppConfigByKey("key").then(value => {
    console.log(value) // -> "value"
})
```

## #GetMcAllConfig

```typescript
GetMcAllConfig().then(conf => {
    console.log(conf) // -> { "key": "value", "key2": "value2" ... }
})
```

## #GetMcConfigByKey

```typescript
GetMcConfigByKey("key").then(value => {
    console.log(value) // -> "value"
})
```

## #UpDataAppConfig

```typescript
UpDataAppConfig("key", "value").then(() => {
    // 这里不会返回值 如果出错会在日志文件中出现
})
```

## #UpDataMcConfig

```typescript
UpDataMcConfig("key", "value").then(() => {
    // 这里不会返回值 如果出错会在日志文件中出现
})
```
