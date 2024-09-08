# conformsTo

检查 `object` 是否符合 `source`，通过调用 `source` 的属性断言与 `object` 的相应属性值。

注意：当 `source` 部分应用时，此方法等同于 [`conforms`](./conforms.md)。

## 签名

```typescript
function conformsTo(object: Record<PropertyKey, any>, source: Record<PropertyKey, (value: any) => boolean>): boolean;
```

### 参数

- `object` (`Record<PropertyKey, any>`): 要检查的对象。
- `source` (`Record<PropertyKey, (value: any) => boolean>`): 要符合的属性断言对象。

### 返回值

`boolean`: 如果 `object` 符合，则返回 `true`，否则返回 `false`。

## 示例

```typescript
const object = { a: 1, b: 2 };

conformsTo(object, {
  b: n => n > 1,
});
// => true

conformsTo(object, {
  b: n => n > 2,
});
// => false
```