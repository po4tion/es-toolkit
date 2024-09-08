# conforms

创建一个函数，调用给定对象的属性值与 `source` 的属性断言，如果所有断言都返回真值则返回 `true`，否则返回 `false`。

注意：创建的函数等同于部分应用 `source` 的 [`conformsTo`](./conformsTo.md)。

## 签名

```typescript
function conforms(source: Record<PropertyKey, (value: any) => boolean>): (object: Record<PropertyKey, any>) => boolean;
```

### 参数

- `source` (`Record<PropertyKey, (value: any) => boolean>`): 要符合的属性断言对象。

### 返回

`(object: Record<PropertyKey, any>) => boolean`: 新的规范函数。

## 示例

```typescript
const objects = [
  { a: 2, b: 1 },
  { a: 1, b: 2 },
];

objects.filter(
  conforms({
    b: n => n > 1,
  })
);
// => [{ 'a': 1, 'b': 2 }]
```