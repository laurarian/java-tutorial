# 1 Ajax

## 1.1 Ajax介绍

### 1.1.1 Ajax概述

# 2 前后台分离开发

## 2.1 前后台分离开发介绍
在之前的课程中，我们介绍过，前端开发有2种方式：**前后台混合开发**和**前后台分离开发**。

前后台混合开发，顾名思义就是前台后台代码混在一起开发，如下图所示：

<img width="660" alt="image" src="https://github.com/user-attachments/assets/e100e838-e323-4696-8cce-7e834d4d8f9d">


这种开发模式有如下缺点：

- 沟通成本高：后台人员发现前端有问题，需要找前端人员修改，前端修改成功，再交给后台人员使用
- 分工不明确：后台开发人员需要开发后台代码，也需要开发部分前端代码。很难培养专业人才
- 不便管理：所有的代码都在一个工程中
- 不便维护和扩展：前端代码更新，和后台无关，但是需要整个工程包括后台一起重新打包部署。



所以我们目前基本都是采用的前后台分离开发方式，如下图所示：
<img width="585" alt="image" src="https://github.com/user-attachments/assets/fc50d8fe-7a85-4d2c-be01-62ca185a7df0">

我们将原先的工程分为前端工程和后端工程这2个工程，然后前端工程交给专业的前端人员开发，后端工程交给专业的后端人员开发。前端页面需要数据，可以通过发送异步请求，从后台工程获取。但是，我们前后台是分开来开发的，那么前端人员怎么知道后台返回数据的格式呢？后端人员开发，怎么知道前端人员需要的数据格式呢？所以针对这个问题，我们前后台统一指定一套规范！我们前后台开发人员都需要遵循这套规范开发，这就是我们的**接口文档**。接口文档有离线版和在线版本，接口文档示可以查询今天提供**资料/接口文档示例**里面的资料。那么接口文档的内容怎么来的呢？是我们后台开发者根据产品经理提供的产品原型和需求文档所撰写出来的，产品原型示例可以参考今天提供**资料/页面原型**里面的资料。

那么基于前后台分离开发的模式下，我们后台开发者开发一个功能的具体流程如何呢？如下图所示：

<img width="638" alt="image" src="https://github.com/user-attachments/assets/86706e0d-51d9-4076-b816-f8cc6475d638">

1. 需求分析：首先我们需要阅读需求文档，分析需求，理解需求。
2. 接口定义：查询接口文档中关于需求的接口的定义，包括地址，参数，响应数据类型等等
3. 前后台并行开发：各自按照接口文档进行开发，实现需求
4. 测试：前后台开发完了，各自按照接口文档进行测试
5. 前后段联调测试：前段工程请求后端工程，测试功能
   
## 2.2 YAPI
前后台分离开发中，我们前后台开发人员都需要遵循接口文档，所以接下来我们介绍一款撰写接口文档的平台。

YApi 是高效、易用、功能强大的 api 管理平台，旨在为开发、产品、测试人员提供更优雅的接口管理服务。

其官网地址：http://yapi.smart-xwork.cn/

YApi主要提供了2个功能：

- API接口管理：根据需求撰写接口，包括接口的地址，参数，响应等等信息。
- Mock服务：模拟真实接口，生成接口的模拟测试数据，用于前端的测试。

### 2.2.2 接口文档管理

接下来我们演示一下YApi是如何管理接口文档的。

首先我们登录YAPI的官网，然后使用github或者百度账号登录，没有的话去注册一个，如下图所示：

登录进去后，在个人空间中，选择项目列表->添加测试项目，效果如图所示：

<img width="637" alt="image" src="https://github.com/user-attachments/assets/7f150232-1dc7-47c6-aee6-0a0c0e41ed72">


然后点击创建的项目，进入到项目中，紧接着先添加接口的分类，如下图所示

<img width="627" alt="image" src="https://github.com/user-attachments/assets/fe3de81e-ae49-447d-b2f1-0438d5e844f7">


然后我们选择当前创建的分类，创建接口信息，如下图所示：

<img width="620" alt="image" src="https://github.com/user-attachments/assets/7e1d85aa-0088-4f40-860b-654cc3a601be">


紧接着，我们来到接口的编辑界面，对接口做生层次的定制，例如：接口的参数，接口的返回值等等，效果图下图所示：

<img width="620" alt="image" src="https://github.com/user-attachments/assets/6c610a7c-aa99-431e-ac76-47b73b88ac7b">


添加接口的请求参数，如下图所示：

<img width="626" alt="image" src="https://github.com/user-attachments/assets/cb10612e-3123-4fac-aebc-0794eba2941c">


添加接口的返回值，如下图所示：

<img width="627" alt="image" src="https://github.com/user-attachments/assets/a0cb9184-b6fe-4496-810b-4884bc481b9f">


然后保存上述设置，紧接着我们可以来到接口的预览界面，查询接口的信息，其效果如下图所示：篇幅有限，只截取部分

<img width="622" alt="image" src="https://github.com/user-attachments/assets/0634f40b-d220-497d-92bc-402e009e1e53">


最后，我们还可以设置接口的mock信息，

<img width="623" alt="image" src="https://github.com/user-attachments/assets/3af467a8-4ff9-47c5-8c07-18e7cfad1a4f">


来到接口的Mock设置窗口，如下图所示：

<img width="621" alt="image" src="https://github.com/user-attachments/assets/02d7b1a2-0017-4767-8e87-2087e4259943">


紧接着我们来到接口的预览界面，直接点击Mock地址，如下图所示：

<img width="627" alt="image" src="https://github.com/user-attachments/assets/ffae3ee1-1b27-4962-bc61-0a6ccd090ffb">


我们发现浏览器直接打开，并返回如下数据：

<img width="627" alt="image" src="https://github.com/user-attachments/assets/1e551292-4c49-4c6b-a0e5-0b8f6d526b44">


如上步骤就是YAPI接口平台中对于接口的配置步骤。

# 3 前端工程化

## 3.1 前端工程化介绍

我们目前的前端开发中，当我们需要使用一些资源时，例如：vue.js，和axios.js文件，都是直接再工程中导入的，如下图所示：

<img width="631" alt="image" src="https://github.com/user-attachments/assets/f1afbdbf-d6e8-426d-b68f-9f2c0cbdfabf">


但是上述开发模式存在如下问题：

- 每次开发都是从零开始，比较麻烦
- 多个页面中的组件共用性不好
- js、图片等资源没有规范化的存储目录，没有统一的标准，不方便维护



所以现在企业开发中更加讲究前端工程化方式的开发，主要包括如下4个特点

- 模块化：将js和css等，做成一个个可复用模块
- 组件化：我们将UI组件，css样式，js行为封装成一个个的组件，便于管理
- 规范化：我们提供一套标准的规范的目录接口和编码规范，所有开发人员遵循这套规范
- 自动化：项目的构建，测试，部署全部都是自动完成

所以对于前端工程化，说白了，就是在企业级的前端项目开发中，把前端开发所需要的工具、技术、流程、经验进行规范化和标准化。从而提升开发效率，降低开发难度等等。接下来我们就需要学习vue的官方提供的脚手架帮我们完成前端的工程化。


## 3.2 前端工程化入门

### 3.2.1 环境准备

我们的前端工程化是通过vue官方提供的脚手架Vue-cli来完成的，用于快速的生成一个Vue的项目模板。Vue-cli主要提供了如下功能：

- 统一的目录结构
- 本地调试
- 热部署
- 单元测试
- 集成打包上线

我们需要运行Vue-cli，需要依赖NodeJS，NodeJS是前端工程化依赖的环境。所以我们需要先安装NodeJS，然后才能安装Vue-cli

- NodeJS安装和Vue-cli安装

  详细安装步骤，请参考**资料/NodeJS安装文档/NodeJS安装文档.md**文件

<img width="592" alt="image" src="https://github.com/user-attachments/assets/b43282c7-e105-4a42-ae7e-ed3071bb901c">

### 3.2.2 Vue项目简介

环境准备好了，接下来我们需要通过Vue-cli创建一个vue项目，然后再学习一下vue项目的目录结构。Vue-cli提供了如下2种方式创建vue项目:

- 命令行：直接通过命令行方式创建vue项目

  ~~~
  vue create vue-project01
  ~~~

  

- 图形化界面：通过命令先进入到图形化界面，然后再进行vue工程的创建

  ~~~
  vue ui
  ~~~

  图形化界面如下：

<img width="589" alt="image" src="https://github.com/user-attachments/assets/a5f5370d-72fb-49bc-9739-b9675219dedb">



#### 3.2.2.1 创建vue项目

此处我们通过第二种图形化界面方式给大家演示。

首先，我们再桌面创建vue文件夹，然后双击进入文件夹，来到地址目录，输入cmd，然后进入到vue文件夹的cmd窗口界面，如下图所示：

![1669294790640](assets/1669294790640.png)

然后进入如下界面：

![1669294846601](assets/1669294846601.png)

然后再当前目录下，直接输入命令`vue ui`进入到vue的图形化界面，如下图所示：

![1669294939067](assets/1669294939067.png) 

然后我门选择创建按钮，在vue文件夹下创建项目，如下图所示：

![1669295020228](assets/1669295020228.png)

然后来到如下界面，进行vue项目的创建

![1669301661722](assets/1669301661722.png)

然后预设模板选择手动，如下图所示：

 ![1669301737491](assets/1669301737491.png) 

然后再功能页面开启路由功能，如下图所示：

![1669301859936](assets/1669301859936.png) 

然后再配置页面选择语言版本和语法检查规范，如下图所示：

![1669301965095](assets/1669301965095.png) 

然后创建项目，进入如下界面：

![1669302091090](assets/1669302091090.png)

最后我们只需要等待片刻，即可进入到创建创建成功的界面，如下图所示：

![1669302171975](assets/1669302171975.png) 

 到此，vue项目创建结束



#### 3.2.2.2 vue项目目录结构介绍

我们通过VS Code打开之前创建的vue文件夹，打开之后，呈现如下图所示页面：

![1669302718419](assets/1669302718419.png)

vue项目的标准目录结构以及目录对应的解释如下图所示:

![1669302973198](assets/1669302973198.png)

其中我们平时开发代码就是在**src目录**下



#### 3.2.2.3 运行vue项目

那么vue项目开发好了，我们应该怎么运行vue项目呢？主要提供了2种方式

- 第一种方式：通过VS Code提供的图形化界面 ，如下图所示：（注意：NPM脚本窗口默认不显示，可以参考本节的最后调试出来）

  ![1669303687468](assets/1669303687468.png)

  点击之后，我们等待片刻，即可运行，在终端界面中，我们发现项目是运行在本地服务的8080端口，我们直接通过浏览器打开地址

  ![1669303846100](assets/1669303846100.png) 

  最终浏览器打开后，呈现如下界面，表示项目运行成功

  ![1669304009602](assets/1669304009602.png)

  其实此时访问的是 **src/App.vue**这个根组件，此时我们打开这个组件，修改代码：添加内容Vue

  ![1669304267724](assets/1669304267724.png)

  只要我们保存更新的代码，我们直接打开浏览器，不需要做任何刷新，发现页面呈现内容发生了变化，如下图所示：

  ![1669304385826](assets/1669304385826.png)

  这就是我们vue项目的热更新功能 

  对于8080端口，经常被占用，所以我们可以去修改默认的8080端口。我们修改vue.config.js文件的内容，添加如下代码：

  ~~~json
  devServer:{
      port:7000
  }
  ~~~

  如下图所示，然后我们关闭服务器，并且重新启动，

  ![1669305444633](assets/1669305444633.png)

​       重新启动如下图所示：

​	![1669305570022](assets/1669305570022.png) 

​	端口更改成功，可以通过浏览器访问7000端口来访问我们之前的项目

- 第二种方式：命令行方式

  直接基于cmd命令窗口，在vue目录下，执行输入命令`npm run serve`即可，如下图所示：

  ![1669304694076](assets/1669304694076.png) 



补充：NPM脚本窗口调试出来

第一步：通过**设置/用户设置/扩展/MPM**更改NPM默认配置，如下图所示

![1669304930336](assets/1669304930336.png)

然后重启VS Code，并且**双击打开package.json文件**，然后点击**资源管理器处的3个小点**，**勾选npm脚本选项**，如图所示

![1669305068434](assets/1669305068434.png) 

然后就能都显示NPM脚本小窗口了。



### 3.2.3 Vue项目开发流程

那么我们访问的首页是index.html，但是我们找到public/index.html文件，打开之后发现，里面没有什么代码，但是能够呈现内容丰富的首页：如下图所示：

![1669308098856](assets/1669308098856.png) 

我们自习观察发现，index.html的代码很简洁，但是浏览器所呈现的index.html内容却很丰富，代码和内容不匹配，所以vue是如何做到的呢？接下来我们学习一下vue项目的开发流程。

对于vue项目，index.html文件默认是引入了入口函数main.js文件，我们找到**src/main.js**文件，其代码如下：

~~~js
import Vue from 'vue'
import App from './App.vue'
import router from './router'

Vue.config.productionTip = false

new Vue({
  router,
  render: h => h(App)
}).$mount('#app')

~~~

上述代码中，包括如下几个关键点：

- import: 导入指定文件，并且重新起名。例如上述代码`import App from './App.vue'`导入当前目录下得App.vue并且起名为App
- new Vue(): 创建vue对象
- $mount('#app');将vue对象创建的dom对象挂在到id=app的这个标签区域中，作用和之前学习的vue对象的le属性一致。
- router:  路由，详细在后面的小节讲解
- render: 主要使用视图的渲染的。



来到**public/index.html**中，我们**删除div的id=app属性**，打开浏览器，发现之前访问的首页一片空白，如下图所示，这样就证明了，我们main.js中通过代码挂在到index.html的id=app的标签区域的。



此时我们知道了vue创建的dom对象挂在到id=app的标签区域，但是我们还是没有解决最开始的问题：首页内容如何呈现的？这就涉及到render中的App了，如下图所示：

![1669313364004](assets/1669313364004.png) 

那么这个App对象怎么回事呢，我们打开App.vue,注意的是.vue结尾的都是vue组件。而vue的组件文件包含3个部分：

- template: 模板部分，主要是HTML代码，用来展示页面主体结构的
- script: js代码区域，主要是通过js代码来控制模板的数据来源和行为的
- style: css样式部分，主要通过css样式控制模板的页面效果得

如下图所示就是一个vue组件的小案例：

![1669313699186](assets/1669313699186.png)



此时我们可以打开App.vue，观察App.vue的代码，其中可以发现，App.vue组件的template部分内容，和我们浏览器访问的首页内容是一致的，如下图所示：

![1669313894258](assets/1669313894258.png)

接下来我们可以简化模板部分内容，添加script部分的数据模型，删除css样式，完整代码如下：

~~~html
<template>
  <div id="app">
    {{message}}
  </div>
</template>

<script>
export default {
  data(){
    return {
      "message":"hello world"
    }
  }
}
</script>
<style>

</style>
~~~



保存直接，回到浏览器，我们发现首页展示效果发生了变化，如下图所示：

![1669314115641](assets/1669314115641.png)



# 4 Vue组件库Element

## 4.1 Element介绍

不知道同学们还否记得我们之前讲解的前端开发模式MVVM，我们之前学习的vue是侧重于VM开发的，主要用于数据绑定到视图的，那么接下来我们学习的ElementUI就是一款侧重于V开发的前端框架，主要用于开发美观的页面的。

Element：是饿了么公司前端开发团队提供的一套基于 Vue 的网站组件库，用于快速构建网页。

Element 提供了很多组件（组成网页的部件）供我们使用。例如 超链接、按钮、图片、表格等等。如下图所示就是我们开发的页面和ElementUI提供的效果对比：可以发现ElementUI提供的各式各样好看的按钮

![1669357961971](assets/1669357961971.png) 

ElementUI的学习方式和我们之前的学习方式不太一样，对于ElementUI，我们作为一个后台开发者，只需要**学会如何从ElementUI的官网拷贝组件到我们自己的页面中，并且做一些修改即可**。其官网地址：https://element.eleme.cn/#/zh-CN，我们主要学习的是ElementUI中提供的常用组件，至于其他组件同学们可以通过我们这几个组件的学习掌握到ElementUI的学习技巧，然后课后自行学习。



## 4.2 快速入门

首先我们要掌握ElementUI的快速入门，接下来同学们就一起跟着步骤来操作一下。

首先，我们先要安装ElementUI的组件库，打开VS Code，停止之前的项目，然后在命令行输入如下命令：

~~~
npm install element-ui@2.15.3 
~~~

具体操作如下图所示：

![1669358653297](assets/1669358653297.png) 

然后我们需要在main.js这个入口js文件中引入ElementUI的组件库，其代码如下：

~~~js
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';

Vue.use(ElementUI);
~~~

具体操作如图所示：

![1669358935188](assets/1669358935188.png)

然后我们需要按照vue项目的开发规范，在**src/views**目录下创建一个vue组件文件，注意组件名称后缀是.vue，并且在组件文件中编写之前介绍过的基本组件语法，代码如下：

~~~html
<template>

</template>

<script>
export default {

}
</script>

<style>

</style>
~~~

具体操作如图所示：

![1669359450896](assets/1669359450896.png) 

最后我们只需要去ElementUI的官网，找到组件库，然后找到按钮组件，抄写代码即可，具体操作如下图所示：

![1669359839574](assets/1669359839574.png)

然后找到按钮的代码，如下图所示：

![1669359904272](assets/1669359904272.png) 



紧接着我们复制组件代码到我们的vue组件文件中，操作如下图所示：

![1669360120385](assets/1669360120385.png)

最后，我们需要在默认访问的根组件**src/App.vue**中引入我们自定义的组件，具体操作步骤如下：

![1669360320983](assets/1669360320983.png) 

然后App.vue组件中的具体代码如下，**代码是我们通过上述步骤引入element-view组件时自动生成的**。

~~~html
<template>
  <div id="app">
    <!-- {{message}} -->
    <element-view></element-view>
  </div>
</template>

<script>
import ElementView from './views/Element/ElementView.vue'
export default {
  components: { ElementView },
  data(){
    return {
      "message":"hello world"
    }
  }
}
</script>
<style>

</style>

~~~

然后运行我们的vue项目，浏览器直接访问之前的7000端口，展示效果如下图所示：

![1669360502407](assets/1669360502407.png)

到此，我们ElementUI的入门程序编写成功



