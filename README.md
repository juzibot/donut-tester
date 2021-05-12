# donut-tester

We have launched a new puppet `wechaty-puppet-donut`. It is ready for testing, and Alpha Testing Volunteers are needed.

Unlike the previous puppet-pad* version, wechaty-puppet-donut is a **windows hook solution**. Compare with puppet-pad*, the new puppet has improvement in some aspect below:

- Support mini app
- Support WeChat Work Mix Message

If you want to benefit from all the new features, you are welcomed to apply for joining the Alpha Testing List.

You can leave a comment under [Issue 1941: [Call for Volunteers] Win32 Puppets: wechaty-puppet-donut is going to ready for testing!](https://github.com/wechaty/wechaty/issues/1941), introduce yourself about who you are and what you want to do (**please DO follow the following TEMPLATE and fill it in details, or you might not be able to be selected**), so that we can be able to add you to the alpha testing list if you are qualified.

## Run

### Install
Only need to install wechaty by command:
```
npm install wechaty@next
```

### Example
```ts
import { Wechaty } from 'wechaty'
import { ScanStatus } from 'wechaty-puppet'
import QrcodeTerminal from 'qrcode-terminal';

const token = 'PUT_YOUR_TOKEN_HERE'

const bot = new Wechaty({
  puppet: 'wechaty-puppet-service',
  puppetOptions: {
    token,
  }
});

bot
  .on('scan', (qrcode, status) => {
    if (status === ScanStatus.Waiting) {
      QrcodeTerminal.generate(qrcode, {
        small: true
      })
    }
  })
  .on('login', async user => {
    console.log(`user: ${JSON.stringify(user)}`)
  })
  .on('message', async message => {
    console.log(`message: ${JSON.stringify(message)}`)
  })
  .start()
```

## Here is the requirement for the alpha test user

1. Strong willingness & motivation in wechaty-puppet-donut
2. Have the ability & engineering power to fix the basic bug instead of just asking for support
3. Good to communicate with the developers in the community
4. The basic requirement for bot online time: we might take the test token back if the bot is offline for more than 1 day.
5. Willing to write a blog to share the experience of using wechaty-puppet-donut

## Wechaty Puppet Donut Alpha Tester Apply Template

1. Introduce Yourself(who you are):

2. Explain the Problem You Want to Solve:(what you do):

3. Are Your Bot Related with the Following Tasks? (YES/NO)
Gambling
Adault & Sex

4. Your Email:

5. Your Wechat:

6. I Had Joined the Wechaty Developers' Home Wechat Room by Scan QRCode from README.md: (Please join the group if you are not, and then say YES at here)

7. I understand that the Wechaty Puppet Donut is in very Early Alpha Stage, and I have the necessary engineering technics to deal with the bugs instead of just asking for support: (Please say YES, then followed by your Name at here)

## Unsupported API List
> The unsupported api will throw Wechaty Puppet Unsupported API Error.

1. get contact alias
2. get room member alias
3. get room QR code
4. all Tag related methods
5. get bot qrcode


## Puppet Comparison

功能 | donut | padpro | padplus | macpro
---|---|---|---|---
 **<消息>**|  |  |
 收发文本| ✅ | ✅ |✅ |✅
 收发个人名片| ✅ | ✅ |✅ |✅
 收发图文链接| ✅ | ✅ |✅ |✅
 发送图片、文件| ✅ | ✅ | ✅（对内容有大小限制，20M以下） |✅
 接收图片、文件| ✅ | ✅ | ✅（对内容有大小限制，25M以下） |✅
 发送视频| ✅ | ✅ | ✅ | ✅
 接收视频| ✅ | ✅ | ✅ | ✅
 发送小程序| ✅ | ❌ | ✅ | ✅
 接收动图| ❌ | ❌ | ✅ | ✅
 发送动图| ✅ | ❌ | ✅ | ✅
 接收语音消息| ✅ | ✅ | ✅ | ✅
 发送语音消息| ❌ | ✅ | ❌ | ❌
 转发文本| ✅ | ✅ | ✅ | ✅
 转发图片| ✅ | ✅ | ✅ | ✅
 转发图文链接| ✅ | ✅ | ✅ | ✅
 转发音频| ✅ | ✅ | ❌ | ✅
 转发视频| ✅ | ✅ | ✅ | ✅
 转发文件| ✅ | ✅ | ✅ | ✅
 转发动图| ❌ | ❌ | ❌ | ❌
 转发小程序| ✅ | ❌ | ❌ | ❌
 **<群组>**|  |  |  |
 创建群聊|✅|✅|✅|✅
 设置群公告|✅|✅|✅|✅
 获取群公告|✅|❌|✅|❌
 群二维码|❌|✅|✅|✅
 拉人进群|✅|✅|✅|✅
 踢人出群|✅|✅|✅|✅
 退出群聊|✅|✅|✅|✅
 改群名称|✅|✅|✅|✅
 入群事件|✅|✅|✅|✅
 离群事件|✅|✅|✅|✅
 群名称变更事件|✅|✅|✅|✅
 @群成员|✅|✅|✅|✅
 群列表|✅|✅|✅|✅
 群成员列表|✅|✅|✅|✅
 群详情|✅|✅|✅|✅
 **<联系人>**|  |  |  |
 修改备注|✅|✅|✅|✅
 添加好友|✅|✅|✅|✅
 自动通过好友|✅|✅|✅|❌
 好友列表|✅|✅|✅|✅
 好友详情|✅|✅|✅|✅
 **<其他>**|  |  |  |
 登录事件|✅|✅|✅|✅
 扫码状态|❌|✅|✅|❌
 登出事件|✅|✅|✅|✅
 依赖协议|windows|iPad|iPad|Mac|
