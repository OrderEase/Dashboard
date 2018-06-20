# RESTful API 规范

## 中英命名

| 中文                        | 英文                        |
| --------------------------- | --------------------------- |
| 菜品                        | Dish                        |
|菜品类别| Category |
| 菜单                        | Menu                        |
| 餐厅                        | Restaurant (简写 Restrt)    |
| 活动                        | Promotion                   |
| 优惠 (「活动」中的具体条款) | Rule  |
|优惠要求金额| Requirement |
|优惠程度|Discount |
| 上架 / 下架                 | Available  / Unavailable    |
| 点赞                        | Like                        |
| 催单                        | Urge                        |
| 库存                        | Stock                       |

## HTTP 请求

### 方法

`GET` 方法用来获取 item 信息
`PUT` 方法可用来更新一个 item 信息
`POST` 方法可用来创建一个 item
`DELETE` 方法用于删除 item

### 响应状态码

200 (“OK”) 用于一般性的成功返回。

201 (“Created”) 资源被创建。

202 (“Accepted”) 用于Controller控制类资源异步处理的返回，仅表示请求已经收到。对于耗时比较久的处理，一般用异步处理来完成。

204 (“No Content”) 此状态可能会出现在PUT、POST、DELETE的请求中，一般表示资源存在，但消息体中不会返回任何资源相关的状态或信息。

301 (“Moved Permanently”) 资源的URI被转移，需要使用新的URI访问。

302 (“Found”) 不推荐使用，此代码在HTTP1.1协议中被303/307替代。我们目前对302的使用和最初HTTP1.0定义的语意是有出入的，应该只有在GET/HEAD方法下，客户端才能根据Location执行自动跳转，而我们目前的客户端基本上是不会判断原请求方法的，无条件的执行临时重定向。

303 (“See Other”) 返回一个资源地址URI的引用，但不强制要求客户端获取该地址的状态(访问该地址)。

304 (“Not Modified”) 有一些类似于204状态，服务器端的资源与客户端最近访问的资源版本一致，并无修改，不返回资源消息体。可以用来降低服务端的压力。

307 (“Temporary Redirect”) 目前 URI 不能提供当前请求的服务，临时性重定向到另外一个URI。在HTTP1.1中307是用来替代早期HTTP1.0中使用不当的302。

400 (“Bad Request”) 用于客户端一般性错误返回, 在其它 4xx 错误以外的错误，也可以使用 400，具体错误信息可以放在body中。

401 (“Unauthorized”) 在访问一个需要验证的资源时，验证错误。

403 (“Forbidden”) 一般用于非验证性资源访问被禁止，例如对于某些客户端只开放部分API的访问权限，而另外一些API可能无法访问时，可以给予403状态。

404 (“Not Found”) 找不到 URI 对应的资源。

405 (“Method Not Allowed”) HTTP 的方法不支持，例如某些只读资源，可能不支持 POST/DELETE。但405的响应header 中必须声明该 URI 所支持的方法。

406 (“Not Acceptable”) 客户端所请求的资源数据格式类型不被支持，例如客户端请求数据格式为application/xml，但服务器端只支持 application/json。

409 (“Conflict”) 资源状态冲突，例如客户端尝试删除一个非空的Store资源

412 (“Precondition Failed”) 用于有条件的操作不被满足时

415 (“Unsupported Media Type”) 客户所支持的数据类型，服务端无法满足

500 (“Internal Server Error”) 服务器端的接口错误，此错误于客户端无关

## 其他

1. 不宜使用过于冗长的 API。
2. 敏感请求使用 OAuth 2.0 进行认证。
3. 全部使用 JSON 格式进行数据返回，避免使用 XML。