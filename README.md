# 采用卷积神经网络（cnn）进行文本分类，依赖dl4j

## 简介
基于dl4j-example中的示例，训练数据较少，从某东上拉取了几百条产品及类型划分，可以用于文本分类，搜索意图识别

train.txt示例，第一列表示产品分类，后边则是分词后的产品名称   

eg.衣服 海澜之家 旗下 品牌 海澜 优选 生活馆 多色 条纹 短袖 t 恤 男 浅灰 条纹 07170 / 95

## 运行
1.运行Word2VecUtil.main生成word2vec.bin模型文件，data目录已存在，训练数据采用train.txt中的产品名称
2.运行CnnSentenceClassificationExample.main训练模型并输出测试结果

## 测试结果
Type:衣服, ProductName : 【 一件 48 两件 78 三件 98 】 t 恤 男 2018 男装 韩 版 夏季 短袖 t 恤 男 短袖 体恤 衣服 t 22 白色 xl    

   CNN Classify Result : [衣服(0.996828), 家用电器(0.001164), 电脑(6.77E-4), 玩具(5.43E-4), 图书(5.08E-4), 手机(2.8E-4), ] 
  
Type:衣服, ProductName : 良布 2018年 夏季 新款 男士 日 系 亚麻 短袖 薄 t 恤 男 短袖 v 领 薄 款 纯色 衣服 上衣 卡其色 xl   

   CNN Classify Result : [衣服(0.995663), 家用电器(0.001585), 玩具(0.001203), 电脑(8.92E-4), 手机(3.49E-4), 图书(3.08E-4), ]    
   

Type:衣服, ProductName : 稻草人 印花 短袖 t 恤 男 圆领 中年 dztc 6619 白色 175
   CNN Classify Result : [衣服(0.993972), 家用电器(0.002658), 电脑(0.001367), 玩具(0.001191), 手机(4.29E-4), 图书(3.83E-4), ]    
   

Type:衣服, ProductName : 古莱登 2018日 系 男士 圆领 短袖 t 恤 领口 绣 标 胸前 条纹 贴布 半 袖 男 白色 l  

   CNN Classify Result : [衣服(0.996824), 家用电器(0.001602), 玩具(6.34E-4), 电脑(6.31E-4), 手机(1.81E-4), 图书(1.28E-4), ]    
   

Type:玩具, ProductName : 儿童 3轮 三合一 可坐 可 滑 闪光 12岁 溜溜 车 6岁 滑 滑 玩具 男孩 女 手推 升级 款 樱 柠 粉 【 闪光 轮 】  

   CNN Classify Result : [玩具(0.980596), 家用电器(0.013514), 图书(0.003079), 衣服(0.002146), 电脑(5.48E-4), 手机(1.17E-4), ]    
   

Type:玩具, ProductName : 智 扣 （ zhikou ） 儿童玩具 活动 礼物 飞行 礼品 动力 男孩 女孩 电动 纸飞机 单只 装 颜色 随机   

   CNN Classify Result : [玩具(0.933394), 家用电器(0.054057), 图书(0.006034), 电脑(0.003206), 衣服(0.00254), 手机(7.69E-4), ]    
   

Type:玩具, ProductName : 诺澳辛 巴狗 系列 儿童 室内 秋千 滑梯 组合 家用 多功能 滑 滑梯 宝宝 滑梯 玩具 ( 吊绳 杆 款 ) 蓝色   

   CNN Classify Result : [玩具(0.962732), 家用电器(0.028758), 图书(0.004047), 电脑(0.002361), 衣服(0.001686), 手机(4.17E-4), ]    
   

Type:玩具, ProductName : 诺澳 儿童 室 内外 滑梯 组合 宝宝 家用 加长 游戏 滑 滑梯 塑料玩具 带 篮球架 ( 蓝 + 黄款)
   CNN Classify Result : [玩具(0.984875), 图书(0.006191), 家用电器(0.005006), 电脑(0.002104), 手机(0.00108), 衣服(7.44E-4), ] 

Type:手机, ProductName : 索爱 t 3 移动 / 联通 直板 按键 老年 机 三 防 老人 手机 超长 待机 双 卡 双 待 幻 海蓝
   CNN Classify Result : [手机(0.994408), 电脑(0.004041), 家用电器(7.65E-4), 玩具(4.07E-4), 衣服(2.5E-4), 图书(1.3E-4), ] 

Type:手机, ProductName : 小 辣椒红 辣椒 note 5 x 6 + 64 gb 学生 智能手机 ai 双 摄 全面 屏 移动 联通 电信 4 g 全 网通 黑色
   CNN Classify Result : [手机(0.99043), 电脑(0.006549), 图书(0.00191), 家用电器(4.88E-4), 衣服(3.85E-4), 玩具(2.37E-4), ] 

Type:手机, ProductName : 【 二手 95 新 】 appleiphonex 苹果 x 手机 深空 灰色 256 g 全 网通
   CNN Classify Result : [手机(0.970446), 电脑(0.009435), 图书(0.009028), 家用电器(0.00737), 衣服(0.002776), 玩具(9.44E-4), ] 

Type:家用电器, ProductName : 【 7折 秒杀 】 东芝 （ toshiba ） 电饭煲 小型 节能 pns 4升 【 特惠 】
   CNN Classify Result : [家用电器(0.990337), 玩具(0.003195), 手机(0.002408), 图书(0.001541), 衣服(0.001472), 电脑(0.001047), ] 

Type:家用电器, ProductName : 【 6折 秒杀 】 东芝 （ toshiba ） 电饭煲 多功能 pj 5升
   CNN Classify Result : [家用电器(0.993301), 玩具(0.003286), 手机(0.001287), 电脑(8.19E-4), 衣服(7.49E-4), 图书(5.58E-4), ] 

Type:图书, ProductName : 包邮 我们 爱科学 科学 大 侦探 杂志 铺 全年 订阅 2018年 8月 起 订阅 共 12期 少 儿科 谱 阅读 每月 快递
   CNN Classify Result : [图书(0.985099), 玩具(0.00417), 家用电器(0.003777), 衣服(0.003582), 手机(0.001844), 电脑(0.001527), ] 

Type:图书, ProductName : 福尔摩斯 探案集 全集 （ 套装 10册 ） 永久 珍藏版 全译本 世界 经典 名著 课外阅读 柯南 道尔
   CNN Classify Result : [家用电器(0.575636), 图书(0.412113), 玩具(0.008458), 衣服(0.001623), 电脑(0.001248), 手机(9.23E-4), ] 

Type:图书, ProductName : 丹布朗 系列 全集 【 套装 6册 】 地狱 + 骗局 + 数字 城堡 + 密码 + 失落 秘 符 + 天使 与 魔鬼
   CNN Classify Result : [图书(0.98155), 手机(0.007936), 家用电器(0.00562), 衣服(0.002107), 玩具(0.001431), 电脑(0.001355), ] 
