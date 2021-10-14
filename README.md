基于美团瓦力的多渠道打包方案：
打包：采用命令行方式完成对母包apk的批量分包操作，
读取：APP内只需要集成美团瓦力的分包信息读取sdk即可

============================

打包使用方法：
	1、拷贝需要分包的APK母包到根目录
	2、编辑修改channel文件中的渠道列表（注意：一个渠道一行）
	3、运行publish.exe文件

============================

App集成及读取方法：
	implementation 'com.meituan.android.walle:library:1.1.6'
	
	ChannelInfo channelInfo = WalleChannelReader.getChannelInfo(getApplicationContext()); //获取渠道信息
	String channelName = channelInfo.getChannel(); //渠道名称
	Map<String, String> extraInfo = channelInfo.getExtraInfo();  //额外信息
    String channel = WalleChannelReader.getChannel(getApplicationContext()); //直接获取渠道名

============================

原文链接：https://www.jianshu.com/p/3906acba482c
瓦力项目：https://github.com/Meituan-Dianping/walle