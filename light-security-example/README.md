# Light Security使用示例

## 测试步骤

### 第一步：登录，获取token

```shell
GET http://localhost:8009/login
# 即可返回token，简单起见，该端点直接模拟了一个用户叫张三，拥有user、admin角色
```



### 第二步：验证基于 `application.yml` 的权限控制

```shell
# 请求/user端点，该端点需要具备admin/user角色之一才能访问
GET http://localhost:8009/user
Authorization:Bearer 你的token
```



### 第三步：验证基于注解的权限控制

```shell
# 请求/annotation-test端点，该端点必须同时具备admin以及user端点才能访问
GET http://localhost:8009/annotation-test
Authorization:Bearer 你的token
```



## IntelliJ IDEA懒人玩法

用IDEA打开 `IDEA HTTP Client测试脚本.http` ，依次执行第一步、第二步、第三步即可。