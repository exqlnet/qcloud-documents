## 操作场景
本文介绍如何将通过 TEM 部署的 Spring Cloud 应用接入微服务引擎托管的 Eureka 注册中心。接入无需修改任何代码。

## 操作步骤

1. 在 [TEM控制台](https://console.cloud.tencent.com/tem) 中创建环境。具体操作请参见 [创建环境](https://cloud.tencent.com/document/product/1371/53293)。

2. 在 [TSE 控制台](https://console.cloud.tencent.com/tse) 创建eureka注册中心实例。具体操作请参见 [创建微服务引擎实例](https://cloud.tencent.com/document/product/1364/58416)。
<dx-alert infotype="explain" title="">
创建 Eureka 注册中心实例时，若不开启公网访问，则所选定的 VPC 需要与 TEM 已创建的环境的 VPC 保持一致。
</dx-alert>

3. 在 [TEM 控制台](https://console.cloud.tencent.com/tem) 点击环境名，进入基本信息页，一键关联 TSE 中的 Eureka 注册中心。
![](https://main.qcloudimg.com/raw/5bdcd1f93e581ee419f2cbde2e75006b.jpg)

4. 在 [TEM 控制台](https://console.cloud.tencent.com/tem) 创建应用，并部署至所创建的环境。具体操作请参见 [创建并部署应用](https://cloud.tencent.com/document/product/1371/53294)。

5. 在 [TSE 控制台](https://console.cloud.tencent.com/tse) 中验证服务注册。点击进入注册中心实例的服务管理页面，若出现以下页面，则证明服务注册成功。
![](https://main.qcloudimg.com/raw/e1b01a45cd510dd765b62d183dd65eaf.png)

## 注意事项
Spring Cloud 应用接入 Eureka 注册中心，配置文件格式需如下所示：
<dx-codeblock>
:::  plaintext
eureka:
  client:
    serviceUrl:
      defaultZone: http://[eureka注册中心实例访问IP:8761]/eureka/
  instance:
    prefer-ip-address: true
:::
</dx-codeblock>


