# API 参考

以下接口仅用于文档展示，不提供真实服务。

## 接口一览

| 方法 | 路径 | 功能 | 是否需鉴权 |
| --- | --- | --- | --- |
| GET | `/api/docs` | 返回文档条目列表 | 否 |
| GET | `/api/docs/{id}` | 按 ID 查询单篇文档 | 否 |

## 查询文档列表

- 请求方法：`GET`
- 请求路径：`/api/docs`
- 功能：返回文档条目列表。

### 请求示例

```bash
curl -s "https://example.com/api/docs?limit=10"
```

### 返回示例

```json
{
  "items": [
    {"id": 1, "title": "使用指南"},
    {"id": 2, "title": "API 参考"}
  ],
  "total": 2
}
```

### 字段说明

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| `items` | array | 文档条目数组 |
| `items[].id` | integer | 文档唯一标识 |
| `items[].title` | string | 文档标题 |
| `total` | integer | 符合条件的总条数 |

!!! note "说明"

    这里描述的是"如果要做后端会长什么样"，本次作业不实现真实服务。
    写这一页的目的是练习用表格和代码块把接口约定讲清楚。

返回 [首页](index.md) 或 [关于本项目](about.md)。
