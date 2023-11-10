# SpringCloud_Note
# SpringCloud常用组件应用及原理:see_no_evil:

## 目录
<a name="3060-1621846615933"></a><a name="cngx-1699584333005"></a>[实用篇](#gbe3-1664904091315)

<a name="lcjo-1699584333007"></a>[一.微服务拆分原则](#llbd-1652109081695)

<a name="dbds-1699584333009"></a>[-单一职责](#owbl-1699482835773)

<a name="rs70-1699584333011"></a>[-暴露接口](#thol-1699482860563)

<a name="g80r-1699584333013"></a>[-独立数据库](#txfn-1699482878280)

<a name="pdl8-1699584333015"></a>[二.微服务调用方式](#0sue-1652108091218)

<a name="cacb-1699584333017"></a>[Feign](#xqiw-1653354686185)

<a name="5gvj-1699584333019"></a>[GRPC](#dtxs-1653355097345)

<a name="yktx-1699584333021"></a>[三、Eureka注册中心](#mrfv-1653492996885)

<a name="u4c1-1699584333023"></a>[-搭建EurakaServer](#kukd-1699482942972)

<a name="bcpf-1699584333025"></a>[-服务注册](#lnru-1699482948466)

<a name="l8qt-1699584333027"></a>[-服务发现](#jnwk-1699482952257)

<a name="9x4s-1699584333030"></a>[nacos](#hsv3-1663868992842)

<a name="bbsv-1699584333032"></a>[-模型(服务-集群-实例)](#xsar-1699483263729)

<a name="qd9z-1699584333034"></a>[-负载均衡策略(优先本地再其他集群）](#lbm1-1699483268112)

<a name="ee9u-1699584333036"></a>[-实例权重控制(配置0~1)](#xc60-1699483339060)

<a name="oap4-1699584333038"></a>[-配置管理](#1trg-1699483392079)

<a name="ty2k-1699584333040"></a>[1.拉取顺序](#ooyn-1699483438704)

<a name="fgwx-1699584333042"></a>[2.热更新](#d0dx-1699483445866)

<a name="v8cr-1699584333044"></a>[3.环境共享](#bsav-1699483462085)

<a name="dosh-1699584333046"></a>[网关](#gro1-1654615618203)

<a name="cscz-1699584333048"></a>[-作用(认证鉴权限流）](#eiai-1699483560749)

<a name="hc5x-1699584333050"></a>[-搭建步骤(路由配置)](#1qnl-1699483587226)

<a name="yqae-1699584333052"></a>[-过滤器(执行顺序)](#d0ae-1699483601450)

<a name="xend-1699584333054"></a>[-网关跨域(cors配置)](#rfrd-1699483683921)

<a name="b7tu-1699584333056"></a>[MQ 消息队列](#b5nt-1664267671060)

<a name="po7i-1699584333058"></a>[-异步优(低耦合高吞吐）](#fvse-1699483815224)

<a name="cljl-1699584333060"></a>[-rabbitMQ(消息发送接收）](#tu7v-1699483831383)

<a name="wx1u-1699584333062"></a>[springAMQP（mq模板）](#zjsf-1664267818209)

<a name="9pe6-1699584333064"></a>[-接收消息](#juhf-1699483941506)

<a name="ucxs-1699584333066"></a>[-workQueue模型](#xma3-1699483955142)

<a name="84q3-1699584333068"></a>[-发布订阅模型](#yqmi-1699483964152)

<a name="mckf-1699584333070"></a>[-FanoutExchange](#w9be-1699483984879)

<a name="4ldz-1699584333072"></a>[-DirectExchange](#bdol-1699483998094)

<a name="nmub-1699584333074"></a>[-TopicExchange](#plzo-1699484006007)

<a name="d8az-1699584333076"></a>[-消息转换器](#2bps-1699484016082)

<a name="i1nm-1699584333078"></a>[elasticsearch](#cumd-1664453094415)

<a name="ldat-1699584333080"></a>[-作用（搜索日志统计分析）](#bjw6-1699484040955)

<a name="qzix-1699584333082"></a>[-倒排索引](#zu2v-1699484079593)

<a name="ehmh-1699584333084"></a>[-ES基本概念](#p9bz-1699484104132)

<a name="jj4g-1699584333086"></a>[-操作索引库-mapping属性](#kw2u-1699484111406)

<a name="ld0k-1699584333088"></a>[-DSL查询语法](#ydit-1699484174907)

<a name="j84p-1699584333090"></a>[-RestClient查询文档](#xwmx-1699484175219)

<a name="2eqy-1699584333092"></a>[-深入分布式搜索引擎ElasticSearch](#urie-1699484175454)

<a name="zpcr-1699584333094"></a>[-集群](#zjrt-1699484175729)

<a name="ywos-1699584333096"></a>[高级篇](#rnrl-1664904101009)

<a name="d95c-1699584333098"></a>[Sentinel（or Hystrix）](#sxsr-1664910145443)

<a name="efdf-1699584333100"></a>[-限流(解决服务雪崩）](#oolh-1699484343150)

<a name="bo91-1699584333102"></a>[-限流规则](#prep-1699581264466)

<a name="qj0i-1699584333104"></a>[-流控模式（直接,关联,链路）](#hpmj-1699581403947)

<a name="7k4g-1699584333106"></a>[-流控效果（快速失败,等待,预热）](#c86l-1699581448479)

<a name="2xxj-1699584333108"></a>[-隔离（信号量,线程池）](#xxzz-1699582196289)

<a name="snjv-1699584333110"></a>[-熔断降级（超阈值拦截）](#pmss-1699583278371)

<a name="sl7k-1699584333112"></a>[-授权及规则持久化](#h6fq-1699583340714)

<a name="jyan-1699584333114"></a>[分布式事务](#u0zn-1664910153126)

<a name="luck-1699584333116"></a>[-CAP定理（只可同时实现其二）](#fkn4-1699583467105)

<a name="lj1b-1699584333118"></a>[-Base理论（基本可用,最终一致性）](#cxea-1699583499418)

<a name="y99y-1699584333121"></a>[-Seata(xa,at,tcc,saga)](#bodx-1699583555792)

<a name="8wqc-1699584333123"></a>[Redis](#krsw-1665245268203)

<a name="ymi7-1699584333125"></a>[持久化](#eegj-1665245288453)

<a name="xiws-1699584333127"></a>[RDB--记录数据](#5kee-1665249623480)

<a name="ahs1-1699584333129"></a>[AOF--记录指令](#errt-1665247506638)

<a name="vkkm-1699584333131"></a>[Redis主从](#sedi-1665249464425)

<a name="0g4t-1699584333133"></a>[搭建主从](#zqmb-1665258900495)

<a name="6rn0-1699584333136"></a>[  数据同步原理(增量,全量)](#q5rb-1665257395581)

<a name="1n2n-1699584333138"></a>[Redis哨兵(监控,故障转移,通知)](#ljys-1665259387699)

<a name="4pre-1699584333140"></a>[Redis分片集群(一般仅大厂有)](#dmud-1665260129911)

<a name="phz6-1699584333142"></a>[分片集群结构](#zz0t-1665312911874)

<a name="9ghz-1699584333144"></a>[散列插槽](#kikk-1665310964195)

<a name="cfdm-1699584333146"></a>[集群伸缩](#1jjc-1665312946913)

<a name="sxn8-1699584333148"></a>[故障转移](#pzdy-1665312988481)

<a name="bxgv-1699584333150"></a>[RedisTemplate访问分片集群](#q7es-1665341747299)

<a name="45bt-1699584333152"></a>[多级缓存(客户端,nginx,redis,服务进程,数据库)](#fl8s-1665341859929)

<a name="zmtq-1699584333154"></a>[MQ常见问题及消息可靠性](#eahb-1665383780873)

<a name="ug04-1699584333156"></a>[K8s](#yap8-1665384333047)

<a name="mdgd-1699584333158"></a>[Docker](#sq2s-1665385586877)

<a name="ovvw-1699584333160"></a>[Docker架构](#gwea-1665424988829)

<a name="v1qb-1699584333162"></a>[docker安装及命令](#6lfr-1665385574632)

<a name="lqes-1699584333164"></a>[镜像命令](#ttrd-1665476783436)

<a name="atfd-1699584333166"></a>[容器命令](#iqdv-1665476805658)

<a name="dyx0-1699584333168"></a>[数据卷命令](#ump6-1665476890868)

<a name="h56t-1699584333171"></a>[自定义镜像](#kkap-1665500054290)

<a name="dd4o-1699584333173"></a>[Compose](#xkql-1665500087777)

<a name="ybgw-1699584333175"></a>[K8S](#q89l-1665764307550)

<a name="mqec-1699584333177"></a>[私有网络vpc](#suxw-1665764770483)

<a name="hc01-1699584333179"></a>[基础概念](#dcnf-1652229405406)

<a name="c1tx-1699584333181"></a>[kubernetes特性](#qmth-1665917783364)

<a name="opj8-1699584333183"></a>[组件架构](#wqdy-1665917368337)

<a name="lzar-1699584333185"></a>[k8s集群搭建](#qsg5-1665932328002)

<a name="o5wu-1699584333187"></a>[核心实战](#rdys-1666457573542)

<a name="15qh-1699584333189"></a>[使用depolyment部署应用](#6lhj-1666457573723)

<a name="gwzt-1699584333191"></a>[Deployment](#uolg-1666537835973)

<a name="1wse-1699584333193"></a>[工作负载 扩缩容](#tmur-1666537880419)

<a name="rcj7-1699584333195"></a>[自愈&故障转移](#azit-1666537966300)

<a name="6xjq-1699584333197"></a>[滚动更新](#a0cx-1666537993719)

<a name="k2d4-1699584333199"></a>[小结](#j8aa-1666538012950)

<a name="cssl-1699584333201"></a>[-Deployment（无状态应用部署）](#3yiv-1699584183808)

<a name="ernk-1699584333203"></a>[-StatefulSet （有状态-登录,购物车,会话）](#umcd-1699584185052)

<a name="dyd4-1699584333205"></a>[-DaemonSet（守护型）](#dmhp-1699584186685)

<a name="juz7-1699584333207"></a>[-Job/CronJob（定时任务型）](#a5t8-1699584187412)

<a name="8uhg-1699584333209"></a>[服务网络Service](#bsl0-1666518658388)

<a name="oqga-1699584333211"></a>[Service：Pod的服务发现与负载均衡](#tw7p-1666538089240)

<a name="hcss-1699584333213"></a>[Ingress统一网关](#bkbr-1666538096293)

<a name="mivi-1699584333215"></a>[存储抽象](#rn2j-1666537720657)

<a name="f19t-1699584333217"></a>[存储层NFS](#xxrj-1666538261122)

<a name="dvq1-1699584333219"></a>[Deployment使用NFS进行挂载](#it4m-1666537737863)

<a name="i27u-1699584333221"></a>[PV与PVC](#co0j-1666537738457)

<a name="tea5-1699584333223"></a>[ConifgMap抽取配置（挂载配置）](#6uyw-1666539135553)

<a name="t0e3-1699584333225"></a>[Secret场景实例](#jznb-1666539673078)

<a name="wjwj-1699584333227"></a>[KubeSphere](#ynvn-1666539781306)

<a name="lo62-1699584333229"></a>[平台安装](#2cyh-1666621353339)

<a name="ebra-1699584333231"></a>[Linux单节点部署KubeSphere](#p1fm-1666540995714)

<a name="atlx-1699584333233"></a>[应用部署实战](#ergo-1666540952093)



![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.001.png)

<a name="c0ka-1699482312429"></a><a name="tdwl-1664904091311"></a><a name="gbe3-1664904091315"></a>**实用篇**

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.002.png)

<a name="cv4r-1652109084031"></a><a name="zxff-1652109081396"></a>**SpringCloudAlibaba 可适配另外两种技术栈。（首选Alibaba）**

<a name="llbd-1652109081695"></a>**一.微服务拆分原则**

<a name="owbl-1699482835773"></a>**-单一职责**

<a name="thol-1699482860563"></a>**-暴露接口**

<a name="txfn-1699482878280"></a>**-独立数据库**

<a name="fwza-1652106701311"></a>1.微服务需要根据业务模块拆分，做到单一职责，不要重复开发相同业务。（订单查订单，用户查用户）

<a name="fp9n-1652106750578"></a>2.微服务可以将业务暴露为接口，供其他微服务使用

<a name="e7ba-1652106810255"></a>3.不同的服务应该有自己独立的数据库。

<a name="129k-1652108089852"></a><a name="0sue-1652108091218"></a>**二.微服务调用方式**

<a name="2xcv-1652108117630"></a>1.基于RestTemplate发起http请求实现远程调用（IOC 注册RestTemplate Bean）

<a name="cuhp-1652108168005"></a>2.http请求做远程调用是与语言无关的调用，只要知道对方的ip、端口、接口路径、请求参数即可。

<a name="xqiw-1653354686185"></a>**Feign**

高级用法

@FeignClient(

`    `value = "service-provider",

`    `fallback = IUserClientFallback.class, //配置fallback类，实现当前的接口：

`    `//Feign的调用有限制响应时间，若在限定的时间内没收到回复的话，会回调调用fallback实现类的接口对应实现方法；

`    `configuration = OAuth2FeignConfig.class //Feign客户端指定配置类，该配置类需要添加@Configuration注解

)

1\.引入feign依赖

2\..消费端开启feign客户端

@SpringBootApplication

@EnableFeignClients// 开启Feign客户端

public class MircoRouteApplication {

`    `public static void main(String[] args) {

`        `SpringApplication.run(MircoRouteApplication.class, args);

`    `}

}

3\.第三步：在消费者服务中，添加Feign的接口

// 标注该类是一个feign接口，value指定生产者的服务（生产者就是实现该接口方法的服务）

@FeignClient(value = "service-provider")

@Component

public interface UserClient {

`    `@GetMapping("/user/{id}") 

`    `User queryById(@PathVariable("id") Long id);

}

4\.在生产者服务中，创建Controller，编写对应的接口

@RestController

public class FeignController{



`    `@Autowired

`    `private xxxService xxxSercice;



`    `@GetMapping("/user/{id}")

`    `User queryById(@PathVariable("id") Long id){

...具体实现逻辑...

`    `}

}

5\.在消费者端调用feign方法

public class Test{

`    `@Resource

`    `private UserClient userClient;



`    `public void test(){

`        `// 这里实质上是调用生产者的接口

`        `User user = userClient.queryById(xxxx);

`    `}

}

Feign跟RestTemplate的区别

`   `1.请求方式不一样

`        `RestTemplate需要每个请求都拼接url+参数+类文件，灵活性高但是消息封装臃肿。

`        `feign可以伪装成类似SpringMVC的controller一样，将rest的请求进行隐藏，不用再自己拼接url和参数，可以便捷优雅地调用HTTP API。

`   `2. 底层实现方式不一样

`        `RestTemplate在拼接url的时候，可以直接指定ip地址+端口号，不需要经过服务注册中心就可以直接请求接口；也可以指定服务名，

`        `请求先到服务注册中心（如nacos）获取对应服务的ip地址+端口号，

`        `然后经过HTTP转发请求到对应的服务接口（注意：这时候的restTemplate需要添加@LoadBalanced注解，进行负载均衡）。

`        `Feign的底层实现是动态代理，如果对某个接口进行了@FeignClient注解的声明，Feign就会针对这个接口创建一个动态代理的对象，

`        `在调用这个接口的时候，其实就是调用这个接口的代理对象，代理对象根据@FeignClient注解中name的值在服务注册中心找到对应的服务，

`        `然后再根据@RequestMapping等其他注解的映射路径构造出请求的地址，针对这个地址，再从本地实现HTTP的远程调用。



http客户端 feign-client抽取成公共jar的最佳实践

不同包的FeignClient的导入有两种方式:

不同包的FeignClient的导入有两种方式：

在@EnableFeignClients注解中添加basePackages，指定

在@EnableFeignClients注解中添加Base Packages，指定

FeignClient所在的包

FeignClient所在的包

在@EnableFeignclients注解中添加clients，指定具体

在@EnableFeignclient注解中添加Clients，指定具体

Feignclient的字节码

Feignclient的字节码

<a name="u0qk-1653355097344"></a>****                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     

<a name="dtxs-1653355097345"></a>**GRPC**

GRPC文件生成----？类似swagger 生成本地的依赖。custom本地发布，depoly远程发布

protobuf:compile

protobuf:compile-custom

<a name="diru-1653548408293"></a>parent-pom 引入需要更新,子模块依赖的版本号可能需要更新

<a name="mrfv-1653492996885"></a>**三、Eureka注册中心**

<a name="kukd-1699482942972"></a>**-搭建EurakaServer**

<a name="lnru-1699482948466"></a>**-服务注册**

<a name="jnwk-1699482952257"></a>**-服务发现**

1\.搭建EurakaServer

`      `引入euraka-server依赖  -父pom管理版本号

`      `添加@EnableEurekaServer注解

`      `在application.yml中配置ereka地址

2\.服务注册

`    `引入eureka-client依赖                -- 心跳机制 每30秒发送一次检查health

`    `在applicaiton.yml中配置eureka地址  -- 多实例copy configration VM中设置不同端口号覆盖yml端口

3\.服务发现

`    `引入euraka-client 依赖

`    `在yml中配置eurekadi地址

`    `给resteTemplate添加@LoadBalanced注解  -- Ribbon 实现，IRule默认 RoundChoose 轮询负载均衡

<a name="ezip-1653493112957"></a>    用服务提供者的服务名称远程调用      --根据服务名拉取服务列表

<a name="hsv3-1663868992842"></a>**nacos**

<a name="xsar-1699483263729"></a>**-模型(服务-集群-实例)**

<a name="lbm1-1699483268112"></a>**-负载均衡策略(优先本地再其他集群）**

<a name="xc60-1699483339060"></a>**-实例权重控制(配置0~1)**

<a name="1trg-1699483392079"></a>**-配置管理**

<a name="ooyn-1699483438704"></a>**1.拉取顺序**

<a name="d0dx-1699483445866"></a>**2.热更新**

<a name="bsav-1699483462085"></a>**3.环境共享**

1\. Nacos服务分级存储模型

一级是服务，例如userservice

二级是集群，例如杭州或上海

三级是实例，例如杭州机房的某台部署了userservice的服务器

2．如何设置实例的集群属性

修改application.yml文件，添加

spring.cloud.nacos.discovery.cluster-name属性即可

2\. NacosRule负载均衡策略

优先选择同集群服务实例列表

本地集群找不到提供者，才去其它集群寻找，并且会报警告

确定了可用实例列表后，再采用随机负载均衡挑选实例

3．实例的权重控制

Nacos控制台可以设置实例的权重值，0~1之间

同集群内的多个实例，权重越高被访问的频率越高

权重设置为0则完全不会被访问

------- Nacos环境隔离

namespace用来做环境隔离

每个namespace都有唯一id③不同namespace下的服务不可见

-------微服务配置拉取

将配置交给Nacos管理的步骤

.在Nacos中添加配置文件

.在微服务中引入nacos的config依赖

.在微服务中添加bootstrap.yml，配置nacos地址、当前环境、服务名称、文件后缀名。这些决定了程序启动时去nacos读取哪个文件

-------配置热更新

Nacos配置更改后，微服务可以实现热更新，方式:

.通过@Value注解注入，结合@RefreshScope来刷新

.通过@configurationProperties注入，自动刷新

注意事项:

·不是所有的配置都适合放到配置中心，维护起来比较麻烦

·建议将一些关键参数，需要运行时调整的参数放到nacos配置中心，一般都是自定义配置

------多环境配置共享

微服务会从nacos读取的配置文件:

·[服务名]-[spring.profile.active].yaml

，环境配置[服务名].yaml，默认配置，多环境共享

优先级:

·[服务名]-[环境].yaml >[服务名].yaml>本地配置

=============配置管理==================

`  `集群搭建步骤:

`    `搭建MySQL集群并初始化数据库表

`    `下载解压nacos

`    `③修改集群配置（节点信息)、数据库配置 

`    `分别启动多个nacos节点

<a name="vrun-1663869031421"></a>    nginx反向代理

<a name="gro1-1654615618203"></a>**网关**

<a name="eiai-1699483560749"></a>**-作用(认证鉴权限流）**

<a name="1qnl-1699483587226"></a>**-搭建步骤(路由配置)**

<a name="d0ae-1699483601450"></a>**-过滤器(执行顺序)**

<a name="rfrd-1699483683921"></a>**-网关跨域(cors配置)**

----网关的作用：

`    `对用户请求做身份认证、权限校验

`    `将用户请求路由到微服务，并实现负载均衡

`    `对用户请求做限流

----统一网关Gateway-搭建网关服务

网关搭建步骤:

网关搭建步骤：

1\.创建项目，引入nacos服务发现和gateway依赖

2．配置application.yml，包括服务基本信息、nacos地址、路由

路由配置包括：

1\.路由id:路由的唯一标示

2\.路由目标(uri):路由的目标地址，http代表固定地址，lb代表根

据服务名负载均衡

3\.路由断言( predicates) :判断路由的规则， 断言工厂

4\.路由过滤器( filters) :对请求或响应做处理  过滤器工厂

过滤器- defalutFilter  GlobalFilter(自己写代码实现，如身份验证) 

----全局过滤器的作用是什么?


对所有路由都生效的过滤器，并且可以自定义处理逻辑实现全局过滤器的步骤

步骤：

实现GlobalFilter接口


添加@Order注解或实现Ordered接口

编写处理逻辑

\-

------过滤器执行顺序

路由过滤器、defaultFilter、全局过滤器的执行顺序?

Order值越小，优先级越高

当order值一样时，顺序是defaultFilter最先，然后是局部的路由过滤器

，最后是全局过滤器


------网关的跨域问题处理  

域名不同、端口不同，浏览器禁止跨域ajax请求。

解决方案：cors

网关yml配置。

<a name="e6x7-1654615652699"></a>                                                                                         

<a name="b5nt-1664267671060"></a>**MQ 消息队列**

<a name="fvse-1699483815224"></a>**-异步优(低耦合高吞吐）**

<a name="tu7v-1699483831383"></a>**-rabbitMQ(消息发送接收）**

同步调用的优点:

·时效性较强，可以立即得到结果

同步调用的问题:

·耦合度高

·性能和吞吐能力下降

·有额外的资源消耗

·有级联失败问题

异步通信的优点:

·耦合度低

·吞吐量提升。故障隔离·流量削峰

异步通信的缺点:

·依赖于Broker的可靠性、安全性、吞吐能力

·架构复杂了，业务没有明显的流程线，不好追踪管理

------rabbitMQ入门

RabbitMQ中的几个概念:

` `channel:操作MQ的工具

· exchange:路由消息到队列中

· queue:缓存消息

. virtual host:虚拟主机，是对queue、exchange等资源的逻辑分组

基本消息队列的消息发送流程:

1．建立connection

2．创建channel

3．利用channel声明队列

4．利用channel向队列发送消息

基本消息队列的消息接收流程:

1．建立connection

2．创建channel

3．利用channel声明队列

4．定义consumer的消费行为handleDelivery()

<a name="lcmu-1664267818208"></a>5.利用channel将消费者与队列绑定

<a name="zjsf-1664267818209"></a>**springAMQP（mq模板）**

<a name="juhf-1699483941506"></a>**-接收消息**

<a name="xma3-1699483955142"></a>**-workQueue模型**

<a name="yqmi-1699483964152"></a>**-发布订阅模型**

<a name="w9be-1699483984879"></a>**-FanoutExchange**

<a name="bdol-1699483998094"></a>**-DirectExchange**

<a name="plzo-1699484006007"></a>**-TopicExchange**

<a name="2bps-1699484016082"></a>**-消息转换器**

springAMQP如何接收消息?

·引入amqp的starter依赖

·配置RabbitMQ地址

·定义类，添加@Component注解

·类中声明方法，添加@RabbitListener注解，方法参数就是消息

注意:消息一旦消费就会从队列删除，RabbitMQ没有消息回溯功能  

------workQueue模型

work模型的使用:

·多个消费者绑定到一个队列，同一条消息只会被一个消费者处理

·通过设置prefetch来控制消费者预取的消息数量

-------发布订阅模型

通过exchange（交换机）实现。广播、路由，话题

-------FanoutExchange

交换机的作用是什么?·

接收publisher发送的消息

·将消息按照规则路由到与之绑定的队列

·不能缓存消息，路由失败，消息丢失

·FanoutExchange的会将消息路由到每个绑定的队列

声明队列、交换机、绑定关系的Bean是什么?

· Queue

·FanoutExchange

· Binding

-------DirectExchange

描述下Direct交换机与Fanout交换机的差异?

· Fanout交换机将消息路由给每一个与之绑定的队列.

· Direct交换机根据RoutingKey判断路由给哪个队列

·如果多个队列具有相同的RoutingKey，则与Fanout功能类似

基于@RabbitListener注解声明队列和交换机有哪些常见注解?

·@Queue

·@Exchange

-------TopicExchange

发布订阅-TopicExchange

TopicExchange与DirectExchange类似，区别在于routingKey必须是多个单词的列表，并且以.分割。Queue与Exchange指定BindingKey时可以使用通配符:

#:代指0个或多个单词    china.#     japan.#

\*:代指一个单词         

--------消息转换器

SpringAMQP中消息的序列化和反序列化是怎么实现的?  用jsonConverter

·利用MessageConverter实现的，默认是JDK的序列化

<a name="rd0h-1664351052636"></a>·注意发送方与接收方必须使用相同的MessageConverter

<a name="cumd-1664453094415"></a>**elasticsearch**

<a name="bjw6-1699484040955"></a>**-作用（搜索日志统计分析）**

<a name="zu2v-1699484079593"></a>**-倒排索引**

<a name="p9bz-1699484104132"></a>**-ES基本概念**

<a name="kw2u-1699484111406"></a>**-操作索引库-mapping属性**

<a name="ydit-1699484174907"></a>**-DSL查询语法**

<a name="xwmx-1699484175219"></a>**-RestClient查询文档**

<a name="urie-1699484175454"></a>**-深入分布式搜索引擎ElasticSearch**

<a name="zjrt-1699484175729"></a>**-集群**

什么是elasticsearch?

一个开源的分布式搜索引擎，可以用来实现搜索、日志统计、分析、系统监控等功能

什么是elastic stack (ELK)?

·是以elasticsearch为核心的技术栈，包括beats、Logstash、kibana、elasticsearch

什么是Lucene?

·是Apache的开源搜索引擎类库，提供了搜索引擎的核心API

------ES倒排索引 （分词/分布式中又叫二级索引

什么是文档和词条?

·每一条数据就是一个文档

·对文档中的内容分词，得到的词语就是词条

什么是正向索引?

什么是正向索引？

·基于文档id创建索引。查询词条时必须先找到文档，而后判断是否包含词条

什么是倒排索引?


·对文档内容分词，对词条创建索引，并记录词条所在文档的信息。查

询时先根据词条查询到文档id，而后获取到文档

ES基本概念

文档:一条数据就是一个文档，es中是]son格式

字段:Json文档中的字段

索引:同类型文档的集合

映射:索引中文档的约束，比如字段名称、类型

elasticsearch与数据库的关系:

·数据库负责事务类型操作

·elasticsearch负责海量数据的搜索、分析、计算

安装ES,安装Kibana 使用kb DevTools 进行DSL语句查询

使用ik分词器插件

分词器的作用是什么?

·创建倒排索引时对文档分词

·用户搜索时，对输入的内容分词

IK分词器有几种模式?

. ik\_smart:智能切分，粗粒度

. ik\_max\_word:最细切分，细粒度

IK分词器如何拓展词条?如何停用词条?

·利用config目录的lkAnalyzer.cfg.xml文件添加拓展词典和停用词典

·在词典中添加拓展词条或者停用词条

-----操作索引库-mapping属性

mapping常见属性有哪些?

. type:数据类型

. index:是否索引

. analyzer:分词器

. properties:子字段

type常见的有哪些?

·字符串: text、keyword

·数字: long.integer、short、 byte、double、float

·布尔: boolean

·日期: date

·对象: object

----索引库的操作有哪些？

·创建索引库:PUT/索引库名

·查询索引库:GET/索引库名

·删除索引库:DELETE/索引库名

.添加字段:PUT/索引库名l\_mapping

-----文档操作

新增、查询、删除、修改

文档操作有哪些?

·创建文档:POST/索引库名l\_doc/文档id { json文档}

·查询文档:GET/索引库名l\_doc/文档id

·删除文档:DELETE/索引库名l\_doc/文档id·修改文档:

·全量修改:PUT/索引库名l\_doc/文档id { json文档}

·增量修改:POST/索引库名l \_update/文档id { "doc":{字段}}

-------java RestClient操作索引库

索引库操作的基本步骤:

·初始化RestHighLevelClient

·创建XxxIndexRequest。XXX是CREATE、Get、Delete

·准备DSL ( CREATE时需要)

。发送请求。调用RestHighLevelClienttindices().xxx()方法,XXx是create、exists、delete

------批量导入文档

Bulk

--------DSL查询语法-match查询

查询DSL的基本语法是什么?

. GET/索引库名/\_search

. { "query":{ "查询类型": { "FIELD":"TEXT"}}}

-----全文检索查询

match和multi\_match的区别是什么?

. match:根据一个字段查询 

. multi\_match:根据多个字段查询，参与查询字段越多，查询性能越差

---------精确查询常见的有哪些?

.  term查询:根据词条精确匹配，一般搜索keyword类型、数值类型、布尔类型、日期类型字段

. range查询:根据数值范围查询，可以是数值、日期的范围

------地理查询  geo\_distance: distance:2km location:"经纬度"

-------elasticsearch中的相关性打分算法是什么?

.TF-IDF:在elasticsearch5.0之前，会随着词频增加而越来越大

.BM25:在elasticsearch5.0之后，会随着词频增加而增大，但增长曲线会趋于水平

-----function score query定义的三要素是什么?

·过滤条件:哪些文档要加分

·算分函数:如何计算function score

·加权方式: function score 与query score如何运算

-----bool查询有几种逻辑关系?

.must:必须匹配的条件，可以理解为“与”

. should:选择性匹配的条件，可以理解为“或”

. must\_not:必须不匹配的条件，不参与打分

. filter:必须匹配的条件，不参与打分

-------搜索处理结果-排序

sort 正常字段排序 和 地理位置排序

-------结果集处理 分页

from + size:

·优点:支持随机翻页

·缺点:深度分页问题，默认查询上限（ from + size）是10000·场景:百度、京东、谷歌、淘宝这样的随机翻页搜索

after search:

·优点:没有查询上限（单次查询的size不超过10000) ·缺点:只能向后逐页查询，不支持随机翻页

·场景:没有随机翻页需求的搜索，例如手机向下滚动翻页

scroll:

·优点:没有查询上限（单次查询的size不超过10000) ·缺点:会有额外内存消耗，并且搜索结果是非实时的

·场景:海量数据的获取和迁移。从ES7.1开始不推荐，建议用aftersearch方案。

-------高亮

高亮:就是在搜索结果中把搜索关键字突出显示。原理是这样的:

·将搜索结果中的关键字用标签标记出来·在页面中给标签添加css样式  "hightlight"

-------RestClient查询文档 

查询的基本步骤是:

1．创建SearchRequest对象

2\.准备Request.source()，也就是DSL。

QueryBuilders来构建查询条件

传入Request.source()的query()方法

3．发送请求，得到结果

4．解析结果（参考JSON结果，从外到内，逐层解析)

------mathch、term、range、bool  要构建查询条件，只需要记住一个类 QueryBuilders

------排序和分页

------高亮显示

-------黑马旅游酒店案例  搜索、分页；条件过滤；我附近的酒店；

--------广告置顶；

我们给需要置顶的酒店文档添加一个标记。然后利用function score给带有标记的文档增加权重。

实现步骤分析:

1．给HotelDoc类添加isAD字段，Boolean类型

2．挑选几个你喜欢的酒店，给它的文档数据添加isAD字段，值为true

3．修改search方法，添加function score功能，给isAD值为true的酒店增加权重

-------深入分布式搜索引擎ElasticSearch

什么是聚合?

·聚合是对文档数据的统计、分析、计算聚合的常见种类有哪些?

.Bucket: 对文档数据分组，并统计每组数量

-Metric:对文档数据做计算，例如avg

` `Pipeline:基于其它聚合结果再做聚合

` `参与聚合的字段类型必须是:

.keyword

·数值·日期·布尔

------DSL实现Bucket聚合

aggs代表聚合，与query同级，此时query的作用是?

·限定聚合的的文档范围

聚合必须的三要素:

·聚合名称

·聚合类型

·聚合字段

聚合可配置属性有:

. size:指定聚合结果数量

. order:指定聚合结果排序方式

. field:指定聚合字段

-------DSL实现metrics聚合  获取每个品牌的用户评分的min、max、avg等值，利用stat聚合

-------RestClient实现聚合

-------多条件聚合

--------带过滤条件的聚合

---------自动补全

---------拼音分词器   es插件

---------自定义分词器    很 强

如何使用拼音分词器?

. 下载pinyin分词器

. 解压并放到elasticsearch的plugin目录

. 重启即可

如何自定义分词器?

. 创建索引库时，在settings中配置，可以包含三部分

.character filter

.tokenizer

.filter

拼音分词器注意事项?

·为了避免搜索到同音字，搜索时不要使用拼音分词器

-------DSL实现自动补全查询   suggest     

自动补全对字段的要求:

类型是completion类型,字段值是多词条的数组

` `-----修改酒店索引库数据结构 

` `------RestAPI实现自动补全   

` `------实现搜索框自动补全



` `---------数据同步-同步方案分析

` `admin微服务-mysql    查询微服务-elasticSearch

方式一:同步调用 -B暴露更新接口(下下策)

·优点:实现简单，粗暴

·缺点:业务耦合度高  A响应变慢

方式二:异步通知 -消息队列MQ

·优点:低耦合，实现难度一般

·缺点:依赖mq的可靠性

方式三:监听binlog  -canel

·优点:完全解除服务间耦合

·缺点:开启binlog增加数据库负担、实现复杂度高

------amqp代码实现

步骤:

·导入课前资料提供的hotel-admin项目

，启动并测试酒店数据的CRUD

·声明exchange.queue、RoutingKey

，在hotel-admin中的增、删、改业务中完成消息发送

·在hotel-demo中完成消息监听，并更新elasticsearch中数据

·启动并测试数据同步功能


--------es集群

--------搭建集群   shards分片 及 备份到不同主机提高可靠性

集群管理 cerebro

--------es集群职责 及 脑裂

master eligible节点的作用是什么?

·参与集群选主

·主节点可以管理集群状态、管理分片信息、处理创建和删除索引库的请求

data节点的作用是什么?

·数据的CRUD

coordinator节点的作用是什么?

·路由请求到其它节点

·合并查询到的结果，返回给用户

脑裂（多主）问题:

`    `网络延迟导致备选当主。通过算法选票机制避免脑裂。

`    `解决：es6.X 配置discovery.zen.ping.multicast.enabled: false  ；es7已自动解决

--------分布式新增和查询流程

分布式新增如何确定分片?

.coordinating node根据id做hash运算，得到结果对shard数量取余，余数就是对应的分片。是均衡的，一旦建立索引库就不能再改变分片数量

分布式查询:

·分散阶段: coordinating node将查询请求分发给不同分片

·收集阶段:将查询结果汇总到coordinating node，整理并返回给用户

-----故障转移  -非常智能

故障转移:

.master宕机后，EligibleMaster选举为新的主节点。

.master节点监控分片、节点状态，将故障节点上的分片转移到正常节点，确保数据安全。

<a name="hahv-1664453119778"></a>                                                      

<a name="5hmj-1664453119779"></a><a name="rnrl-1664904101009"></a>**高级篇**

<a name="sxsr-1664910145443"></a>**Sentinel（or Hystrix）**

<a name="oolh-1699484343150"></a>**-限流(解决服务雪崩）**

<a name="prep-1699581264466"></a>**-限流规则**

<a name="hpmj-1699581403947"></a>**-流控模式（直接,关联,链路）**

<a name="c86l-1699581448479"></a>**-流控效果（快速失败,等待,预热）**

-------初识Sentinel

什么是雪崩问题?

·微服务之间相互调用，因为调用链中的一个服务故障，引起整个链路都无法访问的情况。

如何避免因瞬间高并发流量而导致服务故障?

·流量控制

如何避免因服务故障引起的雪崩问题?

解决雪崩问题的常见方式有四种:

·超时处理:设定超时时间，请求超过一定时间没有响应就返回错误信息，不会无休止等待

·舱壁模式:限定每个业务能使用的线程数，避免耗尽整个tomcat的资源，因此也叫线程隔离。

·熔断降级:由断路器统计业务执行的异常比例，如果超出阈值则会熔断该业务，拦截访问该业务的一切请求。

·流量控制:限制业务访问的QPS，避免服务因流量的突增而故障。-Sentinel

--------服务保护技术对比

ali Sentinel     netflix Hystrix

---------安装sentinel

运行jar文件，改配置在启动时添加配置项即可

---------cloud整合sentinel

---------限流规则

·簇点链路:就是项目内的调用链路，链路中被监控的每个接口就是一个资源。默认情况下sentinel会监控SpringMVC的

每一个端点（Endpoint)，因此SpringMVC的每一个端点（Endpoint)）就是调用链路中的一个资源。

·流控、熔断等都是针对簇点链路中的资源来设置的，因此我们可以点击对应资源后面的按钮来设置规则:

·QPS-每秒处理的请求数，sentinel配置后用jmeter压测

---------流控模式

在添加限流规则时，点击高级选项，可以选择三种流控模式:

·直接:统计当前资源的请求，触发阈值时对当前资源直接限流，也是默认的模式。

·关联:统计与当前资源相关的另一个资源，触发阈值时，对当前资源限流

·链路:统计从指定链路访问到本资源的请求，触发阈值时，对指定链路限流

流控模式-关联

·关联模式:统计与当前资源相关的另一个资源，触发阈值时，对当前资源限流

·使用场景:比如用户支付时需要修改订单状态，同时用户要查询订单。查询和修改操作会争抢数据库锁，产生竞争。

业务需求是有限支付和更新订单的业务，因此当修改订单业务触发阈值时，需要对查询订单业务限流。

小结

满足下面条件可以使用关联模式:

·两个有竞争关系的资源

·一个优先级较高，一个优先级较低

链路小结

·监控非Controller @SentinelResource

--------流控效果

流控效果是指请求达到流控阈值时应该采取的措施，包括三种:

·快速失败:达到阈值后，新的请求会被立即拒绝并抛出FlowException异常。是默认的处理方式。

.warm up:预热模式，对超出阈值的请求同样是拒绝并抛出异常。但这种模式阈值会动态变化，从一个较小值逐渐增

加到最大阈值。

·排队等待:让所有的请求按照先后次序排队执行，两个请求的间隔不能小于指定时长

-------流控效果-warm up

·warm up也叫预热模式，是应对服务冷启动的一种方案。请求阈值初始值是threshold / coldFactor，持续指定时长后，逐渐提

高到threshold值。而coldFactor的默认值是3.

例如，我设置QPS的threshold为10，预热时间为5秒，那么初始阈值就是10/3，也就是3，然后在5秒后逐渐增长到10.

·流控效果-排队等待

当请求超过aPs阈值时，快速失败和warm up会拒绝新的请求并抛出异常。而排队等待则是让所有请求进入一个队列中，然后按

照阈值允许的时间间隔依次执行。

后来的请求必须等待前面执行完成，如果请求预期的等待时间超出最大时长则会被拒绝。

每

小结：流控效果有哪些?

·快速失败:QPS超过阈值时，拒绝新的请求

. warm up: QPS超过阈值时，拒绝新的请求;QPS阈值是逐

渐提升的，可以避免冷启动时高并发导致服务宕机。

·排队等待:请求会进入队列，按照阈值允许的时间间隔依次

执行请求;如果请求预期等待时长大于超时时间，直接拒绝

------热点参数限流

给/order/{orderld}这个资源添加热点参数限流，规则如下:

·默认的热点参数规则是每1秒请求量不超过2

·给102这个参数设置例外:每1秒请求量不超过4

·给103这个参数设置例外:每1秒请求量不超过1

<a name="rtgy-1699582206504"></a>注意，热点参数限流对默认的SpringMVc资源无效，需要使用注解@SentinelResource

<a name="xxzz-1699582196289"></a>**-隔离（信号量,线程池）**

<a name="pmss-1699583278371"></a>**-熔断降级（超阈值拦截）**

<a name="h6fq-1699583340714"></a>**-授权及规则持久化**

----------隔离和降级

隔离和降级

·虽然限流可以尽量避免因高并发而引起的服务故障，但服务还会因为其它原因而故障。而要将这些故障控制在一定范，避免雪崩，

就要靠线程隔离（舱壁模式）和熔断降级手段了。

·不管是线程隔离还是熔断降级，都是对客户端（调用方）的保护。 

-------FeighClient整合Sentinel

SpringCloud中，微服务调用都是通过Feign来实现的，因此做客户端保护必须整合Feign和Sentinel

.1．修改OrderService的application.yml文件，开启Feign的Sentinel功能

feign:

`    `sentinel:

`        `enabled : true #开启Feign的sentinel功能

2．给FeignClient编写失败后的降级逻辑

方式一:FallbackClass，无法对远程调用的异常做处理

方式二:FallbackFactory，可以对远程调用的异常做处理，我们选择这种

总结：Sentinel支持的雪崩解决方案:

·线程隔离（仓壁模式)

·降级熔断

Feign整合Sentinel的步骤:

·在application.yml中配置:feign.sentienl.enable=true·给EeignClient编写FallbackFactory并注册为Bean

·将FallbackFactory配置到FeignClient

------线程隔离的两种手段是?

·信号量隔离

·线程池隔离

信号量隔离的特点是?  -限流策略选QPS改线程数

·基于计数器模式，简单，开销小

线程池隔离的特点是?

·基于线程池模式，有额外开销，但隔离控制更强

------熔断降级

·熔断降级是解决雪崩问题的重要手段。其思路是由断路器统计服务调用的异常比例、慢请求比例，

如果超出阈值则会熔断该服务。即拦截访问该服务的一切请求;而当服务恢复时，断路器会放行访问该服务的请求。

总结：sentinel熔断降级的策略有哪些?

·慢调用比例:超过指定时长的调用为慢调用，统计单位时长内

慢调用的比例，超过阈值则熔断

·异常比例:统计单位时长内异常调用的比例，超过阈值则熔断

·异常数:统计单位时长内异常调用的次数，超过阈值则熔断

-------授权规则及规则持久化

授权规则 -非网关请求不给访问，网关带标识

我们还需要在gateway服务中，利用网关的过滤器添加名为gateway的origin头:

spring:

`    `cloud :gateway :

`        `default-filters:

`        `- AddRequestHeader=origin,gateway #添加名为origin的请求头，值为gateway

给/order/{orderld}配置授权规则:

资源名：/orderl{orderld}

流控应用 ：gatewy

授权类型：白名单○黑名单

Sentinel是通过RequestOriginParser这个接口的parseOrigin来获取请求的来源的。-代码略

-------自定义异常结果

实现BlockException，代码略

--------规则持久化

Sentinel的三种配置管理模式是什么?

·原始模式:保存在内存

·pull模式:保存在本地文件或数据库，定时去读取  -时效性差 

. push模式:保存在nacos，监听变更实时更新  -推荐

<a name="jcat-1664910165538"></a>具体实现代码，修改sentinel源码复杂，略

<a name="u0zn-1664910153126"></a>**分布式事务**

<a name="fkn4-1699583467105"></a>**-CAP定理（只可同时实现其二）**

<a name="cxea-1699583499418"></a>**-Base理论（基本可用,最终一致性）**

<a name="bodx-1699583555792"></a>**-Seata(xa,at,tcc,saga)**

--------分布式事务

分布式服务的事务问题

在分布式系统下，一个业务跨越多个服务或数据源，每个服务都是一个分支事务，要保证所有分支事务最终状态一致，

这样的事务就是分布式事务。

------CAP定理

1998年，加州大学的计算机科学家Eric Brewer提出，分布式系统有三个指标:

. consistency (一致性)：用户访问分布式系统中的任意节点，得到的数据必须一致 -需节点数据同步

. Availability (可用性)：用户访问集群中的任意健康节点，必须能得到响应，而不是超时或拒绝

. Partition tolerance (分区容错性)：

`            `Partition(分区)-因为网络故障或其它原因导致分布式系统中的部分节点与其它节点

`                            `失去连接，形成独立分区。

`            `Tolerance(容错)︰在集群出现分区时，整个系统也要持续对外提供服务 -此时错误节点数据不同步，恢复后不可立即可用，

`                            `需同步数据后再提供服务（CAP案例）

Eric Brewer说，分布式系统无法同时满足这三个指标（最多可两两相交AP、CP）。这个结论就叫做CAP定理。

简述CAP定理内容?

·分布式系统节点通过网络连接，一定会出现分区问题（P)

·当分区出现时，系统的一致性（C）和可用性（A）就无法同时满足

思考: elasticsearch集群是CP还是AP?

.ES集群出现分区时，故障节点会被剔除集群，数据分片会重新分配到其它节点，保证数据一致。因此是低可用性，高一致性，属于CP

----------Base理论


BASE理论是对CAP的一种解决思路，包含三个思想: -选择和调和

.Basically Available (基本可用)︰分布式系统在出现故障时，允许损失部分可用性，即保证核心可用。

. Soft state(软状态)∶在一定时间内，允许出现中间状态，比如临时的不一致状态。

.Eventually Consistent(最终一致性)∶虽然无法保证强一致性，但是在软状态结束后，最终达到数据一致。

而分布式事务最大的问题是各个子事务的一致性问题，因此可以借鉴CAP定理和BASE理论:

·AP模式-最终一致思想:各子事务分别执行和提交，允许出现结果不一致，然后采用弥补措施恢复数据即可，实现最终一致。

·CP模式-强一致思想:各个子事务执行后互相等待，同时提交，同时回滚，达成强一致。但事务等待过程中，处于弱可用状态。

分布式事务模型：

解决分布式事务，各个子系统之间必须能感知到彼此的事务状态，才能保证状态一致，

因此需要一个事务协调者来协调每一个事务的参与者（子系统事务)。

-------Seata

Seata事务管理中有三个重要的角色:-架构

·TC(Transaction Coordinator)-事务协调者:维护全局和分支事务的状态，协调全局事务提交或回滚。

·TM(Transaction Manager)-事务管理器:定义全局事务的范围、开始全局事务、提交或回滚全局事务。

·RM(Resource Manager)-资源管理器︰管理分支事务处理的资源，与TC交谈以注册分支事务和报告分支事务的状态，

并驱动分支事务提交或回滚。

\-------

Seata提供了四种不同的分布式事务解决方案:

. XA模式:强一致性分阶段事务模式，牺牲了一定的可用性，无业务侵入

. TCC模式:最终一致的分阶段事务模式，有业务侵入

。AT模式:最终一致的分阶段事务模式，无业务侵入，也是Seata的默认模式

. SAGA模式:长事务模式，有业务侵入

--------部署seta的tc-server

--------微服务集成Seata

nacos服务名称组成包括?

·namespace + group + serviceName + cluster

seata客户端获取tc的cluster名称方式?

·以tx-group-service的值为key到vgroupMapping中查找

----------XA模式

XA模式的优点是什么?

·事务的强一致性，满足ACID原则。

·常用数据库都支持，实现简单，并且没有代码侵入

XA模式的缺点是什么?

·因为一阶段需要锁定数据库资源，等待二阶段结束才释放，性能较差

·依赖关系型数据库实现事务

-----------AT模式

AT模式同样是分阶段提交的事务模型，不过缺弥补了XA模型中资源锁定周期过长的缺陷。

阶段—RM的工作:

.注册分支事务

.记录undo-log（数据快照)

.执行业务sql并提交

.报告事务状态

阶段二提交时RM的工作:

.删除undo-log即可

阶段二回滚时RM的工作:

.根据undo-log恢复数据到更新前

简述AT模式与XA模式最大的区别是什么?

.XA模式一阶段不提交事务，锁定资源;AT模式一阶段直接提交，不锁定资源。

. XA模式依赖数据库机制实现回滚;AT模式利用数据快照（例如：undolog）实现数据回滚。

.XA模式强一致;AT模式最终一致

AT模式的优点:

·一阶段完成直接提交事务，释放数据库资源，性能比较好

·利用全局锁实现读写隔离，预防脏数据(同时cas对比非seata管理的事务)

·没有代码侵入，框架自动完成回滚和提交

AT模式的缺点:

·两阶段之间属于软状态，属于最终一致

·框架的快照功能会影响性能，但比XA模式要好很多

----------TCC模式原理

TCC模式与AT模式非常相似，每阶段都是独立事务，不同的是TCC通过人工编码来实现数据恢复。

需要实现三个方法:

·Try:资源的检测和预留; -即具体的扣减金额，而不是总金额快照，tips 金额字段约束，无符号（unsigned），负数即异常

·Confirm:完成资源操作业务;要求Try成功Confirm一定要能成功。

. cancel:预留资源释放，可以理解为try的反向操作。

TCC的优点是什么?

·一阶段完成直接提交事务，释放数据库资源，性能好

·相比AT模型，无需生成快照，无需使用全局锁，性能最强

·不依赖数据库事务，而是依赖补偿操作，可以用于非事务型数据库

TCC的缺点是什么?

·有代码侵入，需要人为编写try、confirm和cancel接口，太麻烦

·软状态，事务是最终一致

·需要考虑Confirm和Cancel的失败情况，做好幂等处理，空回滚，业务悬挂问题。

代码略

------------------Saga模式

Saga模式是SEATA提供的长事务解决方案。也分为两个阶段:

·一阶段:直接提交本地事务

·二阶段:成功则什么都不做;失败则通过编写补偿业务来回滚

Saga模式优点:

·事务参与者可以基于事件驱动实现异步调用，吞吐高

·一阶段直接提交事务，无锁，性能好

·不用编写TcC中的三个阶段，实现简单

缺点:

·软状态持续时间不确定，时效性差

<a name="mbwm-1665086589355"></a>·没有锁，没有事务隔离，会有脏写

<a name="tzbg-1665086589356"></a>AT和TCC比较常用

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.003.png)

<a name="k1xe-1665245070294"></a><a name="bove-1665245070297"></a><a name="krsw-1665245268203"></a>**Redis**

<a name="eegj-1665245288453"></a>**持久化**

<a name="5kee-1665249623480"></a>**RDB--记录数据**

-------RDB

Redis内部有触发RDB的机制，可以在redis.conf文件中找到，格式如下:

#900秒内，如果至少有1个key被修改，则执行bgsave ，如果是save ""则表示禁用

RDBsave 900 1

save 300 10

save 6010000

RDB的其它配置也可以在redis.conf文件中设置:

#是否压缩,建议不开启，压缩也会消耗cpu，磁盘的话不值钱

rdbcompression yes

#RDB文件名称

dbfilename dump.rdb

#文件保存的路径目录

dir ./

RDB方式bgsave的基本流程?

. fork主进程得到一个子进程，共享内存空间

·子进程读取内存数据并写入新的RDB文件

·用新RDB文件替换旧的RDB文件。

RDB会在什么时候执行? save 60 1000代表什么含义?

·默认是服务停止时。

·代表60秒内至少执行1000次修改则触发

RDBRDB的缺点?

. RDB执行间隔时间长，两次RDB之间写入数据有丢失的风险

<a name="pkg1-1665247506637"></a>. fork子进程、压缩、写出RDB文件都比较耗时

<a name="errt-1665247506638"></a>**AOF--记录指令**

apendonly File

因为是记录命令，AOF文件会比RDB文件大的多。而且AOF会记录对同一个key的多次写操作，但只有最后一次写操作才有意义。

<a name="wfal-1665249663462"></a>通过执行bgrewriteaof命令，可以让AOF文件执行重写功能，用最少的命令达到相同效果。

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.004.png)

<a name="flh8-1665249663463"></a><a name="60p0-1665249464421"></a><a name="sedi-1665249464425"></a>**Redis主从**

<a name="zqmb-1665258900495"></a>**搭建主从**

Tips :xShell mutil-execution mode: typed to all terminals

搭建主从结构  主为写，从只可读

假设有A、B两个Redis实例，如何让B作为A的slave节点?

<a name="oul1-1665258737505"></a>·在B节点执行命令: slaveof A的IPA的port

<a name="q5rb-1665257395581"></a>  **数据同步原理(增量,全量)**

简述全量同步的流程?

. slave节点请求增量同步

.master节点判断replid，发现不一致，拒绝增量同步（后面会继承master的replid）

.master将完整内存数据生成RDB，发送RDB到slave

. slave清空本地数据，加载master的RDB

.master将RDB期间的命令记录在repl\_baklog，并持续将log中（有offset偏移量）的命令发送给slave

. slave执行接收到的命令，保持与master之间的同步

-------增量同步

简述全量同步和增量同步区别?

·全量同步:master将完整内存数据生成RDB，发送RDB到slave。后续命令则记录在repl\_baklog，逐个发送给slave。

·增量同步: slave提交自己的offset到master, master获取repl\_baklog中从offset之后的命令给slave

什么时候执行全量同步?

.slave节点第一次连接master节点时

.slave节点断开时间太久，repl\_baklog中的offset已经被覆盖时（repl\_baklog为环状结构）

什么时候执行增量同步?

<a name="qcwj-1665259387698"></a>.slave节点断开又恢复，并且在repl\_baklog中能找到offset时

<a name="ljys-1665259387699"></a>**Redis哨兵(监控,故障转移,通知)**

sentinel的三个作用是什么?

.监控

·故障转移

·通知

Sentinel如何判断一个redis实例是否健康?

·每隔1秒发送一次ping命令（心跳监测），如果超过一定时间没有相向则认为是主观下线

·如果大多数sentinel都认为实例主观下线，则判定服务下线

故障转移步骤有哪些?

·首先选定一个slave作为新的master，执行slaveaf no one

·然后让所有节点都执行slaveof新master

·修改故障节点配置，添加slaveof 新master

--------RedisTemplate的哨兵模式  --基本配置就行，其它故障修复选主啥的由sentinel自动化

1．在pom文件中引入redis的starter依赖:

<dependency>

`    `<groupId>org.springframework.boot</groupId>

`    `<artifactId>spring-boot-starter-data-redis

</artifactId></ dependency>

2．然后在配置文件application.yml中指定sentinel相关信息:

spring:

`    `redis:

`        `sentinel:

`        `master: mymaster #指定master名称nodes: #指定redis-sentinel集群信息

`            `-192.168.150.101:27001

`            `- 192.168.150.101:27802

`            `- 192.168.150.101:27003

3．配置主从读写分离

@Bean

public LettuceclientConfigurationBuilderCustomizer configurationBuilderCustomizer(){

`    `//--tips.单个重写方法的匿名内部类可以一键用lambda替换

`    `return configBuilder -> configBuilder.readFrom(ReadFrom.REPLICA\_PREFERRED); 

}

这里的ReadFrom是配置Redis的读取策略，是一个枚举，包括下面选择:

.MASTER:从主节点读取

.MASTER\_PREFERRED:优先从master节点读取，master不可用才读取replica

.REPLICA: 从slave ( replica）节点读取

<a name="6brz-1665260129910"></a>·REPLICA\_PREFERRED:优先从slave (replica）节点读取，所有的slave都不可用才读取master

<a name="dmud-1665260129911"></a>**Redis分片集群(一般仅大厂有)**

<a name="zz0t-1665312911874"></a>**分片集群结构**

---------分片集群结构 ----一般只有大厂机构需要，普通公司单个redis已经够用了

主从和哨兵可以解决高可用、高并发读的问题。但是依然有两个问题没有解决:

·海量数据存储问题

· 高并发写的问题

使用分片集群可以解决上述问题，分片集群特征:

·集群中有多个master，每个master保存不同数据

·每个master都可以有多个slave节点

. master之间通过ping监测彼此健康状态 -哨兵效果

·客户端请求可以访问集群任意节点，最终都会被转发到正确节点

-------集群搭建

<a name="8kda-1665310964194"></a>linux指令一键修改端口号，一键启动多实例

<a name="kikk-1665310964195"></a>**散列插槽**

Redis如何判断某个key应该在哪个实例?

·将16384个插槽分配到不同的实例

·根据key的有效部分计算哈希值，对16384取余(CRC算法)

·余数作为插槽，寻找插槽所在实例即可

如何将同一类数据固定的保存在同一个Redis实例?

<a name="vzk5-1665312946912"></a>·这一类数据使用相同的有效部分，例如key都以{typeld}为前缀

<a name="1jjc-1665312946913"></a>**集群伸缩**

<a name="x9j5-1665312988480"></a>-----新建实例、指令分配插槽

<a name="pzdy-1665312988481"></a>**故障转移**

--------数据迁移

利用cluster failover命令可以手动让集群中的某个master宕机，切换到执行cluster failover命令的这个slave节点，

S现无感知的数据迁移。其流程如下:图-数迁

手动的Failover支持三种不同模式:

·缺省:默认的流程，如图1~6步

. force:省略了对offset的一致性校验

<a name="x0eh-1665333554644"></a>. takeover:"直接执行第5步，忽略数据一致性、忽略master状态和其它master的意见

<a name="lic3-1665333554645"></a>图-数迁

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.005.png)

<a name="tvmo-1665341747296"></a><a name="q7es-1665341747299"></a>**RedisTemplate访问分片集群**

和集群配置一样（Sentinel地址改master、slave集群），Bean代码一样

spring:

`    `redis:

`        `cluster:

`            `nodes:

`                `- 192.168.150.101 : 7001

`                `- 192.168.150.101 :7002- 192.168.150.101:7003- 192.168.150.101:8001- 192.168.150.101 :8002- 192.168.150.101:8003

#sentinel:

`    `#master: mymaster

`        `#nodes:

`        `#- 192.168.150.101:2700l

<a name="tphg-1665341859928"></a>        #- 192.168.150.101:27002

<a name="fl8s-1665341859929"></a>**多级缓存(客户端,nginx,redis,服务进程,数据库)**

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.006.png)

<a name="ntvb-1665383773119"></a><a name="801y-1665383775520"></a><a name="syrm-1665383780871"></a><a name="hjvz-1665383780870"></a>亿级流量

<a name="eahb-1665383780873"></a>**MQ常见问题及消息可靠性**

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.007.png)

<a name="nyc6-1665384108092"></a><a name="mohm-1665384121768"></a><a name="u23l-1665384121771"></a>消息可靠性     死信交换机 惰性队列  MQ集群

<a name="w99z-1665384332679"></a><a name="yap8-1665384333047"></a>**K8s**

<a name="sq2s-1665385586877"></a>**Docker**

<a name="gwea-1665424988829"></a>**Docker架构**

-------Docker

Docker如何解决大型项目依赖关系复杂，不同组件依赖的兼容性问题?

. Docker允许开发中将应用、依赖、函数库、配置一起打包，形成可移植镜像。 

.Docker应用运行在容器中，使用沙箱机制，相互隔离

Docker如何解决开发、测试、生产环境有差异的问题

. Docker镜像中包含完整运行环境，包括系统函数库，仅依赖系统的Linux内核，因此可以在任意Linux操作系统上运行

---总结

Docker是一个快速交付应用、运行应用的技术:

1．可以将程序及其依赖、运行环境一起打包为一个镜像，可以迁移到任意Linux操作系统

2．运行时利用沙箱机制形成隔离容器，各个应用互不干扰

3．启动、移除都可以通过一行命令完成，方便快捷

镜像:

·将应用程序及其依赖、环境、配置打包在一起

容器:

·镜像运行起来就是容器，一个镜像可以运行多个容器

Docker结构:

·服务端:接收命令或远程请求，操作镜像或容器

·客户端:发送命令或者请求到Docker服务端

DockerHub:

<a name="sxuj-1665385574631"></a>·一个镜像托管的服务器，类似的还有阿里云镜像服务，统称为DockerRegistry

<a name="6lfr-1665385574632"></a>**docker安装及命令**

------cent os 根据安装文档安装docker

<a name="tdil-1665425047631"></a>------通过Doker order help学习命令使用

<a name="ttrd-1665476783436"></a>**镜像命令**

-------镜像命令

1．去DockerHub搜索Redis镜像

2．查看Redis镜像的名称和版本

3．利用docker pull命令拉取镜像

4．利用docker save命令将redis:latest打包为一个redis.tar包

5．利用docker rmi删除本地的redis:latest

6．利用docker load重新加载redis.tar文件

##########额外:提交镜像的改变

` `docker commit [OPTIONS]CONTAINER [REPOSITORY[ : TAG]]2

` `docker commit -a "leifengyang" -m“首页变化”341d81f7504f gulnginx:v1.0  //gulnginx-镜像名

镜像推送

docker tag local-image:tagname new-repo:tagname

<a name="uiqg-1665476843501"></a>docker push new-reop:tagname

<a name="iqdv-1665476805658"></a>**容器命令**

<a name="otqb-1665476862769"></a>--------容器命令

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.008.png)

<a name="ajqs-1665476862770"></a><a name="kvmt-1665476575342"></a><a name="eehx-1665476890866"></a>--------案例：创建运行一个Nginx容器

步骤一:去docker hub查看Nginx的容器运行命令

docker run --name containerName -p 80:80 -d nginx

命令解读:

.docker run :创建并运行一个容器

.--name:给容器起一个名字，比如叫做mn

.-p∶将宿主机端口与容器端口映射，冒号左侧是宿主机端口，右侧是容器端口

.-d:后台运行容器

.nginx:镜像名称，例如nginx

查看容器日志的命令:

\- docker logs [容器名称]

·添加-f参数可以持续查看日志

-----------案例进入Nginx容器，修改HTML文件内容，添加“传智教育欢迎您”

步骤一:进入容器。进入我们刚刚创建的nginx容器的命令为:

docker exec -it mn bash

命令解读:

.docker exec:进入容器内部，执行一个命令。-内部为阉割版linux目录（vi命令用不了），可通过查看docker hub看nignx配置文件路径

.-it:给当前进入的容器创建一个标准输入、输出终端，允许我们与容器交互

.mn :要进入的容器的名称

.bash:进入容器后执行的命令，bash是一个linux终端交互命令，windows 为sh    

步骤二:进入nginx的HTML所在目录/usr/share/nginx/ htmlcd /usr/share/nginx/html

步骤三:修改index.html的内容      -但是在容器内修改文件是不推荐的

sed -i 's#Welcome to nginx#传智教育欢迎您#g' index.html

sed -i 's#<head>#<head><meta charset="utf-8">#g' index.html

---------练习创建并运行一个redis容器，并且支持数据持久化

步骤一:到DockerHub搜索Redis镜像

步骤二:查看Redis镜像文档中的帮助信息

步骤三:利用docker run命令运行一个Redis容器

docker run --name mr -p 6379:6379 -d redis redis-server --appendonly yes

--------练习进入redis容器，并执行redis-cli客户端命令，存入num=666

<a name="ngyk-1665476890865"></a>docker exec -it mr redis-cli

<a name="ump6-1665476890868"></a>**数据卷命令**

容器与数据耦合的问题

----01不便于修改

当我们要修改Nginx的html内容时，需要进入容器内部修改，很不方便。

----02数据不可复用

在容器内的修改对外是不可见的。所有修改对新创建的容器是不可复用的。

-----03升级维护困难

数据在容器内，如果要升级容器必然删除旧容器，所有数据都跟着删除了

<a name="gosw-1665480712894"></a>数据卷(volume)是一个虚拟目录，指向宿主机文件系统中的某个目录。

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.009.png)

<a name="6y2n-1665481064236"></a><a name="r4dx-1665481114305"></a>-------操作数据卷

数据卷操作的基本语法如下:

docker volume [COMMAND]

docker volume命令是数据卷操作，根据命令后跟随的command来确定下一步的操作:

.create    创建一个volume

.inspect    显示一个或多个volume的信息 -看文件物理路径

.ls    列出所有的volume

.prun    删除未使用的volume

.rm    删除一个或多个指定的volume

数据卷的作用:

·将容器与数据分离，解耦合，方便操作容器内数据，保证数据安全

----挂载数据卷

我们在创建容器时，可以通过-v参数来挂载一个数据卷到某个容器目录

. docker run:就是创建并运行容器

. -- name mn :给容器起个名字叫mn

. -v html:/root/htm :把html（可自动创建）数据卷挂载到容器内的/root/html这个目录中

. -p 8080:80∶把宿主机的8080端口映射到容器内的80端口

. nginx:镜像名称

数据卷挂载方式:

. -v volumeName: /targetContainerPath

·如果容器运行时volume不存在，会自动被创建出来

-------直接挂在宿主机目录

-----------案例创建并运行一个MySQL容器，将宿主机目录直接挂载到容器

实现思路如下:

1．在将课前资料中的mysql.tar文件上传到虚拟机，通过load命令加载为镜像

2．创建目录/tmp/myql/data

3．创建目录/tmp/myql/conf，将课前资料提供的hmy.cnf文件上传到/tmp/myqL/conf

4．去DockerHub查阅资料，创建并运行MySQL容器，要求:

·挂载/tmp/myql/data到mysql容器内数据存储目录

·挂载/tmp/myql/conf/hmy.cnf到mysql容器的配置文件

·设置MySQL密码

` `docker run \

--name mysql \

-e MYsQL\_RoOT\_PASSwORD=123 \

-p 3306:3306 \

-v /tmp/mysql/conf/hmy.cnf:/etc/mysq1/conf.d/hmy.cnf \  --直接挂载宿主机路径，否则可能数据丢失D:/DockerData/conf/hmy.cnf:/etc/mysq1/conf/hmy.cnf

-v /tmp/ mysql/data:/var/lib/mysql \

-d \

mysql:5.7.25

1\.dockerrun的命令中通过-V参数挂载文件或目录到

容器中:

①-V volume名称:容器内目录

②-v 宿主机文件:容器内文件

③-V 宿主机目录:容器内目录

2\.数据卷挂载与目录直接挂载的

①数据卷挂载耦合度低，由docker来管理目录，但是目录较深,不好找

<a name="gdc0-1665481114304"></a>②目录挂载耦合度高，需要我们自己管理目录,不过目录容易寻找查看

<a name="kkap-1665500054290"></a>**自定义镜像**

------结构

镜像是将应用程序及其需要的系统函数库、环境、配置、依赖打包而成。

镜像是分层结构，每一层称为一个Layer

·Baselmage层:包含基本的系统函数库、环境变量、文件系统

.Entrypoint: 入口，是镜像中应用启动的命令

·其它:在Baselmage基础上添加依赖、安装程序、完成整个应用的安装和配置

------Dockerfile构建镜像

1\. Dockerfile的本质是一个文件，通过指令描述镜像的构建过程

2\. Dockerfile的第一行必须是FROM，从一个基础镜像来构建

3．基础镜像可以是基本操作系统，如Ubuntu。也可以是其他人制作好的镜像，例如: java:8-alpine (省略安装JDK操作)

<a name="mqgy-1665500087776"></a>指令： docker build -t javaweb:1.0 [dockerfile path]

<a name="xkql-1665500087777"></a>**Compose**

--------什么是DockerCompose

. Docker Compose可以基于Compose文件帮我们快速的部署分布式应用，而无需手动一个个创建和运行容器。

. Compose文件是一个文本文件，通过指令定义集群中的每个容器如何运行。

version: "3.8"

`  `services:

`        `mysql:

`        `image: mysql:5.7.25environment:

`            `MYSQL\_RO0T\_PASSWORD:123

`        `volumes:

`            `- /tmp/mysql/data: /var/lib/mysql

`            `- /tmp/mysql/conf/hmy.cnf:/etc/mysql/conf.d/ hmy.cnf

`   `web:

`    `build: .

`    `ports:

`       `- 8090: 8090

---------部署微服务集群

docker-compose up -d

------镜像仓库

本地安装搭建镜像仓库

` `1．推送本地镜像到仓库前都必须重命名(docker tag)镜像，以镜像仓库地址为前缀

2．镜像仓库推送前需要把仓库地址配置到docker服务的daemon.json文件中，被docker信任

3．推送使用docker push命令

<a name="j7zk-1665852570804"></a>4．拉取使用docker pull命令

<a name="q89l-1665764307550"></a>**K8S**

<a name="suxw-1665764770483"></a>**私有网络vpc**

1\.选ECS服务器实例（弹性计算服务），选择centos ,yum安装nginx

2\.选择带宽，绑定公网ip（外部访问），通信用私有ip（走内网省无流量费）

3\. 建立VPC(虚拟专用网络) 网络规划

<a name="ttgf-1665764807118"></a>规划网段 /16    虚拟交换机，规划子网/24 （子网间不互通）

<a name="dcnf-1652229405406"></a>**基础概念**

<a name="qmth-1665917783364"></a>**kubernetes特性**

·服务发现和负教均衡

Kubernetes可以使DNS名称或自己的IP地址公开容器，如果进入容器的流量很大

Kubernetes可以负载均衡并分配网终流童，从而使部署稳定。

·存储编排

Kubernetes 允许你自动挂载你选择的存储系统，例如本地存储公共云提供商等。

·自动部署和回滚

你可以使用Kubernetes描述已部署容的所需需状态，它可以以受控的速率将实际状态更改为期望状态。例如，你可以自动化 Kubernetes 

来为你的部署创建新容器，删除现有容器开将它们的所有资源用于新容器。

·自动完成装箱计算

Kubernetes 允许你指定每个容器所需CPU和内存(RAM)。当容器指定了资源请求时，Kubernetes可以做出更好的决策来管理容器的资源。

·自我修复

Kubernetes重新启动失败的容器、替换容器、杀死不响应用户定义的运行状况检查的容器，并目在准备好服务之前不将其通告给客户端

。密钥与配置管理

Kubernetes 允许你存储和管理敏感信息，例如密码、OAuth 令牌和ssh密钥。

你可以在不重建容器镜像的情况下部署和更新密钥和应用程序配置，也无需在堆栈配置中暴露密钥。

--------工作方式

<a name="bsle-1665917392580"></a>Kubernetes Cluster = N Master Node+ N Worker Node: N主节点+N工作节点;N>=1

<a name="wqdy-1665917368337"></a>**组件架构**

<a name="gvye-1665919152320"></a>消息流转

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.010.png)

<a name="oihd-1665919079196"></a><a name="vz54-1665919079201"></a>组件交互逻辑动画

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.011.png)

<a name="z80f-1665919577275"></a><a name="l9sw-1665919579359"></a><a name="8rsu-1665919579363"></a>集群安装逻辑

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.012.png)

<a name="nkt7-1665932326502"></a><a name="orgd-1665932327998"></a><a name="qsg5-1665932328002"></a>**k8s集群搭建**

=========1.安装yum

Yum（全称为 Yellow dog Updater, Modified）是一个在Fedora和RedHat以及CentOS中的Shell前端软件包管理器。

基于RPM包管理，能够从指定的服务器自动下载RPM包并且安装，

可以自动处理依赖性关系，并且一次安装所有依赖的软件包，无须繁琐地一次次下载、安装。

=========2.安装docker --容器环境

yum istall docker .....

=========3.预备环境

一堆linux 命令准备环境

=========4.安装集群三大件 kubelet,kubeadmin,cubectl

=========5.初始化主节点

#所有机器添加master域名映射，以下需要修改为自己的

` `echo "172.31.e.2cluster-endpoint" >> / etc /hosts3

#主节点初始化7 kubeadm init l

--apiserver-advertise-address=172.31.8.2 \

` `--control-plane-endpoint=cluster-endpnt \

--image-repository registry.cn-hangzhou.aliyuncs.com/lfy\_k8s\_images \

` `--kubernetes-version v1.2e.9 i

` `--service-cidr=10.96.0.0/16  -service层网络

--pod-network-cidr=192.168.0.0/16  -pod层

` `#所有网络范围不重叠

#查看集群所有节点

kubectl get nodes

#根据配置文件，给集群创建资源

kubectl apply -f xxx.yaml

#查看集群部署了哪些应用？

kubectl get pod -A   -- pod = n 个容器

=========6.worker节点加入集群 令牌

=========7.集群自我修复能力  服务器reboot重启自恢复

=========8.令牌过期  一个指令操作

=========9.部署dashboard --可视化界面 

kubectl applu -f http.xxxxxx 或者 wget

<a name="ixdb-1666457598938"></a>#暴露端口

<a name="rdys-1666457573542"></a>**核心实战**

=========1.操作Namespace

名称空间，用来对集群资源进行隔离划分。默认只隔离资源，不隔离网络   -prod  dev

=========2.理解pod  最小单位 1个pod = n个容器

=========3.ctl创建pod   

` `kubectl run myginx --image=nginx 

` `docker ps|grep myredis   --grep 检索目标行命令

=========4.配置文件创建pod

\# kubectl delete pod [podname]

apiVersion: v1

kind: Pod

metadata:

`    `labels:

`        `run : mynginx

`    `name : mynginx

spec:

`    `containers:

`        `- image: nginx

`          `name : mynginx

kubectl apply -f pod.yml

kubectl delete -f pod.yml --删除

=========5.可视化操作与pod细节

kubectl logs -f podname  --查看日志

kubectl get podname -owide  --查看ip等信息，每个pod都会被分配一个ip

kubectl get podname -w

curl ip  --访问nginx首页

集群中任意机器，任意的应用都能通过ip访问（机器内，机器外需要暴露端口）

=========6.多容器pod细节

<a name="fclc-1666465692574"></a>watch -n 1  命令                   //每隔一分钟执行一次命令

<a name="6lhj-1666457573723"></a>**使用depolyment部署应用**

<a name="uolg-1666537835973"></a>**Deployment**

` `一次部署多份

控制Pod，使Pod拥有多副本，自愈，扩缩容等能力

#清除所有Pod.比较下面两个命令有何不同效果?

` `kubectl run mynginx --image=nginx

` `#自愈能力，删了还会在其它机器启动新的，需删除部署才行

kubectl create deployment'mytomcat --image=tomcat:8.5.685

####多副本能力  yml配置

kubectl create deployment my-dep --image=nginx --replicas=3

kubectl get depoly

###删除部署

<a name="ry7a-1666537880418"></a>kubectl delete depolyment

<a name="tmur-1666537880419"></a>**工作负载 扩缩容**

\-----------

kubectl scale --replicas=5 deployment/my-dep

#修改yml replicas

kubectl edit deployment my-dep

<a name="loig-1666537966299"></a>#k8s界面

<a name="azit-1666537966300"></a>**自愈&故障转移**

\-----------

自愈：故障，杀了重启

<a name="gqdo-1666537993718"></a>转移：机器down机，另一个机器（node节点）启pod

<a name="a0cx-1666537993719"></a>**滚动更新**

-----------滚动更新

灰度发布镜像  --设置新版本号，先启新的，再杀老的

kubectl set image deployment/my-dep nginx=nginx:1.16.1 --record

kubectl rollout status deployment/my -dep  

-----------版本回退

#历史记录

kubectl rollout history deployment/my-dep

#查看某个历史详情

kubectl rollout history deployment/my-dep --revision=2

回滚(回到上次)

kubectl rollout undo deployment/my-dep

#回滚(回到指定版本)

<a name="7drv-1666538012949"></a>kubectl rollout undo deployment/my-dep --to-revision=2

<a name="j8aa-1666538012950"></a>**小结**

<a name="3yiv-1699584183808"></a>**-Deployment（无状态应用部署）**

<a name="umcd-1699584185052"></a>**-StatefulSet （有状态-登录,购物车,会话）**

<a name="dmhp-1699584186685"></a>**-DaemonSet（守护型）**

<a name="a5t8-1699584187412"></a>**-Job/CronJob（定时任务型）**

---------工作负载小结

不会直接run pod部署，而是用下面的指令按需求部署

Deployment:无状态应用部署，比如微服务，提供多副本等功能

StatefulSet:有状态应用部署，比如redis，提供稳定的存储、网络等功能，中间件等需要保存中间状态的。

DaemonSet:守护型应用部署，比如日志收集组件，在每个机器都运行一份

<a name="7wgp-1666518687556"></a>Job/CronJob:定时任务部署，比如垃圾清理组件，可以在指定时间运行

<a name="bsl0-1666518658388"></a>**服务网络Service**

<a name="tw7p-1666538089240"></a>**Service：Pod的服务发现与负载均衡**

------Service: Pod的服务发现与负载均衡

#app=my-dep（3个pod都是80端口）,集群内访问serviceip:8000,负载均衡

kubectl expose deploy my-dep --port:8000 --target-port:80   -expose暴露端口

curl serviceip:8000

#服务名service域名.所在名称空间svc

my-dep.default.svc访问：curl my-dep.default.svc

--------测试Service服务发现

-------Service暴露NodePort方式

kubectl expose deploy my-dep --port=8000 --target-port=80 --type=ClusterlP:集群内部的访问

#NodePort端口暴露范围： 30000~37670  访问：ip:nodeport

<a name="cq8q-1666538096292"></a>kubectl expose deploy my-dep --port=8000 --target-port=80 --type=NodePort:集群外也可以访问

<a name="bkbr-1666538096293"></a>**Ingress统一网关**

---------Ingres模型分析及安装

Ingres: Service的统一网关入口 -Istio？

#初始化主节点时  service层网络 10.96.0.0/16  pod层网络 192.168.0.0/16

ingres > 域名 > service > pod  -层层加中间层

Ingres 底层还是nginx，安装步骤：

wget 

vi ingress.yaml

--------Ingres实战域名访问

https://139.198.163.211:32401/ -443

http://139.198.163.211:31405/  -80

网关yaml的一些配置

-------ingress高级用法

路径重写：

kubectl editor xx

vi xxx.yaml

限流：

kubectl get ing

<a name="ajqh-1666520749397"></a>------网络模型总结

![截图.png](assets/Aspose.Words.14c6f8ef-d9ee-49fb-aada-25e4cb51c42b.013.png)

<a name="v62b-1666537723435"></a><a name="rn2j-1666537720657"></a>**存储抽象**

<a name="xxrj-1666538261122"></a>**存储层NFS**

-----数据挂载到抽象出的存储层，即使故障转移数据也没问题

Glusterfs

NFS  network file system

CephFs，

<a name="6ad0-1666537759270"></a>NFS搭建三节点，两从节点数据同步master

<a name="it4m-1666537737863"></a>**Deployment使用NFS进行挂载**

----原生方式

<a name="yb8d-1666538867972"></a>yaml配置nfs地址   优点和缺点都是：删了deploy,也不会删

<a name="co0j-1666537738457"></a>**PV与PVC**

PV:持久卷(Persistent volume)，将应用需要持久化的数据保存到指定位置

PVC:持久卷申明(Plrsistent Volume Claim),申明需要使用的持久卷规格 -申请书

PV池静态供应： 向pvc申请内存后，在pv池找到合适的。 3M 、200M、 1G

yaml配置

<a name="jbsr-1666539159907"></a>PV池动态供应

<a name="6uyw-1666539135553"></a>**ConifgMap抽取配置（挂载配置）**

--------把之前的配置文件创建为配置集 -类似配置nacos中心

#创建配置,redis保存到kas的etcd:

kubectl create cm redis-conf --from-file=redis.conf

#配置文件推荐ConfigMap挂载

1\.检查指定文件内容是否已经更新

修改了CM，Pod里面的配置文件会跟着变

2\.配置值未更改，因为需要重新启动Pod才能从关联的ConfigMap 中获取更新的值。

<a name="bpva-1666539722080"></a>原因:我们的Pod部署中间件自己本身没有热更新能力

<a name="jznb-1666539673078"></a>**Secret场景实例**

Secret对象类型用来保存敏感信息，例如密码、OAuth令牌和SSH 密钥。

<a name="lqz6-1666540562158"></a>将这些信息放在secret 中比放在Pod的定义或者容器镜像中来说更加安全和灵活。

<a name="ynvn-1666539781306"></a>**KubeSphere**

<a name="2cyh-1666621353339"></a>**平台安装**

-------混合云容器平台

Pass系统 同类型的 rancher

1\.#k8s安装kubeSphere 或者 Linux安装kubeSpher

-------安装k8s集群

安装三大件，let,admin,ctl

安装网络组件 calio, kubectl apply -f calio.yaml

--------安装默认储存类型

nfs-server ：动态pv池，动态供应

--------metric-server 集群状态监控

kubectl top pod -A

--------全功能安装

wget http:....cluster.yaml

<a name="ulsz-1666541020562"></a>需要的组件改为true

<a name="p1fm-1666540995714"></a>**Linux单节点部署KubeSphere**

<a name="ergo-1666540952093"></a>**应用部署实战**

中间件: 有状态、数据导入

微服务:  无状态、制作镜像

网络:  各种访问地址

<a name="vboj-1665932515930"></a>配置:  生产配置分离、URL

