
[TOC]
# 二手车交易平台系统 



### 项目简介
> 　　随着国家经济飞速发展,国民生活水平的不断提高,人们对于生活质量有了更高的需求,汽车对于一个家庭来说可以提供更多生活上的便利,提高生活的水平,所以中国汽车保有量逐年增加,有大幅度增长.随之而来的是汽车产业的觉醒.基于此需求,本平台系统将依托于互联网搭建一个O2O(即Online To Offline)模式的二手汽车交易平台.以满足二手汽车进行线上公开透明交易,线下实体汽车交付的需求.



###  主体流程
> 　　用户可进行线上对二手车进行浏览,查看待卖二手汽车相关详细信息,包括汽车外观图汽车相关手续资料,包括汽车外观图,汽车相关手续资料,汽车第三方评估报告等.对于有卖车意向的卖家,卖家用户可以进行在线注册个人信息以及填写上传所卖二手汽车的相关信息,申请买车用户需等待平台进行信息验证,待验证成功,即可发布卖车信息,等待买家出价.对于有买车意向的用户,买家用户可在平台看到相关卖车信息,如需购买,可进行在线注册,登记上传相关个人信息,绑定用户银行卡,并进行认证.认证通过的用户,可以对有意向的汽车进行出价,双方达成买卖意向,生成相应的订单,买卖双方签署订单协议,并进行线下个过户.



### 分析可能出现的功能

* 二手车首页展示
* 二手车详细页展示
* 生成PDF
* 卖家买家角色区分
* 卖家注册
* 上传图片
* 更改状态
* 买家注册
* 购买功能
* 银行卡验证
* 撮合功能
* 订单功能
* 生成订单打印功能



### 二手车分类列表

* 完善车分类列表
* 最近浏览
* 卖车信息列表
* 消息列表
* 个人信息展示
* 个人信息修改
* 出价购买意向表
* 服务保障展示
* 登录



#### 卖家

> 用户注册>登录>完善 个人信息>完善卖车信息>等待审核>发布卖车信息



#### 买家

> 用户注册>登录>完善个人信息>浏览首页>浏览列表页>浏览详情页>出价购买>等待撮合>撮合成功生成订单



#### 平台

> 审核发布信息，审核订单
>
> 卖家买家线下过户



#### 设计表结构

1. 用户表（使用Django自带表做继承扩展）
   * 手机号码
   * 姓名
   * 身份证号码
   * 地址
   * 性别
2. 品牌表
   * logo
   * 品牌
   * 是否删除
3. 汽车信息表（需要关联用户）
   * 用户F （foreign key）
   * 品牌F
   * 车名
   * 上牌日期
   * 发动机号
   * 公里数
   * 维修记录
   * 期望售价
   * 成交价格
   * 新车价格
   * 图片
   * 手续
   * 债务
   * 卖家承诺
   * 审核进度
   * 是否购买
   * 是否删除
4. 购买意愿表
   * 用户F
   * 车辆F
   * 价格
5. 订单表
   * 车辆信息
   * 成交价格
   * 订单号
   * 订单状态
   * 买家
   * 卖家
6. 消息表
   * 消息
   * 日期
   * 消息状态
   * 用户F
7. 银行信息表
   * 开户行
   * 银行卡号
   * 状态
   * 用户F
