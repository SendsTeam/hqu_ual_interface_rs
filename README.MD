# HQU_UAL_INTERFACE_RS

## 华侨大学统一验证登录逆向接口--RUST版

**注意: 使用统一身份认证逆向服务需要取消统一身份认证设置中的只能在一个浏览器上登录的选项，否则无法重复逆向**

统一身份认证设置入口：w.hqu.edu.cn -> 信息门户 -> 右上角个人设置 -> 偏好设置/其他设置/第一个选项

## example

POST:

```json
{
    "stunum":"212510XXXX",
    "password":"XXXXX"
}
```

RETURN:

```json
{
    "code": 200,
    "data": {
        "CASTGC": "TGT-629062-BHWJtRnzHSjwunfC-4Fm37blxGhPUKhP09AKOxwhlXripvQvpwyPYtjO4JdCu3Cf6O4tpl-Euler",
        "GS_SESSIONID": "51d2ad3a4c8b93241426d946f086e627"
    },
    "msg": "Ok"
}
```

or

```json
{
    "code": 500,
    "data": "模拟登录错误: 您提供的用户名或者密码有误",
    "msg": "Error"
}
```

or

```json
{
    "code": 200,
    "data": {
        "CASTGC": "TGT-577490-VVcojPDc884tYzNNAzJFY5HnkflsVvPyvdZcZG-eLz6q2qQ3dJ8MX1PTUJ3p8HjJ-RYtpl-Euler"
    },
    "msg": "Ok"
}
```

`有了jwapp的cookie：GS_SESSIONID 即可获取jwapp数据`
