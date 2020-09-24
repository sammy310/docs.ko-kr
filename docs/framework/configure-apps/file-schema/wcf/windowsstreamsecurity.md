---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 3c82bd81bd0fabf10f2dd835188b346f62d038b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167082"
---
# \<windowsStreamSecurity>

사용자 지정의 바인딩에 대한 Windows 스트림 보안 설정을 지정합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|protectionLevel|메시지 보안 수준을 정의합니다. 메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다. 암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다. 유효한 값은 다음과 같습니다.<br /><br /> -없음: 보호 되지 않습니다.<br />-서명: 메시지가 서명 됩니다.<br />-EncryptAndSign: 메시지는 서명 되 고 암호화 됩니다.<br /><br /> 기본값은 EncryptAndSign입니다.<br /><br /> 이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>설명  

 TCP 및 명명된 파이프와 같은 스트림 지향 프로토콜을 사용하는 전송은 스트림 기반 전송 업그레이드를 지원합니다. 특히 WCF는 보안 업그레이드를 제공합니다. 이 전송 보안의 구성은이 구성 요소 뿐만 아니라 [\<sslStreamSecurity>](sslstreamsecurity.md) 사용자 지정 바인딩에 구성 및 추가 될 수 있는에 의해 캡슐화 됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [바인딩하](../../../wcf/bindings.md)
- [바인딩 확장명](../../../wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
