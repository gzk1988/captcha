# golang实现的验证码 golang captcha



## 优点

1. 使用简单
2. 不依赖第三方图形库 直接go get 就Ok
3. 丰富自定义设置(字体,多颜色,验证码大小,文字模式,文字数量,干扰强度)



## demo

![color](http://115.28.182.181:8123/0)

![sample](http://115.28.182.181:8123/1)

![color2](http://115.28.182.181:8123/2)

## 使用 Start using it

Download and install it:
```
go get github.com/afocus/captcha
```
**必须设置font**

#### 最简单的示例 sample use

```go
cap = captcha.New()
// 设置字体
cap.SetFont("comic.ttf")
// 创建验证码 4个字符 captcha.NUM 字符模式数字类型
// 返回验证码图像对象以及验证码字符串 后期可以对字符串进行对比 判断验证
img,str := cap.Create(4,captcha.NUM)
```

#### 设置 set options

```go
cap = captcha.New()
cap.SetFont("comic.ttf")
// 设置验证码大小
cap.SetSize(128, 64)
// 设置干扰强度
cap.SetDisturbance(captcha.MEDIUM)
// 设置前景色 可以多个 随机替换文字颜色 默认黑色
cap.SetFrontColor(captcha.Color{255, 255, 255})
// 设置背景色 可以多个 随机替换背景色 默认白色
cap.SetBkgColor(captcha.Color{255, 0, 0}, captcha.Color{0, 0, 255}, captcha.Color{0, 153, 0})

img,str := cap.Create(4,captcha.NUM)
img1,str1 := cap.Create(6,captcha.ALL)
```

#### 自定义字符串 custom captcha words

```go
cap = captcha.New()
// 设置字体
cap.SetFont("comic.ttf")
img := cap.CreateCustom("hello")
```


#### 网站中如果使用? how to use for web

look `examples/main.go`




