# Flutter_ZZYVideoPlayer
这是一款基于共享外接纹理坐标texture的方式，集成的跨平台播放视频的框架

1、前提：
项目中已经集成Flutter混合开发框架

2、在Native侧使用该视频播放插件：
1）导入插件头文件
#import "TexturePlugin.h"

2）在开始视频播放时，启用插件
FlutterViewController *flutterVC = [[FlutterViewController alloc]initWithProject:nil nibName:nil bundle:nil];
[GeneratedPluginRegistrant registerWithRegistry:flutterVC.pluginRegistry];
_texture = [TexturePlugin registerWithRegistrar:[flutterVC.pluginRegistry registrarForPlugin:@"TexturePlugin"]];

3）将Native的视频数据源通过插件传入：
[_texture.glRender yuvPixelBufferWithData:_displayData width:width heigth:height];

通过上述步骤，即可将Native的视频数据源源不断的在Flutter页面播放出来
