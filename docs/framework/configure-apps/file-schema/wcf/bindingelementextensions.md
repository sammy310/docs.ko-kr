---
description: 다음에 대해 자세히 알아보세요. <bindingElementExtensions>
title: <bindingElementExtensions>
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: 4c1b4b924906b1a6dc143588a057129ca5ce8f40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639421"
---
# \<bindingElementExtensions>

이 섹션은 시스템 또는 애플리케이션 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다. `add` 키워드를 사용하고 요소의 `type` 특성을 바인딩 요소 확장으로, `name` 특성을 사용자 지정 바인딩 요소로 설정하여 사용자 지정 바인딩 요소를 이 컬렉션에 추가할 수 있습니다.  
  
 바인딩 확장을 사용하면 사용자 지정 바인딩에 사용할 사용자 정의 바인딩 요소를 만들 수 있습니다. 프로그래밍에서 바인딩 확장은 추상 클래스 <xref:System.ServiceModel.Channels.BindingElement>을 구현하는 형식입니다. 구성 파일에서 `bindingElementExtensions` 섹션을 사용하여 확장명 요소를 정의합니다.  
  
 다음 예제에서는 `add` 요소와 `name` 특성을 사용하여 구성 파일의 `bindingElementExtensions` 섹션에 바인딩 확장을 추가합니다.  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingElementExtensions>
      <add name="udpTransport"
           type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingElementExtensions>
  </extensions>
</system.serviceModel>
```  
  
 요소에 구성 기능을 추가하려면 `bindingElementExtensionSection` 요소를 작성하고 등록해야 합니다. 이에 대한 자세한 내용은 <xref:System.Configuration> 설명서를 참조하세요.  
  
 요소 및 해당 구성 형식이 정의되면 다음 예제와 같이 확장을 사용자 지정 바인딩의 일부로 사용할 수 있습니다.  
  
```xml  
<customBinding>
  <binding name="test2">
    <udpTransport />
    <binaryMessageEncoding maxReadPoolSize="211"
                           maxWritePoolSize="2132"
                           maxSessionSize="3141" />
  </binding>
</customBinding>
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>
- [바인딩 확장명](../../../wcf/extending/extending-bindings.md)
