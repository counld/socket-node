This is a simple chat demo by using Node.js and Socket.IO.

## 启动项目 
npm run start  启动后台服务

client 端 直接打开浏览器 socket连接服务器 

```javascript 
使用ws 协议启动
	//连接websocket后端服务器
	this.socket = io.connect('ws://localhost:3000');
  前台必须得后台通过跨域设置请求头，这样才能跟服务器进行通信，
  不然会跨域

  它实现了浏览器与服务器全双工（full-duplex）通信，能更好地节省服务器资源和带宽并达到实时通讯。
  WebSocket建立在TCP之上，同HTTP一样通过TCP来传输数据，但是它和HTTP最大不同是：WebSocket是
  一种双向通信协议，在建立连接后，WebSocket服务器和Browser/Client Agent都能主动地向对方发送
  或接收数据，就像Socket一样；WebSocket需要类似TCP的客户端和服务器端通过握手连接，连接成功
  后才能相互通信

```

通过后端设置跨域请求，这样前台就可以请求到后端的消息推送啦

var io = require('socket.io')(http,{ cors: true });
这个真的是好用,
前台通过io接通scoket连接后台