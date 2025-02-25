腾讯云视立方播放器 Player 的点播播放器（Video on Demand Player SDK）是点播提供给用户连接云端服务，打造云端一体能力的重要组成；点播为用户提供了超级播放器、超级播放器 Adapter 两种类型的播放器，支持 Web 端、iOS 端、Android 端、Flutter 端四大终端，是腾讯云提供的集多功能于一体的高性能解决方案。它能够根据您的使用场景，在短时间内打造出流畅的观看体验。本文为您介绍它们的区别和使用方法，帮助用户选择适合自己的播放器。

[](id:concept)

### 基本概念说明

#### 超级播放器
点播超级播放器支持两种播放的模式：基础播放和点播播放。

| 播放模式 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| 基础播放 | 基础播放为点播提供给用户播放URL的方式，该播放方法常用于 **短视频** 或 **中视频** 等无需其他媒资辅助信息的场景，用户集成后不支持点播基于 Fileid 的数据统计和复杂媒资功能。 |
| 点播播放 | 点播播放为云点播提供给用户直接播放云点播 Fileid 的播放器，该播放方式提供点播云端资源和播放器 SDK 深度耦合的能力，常用于**长视频**等需要其他媒资辅助信息一起播放的场景，用户可以基于 Fileid 实现数据上报、监控和复杂媒资绑定功能。 |

#### 超级播放器 Adapter
超级播放器 Adapter 为云点播提供给客户希望使用第三方播放器或自研播放器开放的对接云 PAAS 资源的播放器，常用于有**强烈自定义播放器功能**需求的用户，有一定的技术接入门槛。

<table>
<tr><th width=21%>播放器类别</th><th width=20%>功能</th><th>特点</th><th>自定义程度</th><th>常见场景</th></tr>
<tr>
<td>超级播放器（基础播放）</td>
<td>仅支持播放媒体 URL</td>
<td>适用于云资源和播放器都使用云点播的用户</td>
<td>低</td>
<td>短视频/<br>中视频</td>
</tr>
<tr>
<td>超级播放器（点播播放）</td>
<td>仅支持播放点播 Fileid</td>
<td>适用于云资源和播放器都使用云点播的用户</td>
<td>低</td>
<td>长视频</td>
</tr>
<tr>
<td>超级播放器 Adapter</td>
<td>仅支持播放云点播 Fileid</td>
<td>适用于云资源使用云点播，播放器使用第三方或者自研播放器的用户</td>
<td>高</td>
<td>长视频</td>
</tr></table>

[](id:core)

### 核心优势

- **云端一体**：用户可以轻松使用云点播 PAAS 资源，构建云端一体能力。
- **视频安全**：提供防盗链、URL 鉴权、HLS 加密、私有协议加密、本地加密等多种加密方案，全方位保证用户媒体安全，满足不同场景安全需求。
- **视频播放**：提供首屏秒开、边播边缓存、倍速播放、视频打点、媒体弹幕和外挂字幕等多种功能。
- **视频加速**：依靠腾讯云海量加速节点，提供完备的视频加速能力，毫秒级的延迟让用户无延迟体验极速视频播放。

[](id:function)

### 特色功能

通过集成腾讯云视立方点播超级播放器，我们支持多种功能一键集成，更多功能查看 [功能列表](https://cloud.tencent.com/document/product/266/45539#.E8.83.BD.E5.8A.9B.E6.B8.85.E5.8D.95.3Ca-id.3D.22p1.22.3E.3C.2Fa.3E)。

<table>
<tr><th width=10%>功能</th><th>功能描述</th><th width=20%>其他说明</th></tr>
<tr>
<td>视频加密</td>
<td>支持标准 HlS 加密和腾讯云私有协议加密</td>
<td><a href="https://cloud.tencent.com/document/product/266/45552">视频加密综述</a></td>
</tr>
<tr>
<td>视频播放</td>
<td>支持在不同场景下结合点播下媒体和相关媒资辅助信息，并通过 FileId 输出，完成多样化视频播放能力</td>
<td><a href="https://cloud.tencent.com/document/product/266/45539">视频播放综述</a></td>
</tr>
<tr>
<td>安全下载</td>
<td>支持将下载的视频在本地进行二次加密，确保用户的媒体仅通过唯一的应用播放</td>
<td><a href="https://cloud.tencent.com/document/product/266/46220">安全下载 - 链接占位</a></td>
</tr></table>

[](id:scenes)

### 使用场景

#### 短视频/中视频
短视频/中视频通常时长较短，仅需要播放一路转码流，这类视频通常通过 URL 播放，点播推荐用户在这种场景下使用超级播放器的基础播放能力，常用场景如下：
- 短视频社交平台（微视、快手、抖音）中播放的视频。
- 电商购物平台（京东、拼多多）中的商品宣传视频。
- 社区内容平台（微信公众号、自媒体）中分享的资讯短片。
腾讯云基础播放器在这种场景下支持播放预加载，首屏秒开，播放控制等功能，帮助用户更便捷集成相关播放能力。

#### 长视频
长视频通常时长较长，同时涉及大量的媒资辅助相关信息，这类视频通常不仅仅包含媒体源文件，还会包含视频截图，视频打点信息媒资辅助信息，这类视频在云点播中会统一挂载到一个 Fileid 下，这类视频通过 Fileid 能够携带丰富的媒体信息，点播推荐用户在这种场景下使用超级播放器的点播播放能力，常见场景如下：
- 视频媒体平台（腾讯视频、优酷、爱奇艺）发布的独播剧、综艺节目和视频门户网站等。
- 在线教育网站（腾讯课堂、企鹅辅导）的课程视频。
- 网络电视平台（CNTV、芒果 TV）的电视节目回看视频。
腾讯超级播放器支持视频加密，自动切换视频清晰度，视频试看，多种格式和编码的媒体播放等功能，帮助用户更加全面的完善产品播放能力。

[](id:link)

### 相关链接

腾讯云视立方点播播放器 Player 支持 Web 端、iOS 端、Android 端、Flutter 端四大终端, 其中 Flutter 仅支持超级播放器使用，详情请参见表格中的文档。

<table>
<thead>
<tr>
<th>终端类别</th>
<th>功能列表</th>
<th>SDK 下载</th>
<th>Demo 展示</th>
<th>使用文档</th>
</tr>
</thead>
<tbody><tr>
<td>iOS 端集成</td>
<td><a href="https://cloud.tencent.com/document/product/266/45539#.E8.B6.85.E7.BA.A7.E6.92.AD.E6.94.BE.E5.99.A8">能力清单</a></td>
<td><a href="https://github.com/tencentyun/SuperPlayer_iOS">Github</a></td>
<td><img src="https://main.qcloudimg.com/raw/12c7da97cc910eda673cb19b66fc7cb3.png" width="150"></td>
<td><a href="https://cloud.tencent.com/document/product/1449/57082?!preview&!editLang=zh">超级播放器</a>、<a href="https://cloud.tencent.com/document/product/1449/57084?!preview&!editLang=zh">超级播放器 Adapter</a></td>
</tr>
<tr>
<td>Android 端</td>
<td><a href="https://cloud.tencent.com/document/product/266/45539#.E8.B6.85.E7.BA.A7.E6.92.AD.E6.94.BE.E5.99.A8">能力清单</a></td>
<td><a href="https://github.com/tencentyun/SuperPlayer_Android">Github</a></td>
<td><img src="https://main.qcloudimg.com/raw/6790ddaf4ffe4afd0ceb96b309a16496.png" width="150"></td>
<td><a href="https://cloud.tencent.com/document/product/1449/57085?!preview&!editLang=zh">超级播放器</a>、<a href="https://cloud.tencent.com/document/product/1449/57087?!preview&!editLang=zh">超级播放器 Adapter</a></td>
</tr>
<tr>
<td>Flutter 端</td>
<td><a href="https://cloud.tencent.com/document/product/1449/57091#.E8.B6.85.E7.BA.A7.E6.92.AD.E6.94.BE.E5.99.A8">能力清单</a></td>
<td><a href="https://github.com/tencentyun/SuperPlayer/tree/main/Flutter">Github</a></td>
<td><a href="https://github.com/tencentyun/SuperPlayer/tree/main/Flutter">Demo</a></td>
<td><a href="https://cloud.tencent.com/document/product/1449/57091?!preview&!editLang=zh">超级播放器</a></td>
</tr>
<tr>
<td>Web 端</td>
<td><a href="https://cloud.tencent.com/document/product/266/45539#.E8.B6.85.E7.BA.A7.E6.92.AD.E6.94.BE.E5.99.A8">能力清单</a></td>
<td><a href="https://tcloud-doc.isd.com/document/product/266/14424?">SDK</a></td>
<td><a href="https://imgcache.qq.com/open/qcloud/video/tcplayer/examples/vod/tcplayer-vod-base.html">Demo</a></td>
<td><a href="https://cloud.tencent.com/document/product/1449/57088?!preview&!editLang=zh">超级播放器</a>、<a href="https://cloud.tencent.com/document/product/1449/57089?!preview&!editLang=zh">超级播放器 Adapter</a></td>
</tr>
</tbody></table>

[](id:method)
### 集成方式

| 播放器类型 | SDK 下载地址 | 使用文档 |
| ---------- | ---------- | ---------- |
| 超级播放器 | <ul style="margin:0;"><li>[Android](https://cloud.tencent.com/document/product/1449/57085?!preview&!editLang=zh#sdk-.E4.B8.8B.E8.BD.BD)</li><li>[iOS](https://cloud.tencent.com/document/product/1449/57082?!preview&!editLang=zh#sdk-.E4.B8.8B.E8.BD.BD)</li><li>[Web](https://cloud.tencent.com/document/product/1449/57088?!preview&!editLang=zh#sdk-.E4.B8.8B.E8.BD.BD)</li><li>[Flutter](https://cloud.tencent.com/document/product/1449/57091?!preview&!editLang=zh#sdk-.E4.B8.8B.E8.BD.BD)</li></ul> | <ul style="margin:0;"><li>[Android](https://cloud.tencent.com/document/product/1449/57085?!preview&!editLang=zh)</li><li>[iOS](https://cloud.tencent.com/document/product/1449/57082?!preview&!editLang=zh)</li><li>[Web](https://cloud.tencent.com/document/product/1449/57088?!preview&!editLang=zh)</li><li>[Flutter](https://cloud.tencent.com/document/product/1449/57091?!preview&!editLang=zh)</li></ul> |



### 接入指引
为了帮助您快速接入点播的超级播放器，我们为您提供了超级播放器 [接入指引](https://cloud.tencent.com/document/product/266/43629)，以示例的方式为您讲解接入步骤。

  
