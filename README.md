# Seablue框架开发标准指南

此文档是本人简易变量/语句开发标准，没有实用价值，请谨慎使用,看完请关闭务必忘记！



> #### 版本规则

version: 0.1.0.1.0

第一位 - 修改的重大api   
第二位 - 新增大量功能和组件开发   
第三位 - 修改大量功能和组件开发   
第四位 - 修复css或js内容  
第五位 - 新增文件

简介详写 

- 修改数据-u
- 新增数据-i
- 删除数据-d



> #### **html**   使用语义化更利于SEO优化

网页导航栏/引导块:  `nav `   
网页头部:  `header`    
网页内容:  `main`  
网页底部:  `footer`  
网页区域/一个面/一个功能的(主/标)题 : `section`       
网页副标题: `small`  
网页行内小文字/相同元素: `span`  
文章存放区域: `article`  
网页中额外内容: `aside`



> #### **JS 开发规则  **   

> **变量**全部为小写，**全局变量/全局常量**全部为大写. 
> **命名函数** 小驼峰命名法，**类/函数表达式** 大驼峰命名法  
> 注意:  [  ] 表示任意非符号英文单词  () 代表组合存在多个字母  ^表示开头  $表示结尾  
> ^A-Z  (a-z)   开头第一个大写其他小写 标注 a  

默认: `def`    
错误: `err`    
获取: `get`    
设置: `set`    
删除: `del`    
初始化: `init`  
方法共同存在: `public`  
返回值或者结果: `result`  
判断是否含义某个值: `has`  
判断是否为某个值: `is`  
加载某些数据: `load`

变量规则:   
   全小写，常量全大写,多单词下划线隔开    
   标签元素意义变量  $ 开头 例如: `var $body = document.body`
   实参变量: 小驼峰命名法
函数规则:  
   小驼峰命名法  
原型规则:
原型上的获取某种功能调用: `_get[a]`    
原型上的设置某种功能调用: `_set[a]`    
原型上的默认功能: `_def[a]`   
原型上的信息功能: `_in[a]`   
原型上的同步功能: `_asy[a]`  
原型上的样式功能: `_styl[a]`   
原型上的事件功能: `_e[a]`  
原型上的对象功能: `_obj[a]`   
原型上的数据类型功能: `_dat[a]`   
原型上的函数类型功能: `_fun[a]`   
原型上的错误处理功能: `_try[a]`   
原型上的隐藏功能: `_hide[a]`  
原型上的判断功能: `_is[a]`   
原型上的通用或者默认功能: `_def[a]` 

 

 

> #### **JS**    控制样式类

 

###### **临时标识类**   

语法: 功能-flag-具体元素类名    
规则:  在某个功能上临时标记个类或者选择器，让dom进行一些特殊操作

例如:

```
var isbase = $('#prompthover').hasClass('prompt-flag-is');

提示功能判断是否存在，的意思，简明扼要
```

 

 





> #### **CSS**   样式开发规则

定义:     
定位 z-index 层叠规则：

  1 表示大于文档流排列  
  2 表示大于或欲脱离一切排列  
  3 脱离文档流层叠优先  
  4 绝对顶层  
  5 外部因素    
1,2 属于文档流排列类 ， 3,4 属于功能或者独立模块， 5 最大 
默认层叠大小为1，最小或者说是背景底层设置为0 , 最大层叠数为5  
禁止使用 1~ 5 以外的数字提权，导致难以审计代码



在一个CSS功能/组件 中定义 CSS 纯类：

写法: 

```
  具体内容往下看例子1.1 
 第一种  .父类-子类   // headbar-logo  
 第二种  .父类-父类-子类   // headbar-logo-img
 第三种  .第一层父类-本层父类-该层子类  // headbar-img-title
 
 使用此方法类名修改方便，易于维护
```

CSS类规则:   
    1 使用`-` 隔开多单词字母  
    2 全部为小写
    3 一个框架性质的类、id为大驼峰命名法   
注意事项：超过2个父类使用第一层父类组合本层父类加上自身     

原因是 预处理CSS如sass/less/stylus 等等   
预处理使用多重父子嵌套会导致无法预知的错误，嵌套2层无疑最优

1.1 例如: 

```
html

<div class="headbar">
    <div class="headbar-logo">
        <div class="headbar-logo-img">
        	<img src="#" class="headbar-img-title" alt="#">  // 使用第一层父类
        </div>
    </div>
    <div class="headbar-title">
        <section>Seablue Dearmsdan</section>
        <small>Agency based Dearmsdan theme.</small>
    </div>
</div>

SCSS 语法
.headbar {
    background: $c-fff;
    .headbar-logo {
        font-weight: bolder;
    }
    .headbar-logo-img {
        font-weight: bolder;
    }
    .headbar-img-title{
        font-weight: bolder;
    }
    .headbar-title {
        font-weight: bolder;
    }
}
```







### 页面测试规则:

测试尺寸： 

 320 >  710  >  900  > 1128  >  1280









> #### **Java** 包/类名规则
