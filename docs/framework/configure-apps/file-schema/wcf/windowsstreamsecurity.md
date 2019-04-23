---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113635"
---
# <a name="windowsstreamsecurity"></a>\<windowsStreamSecurity>
사용자 지정의 바인딩에 대한 Windows 스트림 보안 설정을 지정합니다.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<windowsStreamSecurity>  
  
## <a name="syntax"></a>구문  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|protectionLevel|메시지 보안 수준을 정의합니다. 메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다. 암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다. 유효한 값은 다음과 같습니다.<br /><br /> -None. 보호되지 않습니다.<br />기호: 메시지가 서명됩니다.<br />-   EncryptAndSign: 메시지 서명 및 암호화 합니다.<br /><br /> 기본값은 EncryptAndSign입니다.<br /><br /> 이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>설명  
 TCP 및 명명된 파이프와 같은 스트림 지향 프로토콜을 사용하는 전송은 스트림 기반 전송 업그레이드를 지원합니다. 특히 WCF는 보안 업그레이드를 제공합니다. 이 전송 보안의 구성은이 구성 요소에 캡슐화 [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), 구성 및 사용자 지정 바인딩에 추가할 수 있는  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [바인딩](../../../../../docs/framework/wcf/bindings.md)
- [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
