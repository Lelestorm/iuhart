##表单验证
[转载来源](https://github.com/Lelestorm/build-web-application-with-golang/blob/master/zh/04.2.md)

### 必选字段
```golang
    if len(r.Form["username"][0])==0{
        //为空的处理
    }
```
### 数字
```golang
    getint,err:=strconv.Atoi(r.Form.Get("age"))
    if err!=nil{
        //数字转化出错了，那么可能就不是数字
    }

    if m, _ := regexp.MatchString("^[0-9]+$", r.Form.Get("age")); !m {
        return false
    }
```
### 中文
```golang
    if m, _ := regexp.MatchString("^\\p{Han}+$", r.Form.Get("realname")); !m {
        return false
    }
```
### 英文
```golang
    if m, _ := regexp.MatchString("^[a-zA-Z]+$", r.Form.Get("engname")); !m {
        return false
    }
```
### 邮箱
```golang
    if m, _ := regexp.MatchString(`^([\w\.\_]{2,10})@(\w{1,}).([a-z]{2,4})$`, r.Form.Get("email")); !m {
        fmt.Println("no")
    }else{
        fmt.Println("yes")
    }
```
### 手机号码
```golang
    if m, _ := regexp.MatchString(`^(1[3|4|5|8][0-9]\d{4,8})$`, r.Form.Get("mobile")); !m {
        return false
    }
```
### 下拉菜单 | 单选
```golang
    slice:=[]string{"apple","pear","banane"}
    
    v := r.Form.Get("fruit")
    for item in slice {
        if item == v {
            return true
        }
    }
    
    return false
```
### 复选框
```golang
    slice:=[]string{"football","basketball","tennis"}
    a:=Slice_diff(r.Form["interest"],slice)
    if a == nil{
        return true
    }

    return false
```
// Slice_diff() 函数 [Slice开源库(https://github.com/astaxie/beeku/blob/master/slice.go)](https://github.com/astaxie/beeku/blob/master/slice.go)

### 身份证号码
```golang
    //验证15位身份证，15位的是全部数字
    if m, _ := regexp.MatchString(`^(\d{15})$`, r.Form.Get("usercard")); !m {
        return false
    }

    //验证18位身份证，18位前17位为数字，最后一位是校验位，可能为数字或字符X。
    if m, _ := regexp.MatchString(`^(\d{17})([0-9]|X)$`, r.Form.Get("usercard")); !m {
        return false
    }
```

