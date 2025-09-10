# 进程管理

### API提供两种进程的接口

1. ConPty 进程
2. 普通进程

## ConPty进程

> 创建终端进程\
> [NewConPtyProcess](#NewConPtyProcess)(path: string): Promise<ConPtyProcess | null>

> 启动终端进程\
> [ConPtyProcessStart](#ConPtyProcessStart)(conPtyProcess: ConPtyProcess | null, outputEventName: string, args:
> string[]): Promise<void>

> 终止终端进程\
> [ConPtyProcessStop](#ConPtyProcessStop)(conPtyProcess: ConPtyProcess | null): Promise<void>

> 获取终端进程状态\
> [GetConPtyProcessStatus](#GetConPtyProcessStatus)(conPtyProcess: ConPtyProcess | null): Promise<ProcessState | null>

> 发送命令给终端进程\
> [SendCommandToConPtyProcess](#SendCommandToConPtyProcess)(conPtyProcess: ConPtyProcess | null, command: string):
> Promise<void>

### #NewConPtyProcess

```typescript
let process;

NewConPtyProcess(path).then(pes => {
    process = pes
})
```

### #ConPtyProcessStart

```typescript
let outputName = 'example';

ConPtyProcessStart(process, outputName, ['-c', 'ls']).then(() => {
    console.log('start')
})
```

### #ConPtyProcessStop

```typescript
ConPtyProcessStop(process).then(() => {
    console.log('stop')
})
```

### #GetConPtyProcessStatus

```typescript
GetConPtyProcessStatus(process).then(status => {
    console.log(status)
})
```

### #SendCommandToConPtyProcess

```typescript
SendCommandToConPtyProcess(process, 'ls').then(() => {
    console.log('send command')
})
```

## 普通进程

> 创建普通进程\
> [NewOrdinaryProcess](#NewOrdinaryProcess)(path: string): Promise<OrdinaryProcess | null>

> 启动普通进程\
> [OrdinaryProcessStart](#OrdinaryProcessStart)(ordinaryProcess: OrdinaryProcess | null, outputEventName: string, args:
> string[]): Promise<void>

> 终止普通进程\
> [OrdinaryProcessStop](#OrdinaryProcessStop)(ordinaryProcess: OrdinaryProcess | null): Promise<void>

> 获取普通进程状态\
> [GetOrdinaryProcessStatus](#GetOrdinaryProcessStatus)(ordinaryProcess: OrdinaryProcess | null): Promise<ProcessState |
> null>

> 发送命令给普通进程\
> [SendCommandToOrdinaryProcess](#SendCommandToOrdinaryProcess)(ordinaryProcess: OrdinaryProcess | null, command:
> string):
> Promise<void>

### #NewOrdinaryProcess

```typescript
let process;

NewOrdinaryProcess(path).then(pes => {
    process = pes
})
```

### #OrdinaryProcessStart

```typescript
let outputName = 'example';

OrdinaryProcessStart(process, outputName, ['-c', 'ls']).then(() => {
    console.log('start')
})
```

### #OrdinaryProcessStop

```typescript
OrdinaryProcessStop(process).then(() => {
    console.log('stop')
})
```

### #GetOrdinaryProcessStatus

```typescript
GetOrdinaryProcessStatus(process).then(status => {
    console.log(status)
})
```

### #SendCommandToOrdinaryProcess

```typescript
SendCommandToOrdinaryProcess(process, 'ls').then(() => {
    console.log('send command')
})
```

> 补充:\
> 获取进程的输出需要使用 @wailsio/runtime 包的 OnEvent API 并且需要特殊写法\
> 示例:\
> ```typescript
> import * as WailsRunTime from "@wailsio/runtime"; // 这里的导入必须是这种形式 导入的名称不能变
> 
> WailsRunTime.Events.OnEvent(outputName, (output: { data: string[] }) => {
>     console.log(output.data)
> })
> ```