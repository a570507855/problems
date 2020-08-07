#post提交的跨域问题(前端：axios)
后端解决方法：设置header：{'Access-Control-Allow-Origin':'\*'}
其中\*为通配符,可以设置成允许一个或多个域名访问  
前端解决方法：  
```javascript
  import querystring from 'querystring' //node.js环境中可直接引入
  //import qs from 'qs' //npm i qs; qs.stringify(req.data)
  axios.interceptors.request.use(req => {
    if(req.method === 'post'){
        req.data = querystring.stringify(req.data);//将{name:xyy,age:26}对象 转化为name=xyy;age=26格字符串格式
    }
    return req;
  })  
```


