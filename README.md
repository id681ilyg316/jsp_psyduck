## 本项目实现的最终作用是基于JSP美食菜谱分享系统
## 分为1个角色
### 第1个角色为用户角色，实现了如下功能：
 - 主页
 - 发布菜谱
 - 查看我的收藏
 - 查看菜谱
 - 注册账号
 - 用户登录
## 数据库设计如下：
# 数据库设计文档

**数据库名：** psyduck

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [category](#category) |  |
| [recipe](#recipe) |  |
| [recipe_category](#recipe_category) |  |
| [recipe_step](#recipe_step) |  |
| [user](#user) | 用户表 |
| [user_collection](#user_collection) |  |
| [user_createrecipe](#user_createrecipe) |  |

**表名：** <a id="category">category</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 分类ID  |
|  2   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 分类名  |

**表名：** <a id="recipe">recipe</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 菜谱ID  |
|  2   | createDate |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  3   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  4   | coverPath |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 封面（图）  |
|  5   | info |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 介绍  |
|  6   | material |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 食材  |

**表名：** <a id="recipe_category">recipe_category</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | id  |
|  2   | recipeId |   int   | 10 |   0    |    Y     |  N   |   NULL    | 菜谱Id（外键）  |
|  3   | category |   int   | 10 |   0    |    Y     |  N   |   NULL    | 分类  |

**表名：** <a id="recipe_step">recipe_step</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | id  |
|  2   | recipeId |   int   | 10 |   0    |    Y     |  N   |   NULL    | 菜谱ID（外键）  |
|  3   | info |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 详细步骤  |
|  4   | filePath |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 步骤图地址  |

**表名：** <a id="user">user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 用户ID  |
|  2   | createDate |   date   | 10 |   0    |    N     |  N   |       | 创建时间  |
|  3   | username |   varchar   | 255 |   0    |    N     |  N   |       | 用户名  |
|  4   | password |   varchar   | 255 |   0    |    N     |  N   |       | 密码  |
|  5   | protrait |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 头像  |
|  6   | info |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 个人介绍  |

**表名：** <a id="user_collection">user_collection</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | id  |
|  2   | userId |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户id（外键）  |
|  3   | collection |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户收藏的菜谱id  |

**表名：** <a id="user_createrecipe">user_createrecipe</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | id  |
|  2   | userId |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户Id（外键）  |
|  3   | createRecipe |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户创建的菜谱  |
|  4   | username |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 创建菜谱的用户名  |

**运行不出来可以微信 javape 我的公众号：源码码头**
