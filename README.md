# 智能魔方

## 1、用户模块

### 1.1 登录  get  api/user/login

| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| loginName | true | string | 登录名 |
| password | true | string | 密码 |

| 返回值 | 类型 | 说明 |
| ------ | ------ | ------ |
| id | Number | Id |
| nickName  | string | 昵称 |
| loginName  | string | 登录名 |
| photo  | string | 头像路径 |
| phone  | string | 手机号 |
| email  | string | 邮箱 |
| qq  | string | qq |
| wenxi  | string | 微信 |
- 例如

```javascript
{	
	"id": "4"
	"nickName": "张三", 
	"loginName": "zhangsan10",
	"photo": "",
	"phone": "",
	"email": "123456@qq.com",
	"qq": 12121212,
	"wenxi": 12121212
}
```
### 1.2 修改个人信息 put api/user
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| id | true | string | id |
| nickName | false | string | 昵称 |
| loginName | false | string | 登录名 |
| photo | false | string | 头像路径 |
| phone | false | string | 手机 |
| email | false | string | 邮箱 |
| qq | true | string | qq
| wenxi | true | string | 微信 |
- 例如

```javascript
{"code":0,"msg":"更新成功"}
```
### 1.3 登出 post api/user/logout
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| id | true | string | id |
- 例如

```javascript
{"code":0}
```
### 1.4 注册post api/user/register
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| password | true | string | 密码 |
| nickName | false | string | 昵称 |
| loginName | false | string | 登录名 |
| photo | false | string | 头像路径 |
| phone | false | string | 手机 |
| email | false | string | 邮箱 |
| qq | true | string | qq
| wenxi | true | string | 微信 |
- 例如

```javascript
正确返回：{"code":0,"msg":"注册成功"}
错误返回：{"code":1,"msg":"登录名重复"}
```

## 2、短信模块
### 2.1 注册验证 post api/sms
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| phone | true | string | 手机号 |

- 例如

```javascript
{"code":0,"verifi_code":106610}
```
### 2.2 登录验证 get api/sms
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| phone | true | string | 手机号 |

- 例如

```javascript
{"code":0,"verifi_code":106610}
```

## 3、魔方模块
### 3.1 通过id获取魔方信息 get api/mgc
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| id | true | string | 魔方id |

| 返回值 | 类型 | 说明 |
| ------ | ------ | ------ |
| id | Number | Id |
| sequence  | string | 序列号 |
| type  | string | 类型 |
| bind_number  | string | 绑定设备数量 |
| bind_user  | string | 绑定的用户 |
### 3.2 用户绑定魔方 put api/mgc/bind
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| mgc_id | true | number | 魔方id |
| user_id | true | number | 用户id |
- 例如

```javascript
正确返回：{"code":0,"msg":"绑定成功"}
错误返回：{"code":1,"msg":"不可重复绑定"}
```
## 3.3 用户解除绑定魔方 put api/mgc/unbind
| 请求参数 | 必选 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| mgc_id | true | number | 魔方id |
| user_id | true | number | 用户id |
- 例如

```javascript
正确返回：{"code":0,"msg":"解除绑定成功"}
错误返回：{"code":1,"msg":"未绑定"}
```
## 4 转动数据
### 4.1 上传转动数据 post api/obs
- 参数待定


