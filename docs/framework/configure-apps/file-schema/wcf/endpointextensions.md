---
description: 다음에 대해 자세히 알아보세요. <endpointExtensions>
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: d9684ccfab868b1b0d5fe9e054a3a97912712324
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664758"
---
# \<endpointExtensions>

<span data-ttu-id="e8031-102">이 섹션에서는 새 표준 엔드포인트를 컴퓨터 또는 애플리케이션 구성 파일의 extensions 섹션에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e8031-102">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="e8031-103">ph x="1" /&gt; 키워드를 사용하고 요소의 `type` 특성을 해당 엔드포인트 형식으로 설정하고, `name` 특성을 표준 엔드포인트의 이름으로 설정하여 표준 엔드포인트를 이 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8031-103">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="e8031-104">다음 예제에서는 `add` 요소와 `name` 특성을 사용하여 구성 파일의 `<endpointExtensions>` 섹션에 표준 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e8031-104">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="e8031-105">표준 엔드포인트를 등록한 다음 이를 다음 예제와 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8031-105">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="e8031-106">요소에서 [\<endpoint>](endpoint-element.md) `kind` 특성은 섹션에 등록 된 표준 끝점 형식을 지정 합니다 `<endpointExtensions>` .</span><span class="sxs-lookup"><span data-stu-id="e8031-106">In the [\<endpoint>](endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="e8031-107">`endpointConfiguration`특성은 `name` 섹션의 표준 끝점에 대 한 구성 요소의 특성과 동일 합니다 `<standardEndpoints>` .</span><span class="sxs-lookup"><span data-stu-id="e8031-107">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
