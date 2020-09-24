---
title: <netNamedPipeBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 1a231a60d29cc6a4460de69a98753c23c0386027
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170040"
---
# <a name="security-of-netnamedpipebinding"></a>\<netNamedPipeBinding>의 \<security>

바인딩에 대한 보안 설정을 정의합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|mode|이 바인딩에 적용되는 보안 형식을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -없음: 보안을 사용 하지 않습니다.<br />-전송: 보안은 기본 전송 기반 보안을 사용 하 여 제공 됩니다. 이 모드에서는 보호 수준을 제어할 수 있습니다.<br />-기본값은 Transport입니다. 이 특성은 <xref:System.ServiceModel.NetNamedPipeSecurityMode> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|교통|전송의 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|바인딩|의 바인딩 요소 [\<netNamedPipeBinding>](netnamedpipebinding.md) 입니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
- [자격 증명 형식 선택](../../../wcf/feature-details/selecting-a-credential-type.md)
- [바인딩하](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
