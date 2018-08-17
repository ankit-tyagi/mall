# mall

## 技术选型

### 后端技术

技术 | 名称 
----|----
Spring Boot | 容器+MVC框架
Spring Security | 认证和授权框架
MyBatis | ORM框架  
MyBatisGenerator | 代码生成  
PageHelper | MyBatis物理分页插件  
Swagger-UI | 文档生产工具
Hibernator-Validator | 验证框架
Elasticsearch | 搜索引擎
RabbitMq | 消息队列
Redis | 分布式缓存
MongoDb | NoSql数据库

### 前端技术

技术 | 名称 
----|----
Vue | 前端框架
Vue-router | 路由框架
Vuex | 全局状态管理框架
Element | 前端UI框架
Axios | 前端HTTP框架
Js-cookie | cookie管理工具

### 框架搭建

功能 | 完成 
----|----
集成MyBatis | ✔
集成MyBatisGenerator | ✔
集成SpringSecurity | ✔
集成Swagger-UI | ✔
集成Hibernator-Validator | ✔
集成日志功能 | ✔
集成监控功能 | ✔
crud操作demo | ✔
合理规划包结构 | ✔
SpringAOP通用日志处理 | ✔
SpringAOP通用验证失败结果返回 | ✔
CommonResult对通用返回结果进行封装 | ✔
SpringSecurity登录改为Restful形式 | ✔
JWT登录、注册、获取token | ✔
JTA事务处理 | ✔
集成单元测试 | ✔
OSS上传功能 | ✔
Elasticsearch搜索功能 | ✔
SpringSecurity权限管理功能 |
HTTPS支持 | ✔
日志收集功能 |
数字型ID生成 |
定时任务支持 |
RestTemplate服务间调用 |
docker容器化部署 |

### 后台功能

#### 后台登录功能 ✔

- 后台用户注册功能
- 后台用户登录后获取token
- 刷新token功能

#### 商品管理 ✔

> **商品分类管理**

- 按父分类编号分页查看分类列表
- 添加、编辑、删除分类
- 转移分类商品

> **商品品牌管理**

- 按品牌名称搜索分页查看品牌列表
- 添加、编辑、删除品牌
- 查看当前品牌的所有产品

> **商品属性分类管理**

- 添加商品属性分类（名称）
- 分页查询全部商品属性分类
- 删除单个商品属性分类
- 修改单个属性分类名称
- 查询单个属性分类信息

> **商品属性管理**

- 根据分类查询属性列表或参数列表（分页，支持类型）
- 添加商品属性
- 查询单个商品属性
- 编辑商品属性
- 批量删除商品属性
- 分页查询全部商品属性

> **添加商品**

- 选择商品分类：根据商品分类id查找分类
- 选择品牌：查询全部品牌
- 选择运费模版：查询全部运费模版
- 设置会员价格：查询所有会员等级，传入List<PmsMemberPrice>
- 添加阶梯价格: 参数传入List<PmsProductLadder>
- 设置满减价格: 参数传入List<PmsProductFullReduction>
- 选择商品属性类别:获取所有商品属性分类，根据商品属性分类的id获取规格和参数(type=0->规格；type=1->参数)
- 选择规格并生成库存信息：前端实现
- 添加sku库存信息：参数传入List<PmsSkuStock>
- 设置属性图片：设置到pic和album_pics字段中去
- 添加商品参数：参数传入List<PmsProductAttributeValue>
- 添加自定义商品规格：参数传入List<PmsProductAttributeValue>
- 关联专题:参数传入List<CmsSubjectProductRelation>关系
- 关联优选:参数传入List<CmsPrefrenceAreaProductRelation>关系

> **修改商品**

- 根据商品id查询商品信息
- 查询商品基本信息：商品分类名称、品牌名称、运费模版名称
- 查询商品促销信息：商品的会员价格、阶梯价格、满减价格
- 查询商品属性信息：商品属性类别名称、sku库存信息、属性分类对应规格和参数值
- 查询商品关联信息：商品关联专题和关联优选
- 修改商品信息：商品属性分类及规格不可修改，只支持单个sku的修改、删除、新增；商品属性分类及规格可以修改：修改后同时显示原sku库存及属性分类

> **商品分页查询**

- 商品的状态：全部商品、已上架、未上架、待审核、未通过 (publishStatus verifyStatus)
- 商品名称(%name%)
- 商品货号(productSn)
- 商品分类id(productCategoryId)
- 商品品牌id(brandId)
- 批量操作：上下架、推荐、新品、转移分类、放入回收站、审核
- 查看记录：审核记录，操作日志
- sku:根据产品及sku编号获取sku信息，批量修改sku信息

> **商品回收管理** ❓

- 分页展示回收商品列表
- 回收商品还原功能

> **商品评价管理** ❓

#### 促销管理

> **秒杀活动管理**

- 活动列表展示
- 活动上下线
- 设置活动商品
- 添加、编辑、删除活动

> **优惠券管理**

- 优惠券列表展示
- 添加、编辑、删除优惠券
- 查看优惠券领取记录

> **活动管理**

- 活动列表展示
- 添加、编辑、删除活动
- 活动上下线
- 发布到广告

> **首页推荐**

- 品牌推荐：列表展示、是否推荐、排序、删除、多选加入品牌
- 新鲜好物：商品列表展示、是否推荐、排序、删除、多选加入商品
- 人气推荐：商品列表展示、是否推荐、排序、删除、多选加入商品
- 专题精选：专题列表展示、是否推荐、排序、删除、多选加入专题
- 广告管理：广告列表展示、是否上线、排序、删除、添加编辑广告

#### 内容管理

> **专题管理**

- 专题列表：查看、删除、推荐专题
- 添加、编辑专题：选择专题分类、添加、删除关联商品
- 专题分类管理：控制显示、排序、编辑删除分类

> **优选主题**

- 优选列表：控制显示、排序、删除
- 添加、编辑优选：关联和删除商品

> **话题管理**

- 专题列表：查看、删除、热门话题
- 话题分类管理：控制显示、排序、编辑删除分类

> **帮助管理**

- 帮助列表：查看、删除、控制显示
- 添加、编辑帮助：选择帮助分类
- 帮助分类管理：控制显示、排序、编辑删除分类

#### 用户管理

> **用户管理**

- 用户列表：帐号启用、删除、群发短信
- 批量操作：群发短信、站内信、推送、设置标签、赠送优惠券
- 查看、编辑用户信息：用户详情（统计信息、收货地址、订单记录）、编辑资料、登录日志
- 购买力筛选：最近消费、消费次数、消费金额、订单均价、商品分类、会员等级、用户标签
- 用户标签管理：标签列表、添加、编辑、删除
- 会员等级设置：列表、添加、编辑、设置默认会员等级

> **成才值及积分**

- 成长值及积分查询：列表展示、积分明细、成长值明细、修改数值
- 任务奖励设置：新手任务、日常任务
- 更多规则设置：成长值规则、积分规则、积分消费设置

#### 订单管理

#### 权限管理

> **权限管理**

- 角色管理：角色列表、分配菜单权限、添加、编辑、删除角色
- 成员管理：成员列表、单独设置权限（+-）、设置角色、添加、编辑、删除成员
- 操作日志：成员操作日志记录

角色 | 菜单 
----|----
管理员 | 所有菜单权限
运营 | 首页、用户、促销、运营、内容
财务 | 首页、统计、财务
美工 | 首页、商品
客服 | 首页、商品、订单

### 前台功能

#### 商品搜索 ✔

> **综合搜索功能**

- 搜索：根据商品标题、副标题、关键字进行搜索；
- 筛选：未选择分类时聚合搜索结果，选择出现次数最多的分类，选择分类以后可以根据选择分类的筛选字段进行筛选；
- 排序：按新品、销量、价格进行排序
- 搜索返回结果：商品ID、商品图片、名称、副标题、价格、商品销量、新品、商品的参数、品牌名称、分类名称
- 接口：从数据库中查询相关数据并导入es,插入（修改）数据接口，删除数据接口
- 品牌分类筛选：根据搜索结果聚合返回品牌、分类及属性

> **商品推荐功能**

- 推荐某商品的相关商品、根据该商品的品牌（10）、分类（6）、名称（8）、关键字（2）、副标题（2）
- 根据用户一周浏览记录推荐商品，根据用户搜索记录推荐商品

> **商品热搜功能**

- 根据用户搜索记录聚合生成热搜词

> **商品搜索联想功能** ❓

- 根据用户搜索记录聚合生成热搜词

#### 购物流程

> **购物车** ✔

- 添加商品到购物车
- 购物车商品列表（商品主图、商品名称、商品数量、商品规格）
- 修改购物车中商品数量
- 购物车中商品重选规格
- 购物车中商品删除功能

> **生成确认单**

- 生成确认单信息：收货信息、商品信息、价格信息、发票信息、支付方式
- 选择收货地址：默认收货地址
- 选择优惠券及积分抵扣：展示可用优惠券和不可以优惠券
- 计算商品价格：商品合计、运费、优惠券抵扣、积分抵扣、活动优惠
- 选择支付方式：在线支付及货到付款
- 计算应付金额：合计+运费-优惠券抵扣-积分抵扣-活动优惠

> **提交订单及支付**

- 将确认单信息转化为订单
- 删除购物车中相关商品
- 添加订单到数据库并锁定库存
- 在线支付选择支付方式：支付宝、微信、银联、ApplePay
- 支付完成后修改订单状态为已支付、扣除库存

#### 会员模块（我的）✔

> **我的关注**

- 关注品牌列表：品牌logo、名称、地址、关注数量
- 取消关注功能
- 关注列表展示

> **我的收藏**

- 收藏的商品：商品主图、名称、卖点、价格、找相似
- 收藏的专题：专题主图、标题、副标题、收藏数、浏览数、评论数
- 收藏的话题：话题主图、标题、副标题、收藏数、浏览数、评论数

> **我的足迹**

- 浏览过的商品：商品主图、名称、卖点、价格、找相似
- 删除记录功能
- 浏览列表展示

> **会员登录注册**

- 登录功能：https登录
- 注册功能：用户名、密码、手机号、手机验证码
- 获取验证码：后台生成验证码，验证码绑定手机号
- 忘记密码：手机号、短信验证码、新密码
- 登出功能


