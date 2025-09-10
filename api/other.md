# 其他模块

> 获取指定ip 端口的DBS服务器状态
> GetMcServerState(host: string, port: number): Promise<ServerStatus | null>

```typescript
GetMcServerState('127.0.0.1', 19132).then(res => {
    console.log(res)
})
```

> 获取当前系统状态
> GetOsState(): Promise<OsState | null>

```typescript
GetOsState().then(res => {
    console.log(res)
})
```