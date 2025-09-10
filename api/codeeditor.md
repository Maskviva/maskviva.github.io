# 代码编辑器

> 添加文件到缓存列队
> AddCodeTemp(codeTempObj: CodeTemp): Promise<void>

```typescript
const codeTempObj = {
    "Name": "example",
    "Type": "typescript",
    "Path": "C:/example.ts",
}

AddCodeTemp(codeTempObj).then(() => {
    console.log('添加成功')
})
```

> 从缓存列队中删除指定的对象
> DeleteCodeTemp(name: string): Promise<void>

```typescript
DeleteCodeTemp('example').then(() => {
    console.log('删除成功')
})
```

> 获取缓存列队中指定的对象
> GetCodeTemp(name: string): Promise<{"Name": string, "Type": string, "Path": string, "Content": string} | null>

```typescript
GetCodeTemp('example').then(codeTemp => {
    console.log('name:', codeTemp.Name)
    console.log('type:', codeTemp.Type)
    console.log('path:', codeTemp.Path)
    console.log('content:', codeTemp.Content)
})
```

> 打开代码编辑器
> OpenCodeEditor(name: string): Promise<void>

```typescript
OpenCodeEditor('example').then(() => {
    console.log('打开成功')
})
```

> 更新缓存列队中指定的对象所指向的文件的内容
> UpdateCodeTemp(name: string, content: string): Promise<void>

```typescript
UpdateCodeTemp('example', 'console.log("hello world")').then(() => {
    console.log('更新成功')
})
```