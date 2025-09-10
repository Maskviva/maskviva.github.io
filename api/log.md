# 日志系统

在日志系统中，提供的方法有

> 写入Debug级别的日志
> [WriteAppLogDebug](#WriteAppLogDebug)(content: string) Promise<void>

> 写入Error级别的日志
> [WriteAppLogError](#WriteAppLogError)(content: string): Promise<void>

> 写入Info级别的日志
> [WriteAppLogInfo](#WriteAppLogInfo)(content: string): Promise<void>

> 写入Warn级别的日志
> [WriteAppLogWarn](#WriteAppLogWarn)(content: string): Promise<void>

> 写入MC日志
> [WriteMcLog](#WriteMcLog)(content: string): Promise<void>

## #WriteAppLogDebug

```typescript
WriteAppLogDebug().then(() => {
    console.log("写入Debug级别的日志成功")
})
```

## #WriteAppLogError
```typescript
WriteAppLogError().then(() => {
    console.log("写入Error级别的日志成功")
})
```

## #WriteAppLogInfo
```typescript
WriteAppLogInfo().then(() => {
    console.log("写入Info级别的日志成功")
})
```

## #WriteAppLogWarn
```typescript
WriteAppLogWarn().then(() => {
    console.log("写入Warn级别的日志成功")
})
```

## #WriteMcLog
```typescript
WriteMcLog().then(() => {
    console.log("写入MC日志成功")
})
```