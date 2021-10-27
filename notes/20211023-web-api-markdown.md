# 



## API shili


#### 获取项目列表

```
GET /projects
```

| Name       | Type    | In     | Description                                                  |
| :--------- | :------ | :----- | :----------------------------------------------------------- |
| `accept`   | string  | header | Setting to `application/vnd.github.v3+json` is recommended.  |
| `org`      | string  | path   |                                                              |
| `state`    | string  | query  | Indicates the state of the projects to return. Can be either `open`, `closed`, or `all`.Default: `open` |
| `per_page` | integer | query  | Results per page (max 100)Default: `30`                      |
| `page`     | integer | query  | Page number of the results to fetch.Default: `1`             |

