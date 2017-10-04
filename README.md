# 自己用的php规范

# php 
##类名
###大驼峰 例如 `UserOrder`
# mysql




整体架构  MSVC    m值数据层  只对单表读写数据  s业务逻辑层  v 显示层  c 控制层


数据提交    get psot ajax  
 请求 一般web页面  get  有时ajax get
      提交写入表单 一律用ajax+post  
      搜索表单get（跳转） 或者ajax+post（动态请求）
      返回 数据 不区分是否ajax get：返回html  post 返回json


cv 之间json数据约定
status  1 业务处理成功 0 业务处理失败
message 字符串  返回给v的显示信息 一般用于业务处理失败时
data   数组  列表一般用list  字段一般用field
  



一个controller 应该返回什么
true（转为空字符串） 字符串和数字   给传给response 
false null 不返回错误的输出   errjson或者errmsg
数组  json 输出
object 1.response  输出，2/其他类的实例 __toString()

解析模板是否清除以前的输出   清除不利于debug但能很好的保证系统健壮性
