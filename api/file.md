# 文件类

> 验证目录的文件
> AuthDirectory(path: string, filesList: string[][]): Promise<boolean>

```typescript
AuthDirectory("C:/example/", ["file1.txt", "file2.txt"]).then(ok => {
    console.log(ok);
})
```

> 打开目录选择框
> OpenDirectoryDialog(title: string): Promise<string>

```typescript
OpenDirectoryDialog("选择目录").then(path => {
    console.log(path);
})
```

> 打开文件选择框
> OpenFileDialog(title: string, displayName: string, pattern: string): Promise<string>

```typescript
OpenFileDialog("选择文件", "*.txt", "*.txt").then(path => {
    console.log(path);
})
```