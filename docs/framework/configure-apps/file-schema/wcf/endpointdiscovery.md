---
description: 다음에 대해 자세히 알아보세요. <endpointDiscovery>
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 01913de37ae426484d5bb1ff6a815a64302024fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782132"
---
# \<endpointDiscovery>

<span data-ttu-id="4222b-102">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="4222b-103">구문</span><span class="sxs-lookup"><span data-stu-id="4222b-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4222b-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4222b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="4222b-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4222b-106">특성</span><span class="sxs-lookup"><span data-stu-id="4222b-106">Attributes</span></span>  
  
|<span data-ttu-id="4222b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="4222b-107">Attribute</span></span>|<span data-ttu-id="4222b-108">설명</span><span class="sxs-lookup"><span data-stu-id="4222b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4222b-109">사용</span><span class="sxs-lookup"><span data-stu-id="4222b-109">enabled</span></span>|<span data-ttu-id="4222b-110">이 끝점에서 검색 기능이 사용 되는지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-110">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="4222b-111">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-111">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4222b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4222b-112">Child Elements</span></span>  
  
|<span data-ttu-id="4222b-113">요소</span><span class="sxs-lookup"><span data-stu-id="4222b-113">Element</span></span>|<span data-ttu-id="4222b-114">설명</span><span class="sxs-lookup"><span data-stu-id="4222b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="4222b-115">엔드포인트에 대한 범위 URI의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-115">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="4222b-116">단일 엔드포인트에 둘 이상의 범위 URI를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-116">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="4222b-117">[\<extensions>](extensions.md) [of \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="4222b-117">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="4222b-118">엔드포인트에 대해 게시되는 사용자 지정 메타데이터를 지정할 수 있는 XML 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-118">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="4222b-119">검색할 인터페이스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-119">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4222b-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4222b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4222b-121">요소</span><span class="sxs-lookup"><span data-stu-id="4222b-121">Element</span></span>|<span data-ttu-id="4222b-122">설명</span><span class="sxs-lookup"><span data-stu-id="4222b-122">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4222b-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-123">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="4222b-124">설명</span><span class="sxs-lookup"><span data-stu-id="4222b-124">Remarks</span></span>  

 <span data-ttu-id="4222b-125">엔드포인트의 동작 구성에 추가되고 `enabled` 특성이 `true`로 설정되면 이 구성 요소에 대한 검색 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-125">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="4222b-126">또한 자식 요소를 사용 하 여 [\<scopes>](scopes.md) 쿼리 중에 서비스 끝점을 필터링 하는 데 사용할 수 있는 사용자 지정 범위 uri를 지정 하 고, [\<extensions>](extensions.md) 표준 검색 가능 메타 데이터 (EPR, ContractTypeName, Bindingname, Scope 및 ListenURI)와 함께 게시 되어야 하는 사용자 지정 메타 데이터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-126">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="4222b-127">이 구성 요소는 검색 기능에 [\<serviceDiscovery>](servicediscovery.md) 대 한 서비스 수준 제어를 제공 하는 요소에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-127">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="4222b-128">즉, 구성에가 없는 경우에는이 요소의 설정이 무시 됩니다 [\<serviceDiscovery>](servicediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="4222b-128">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4222b-129">예제</span><span class="sxs-lookup"><span data-stu-id="4222b-129">Example</span></span>  

 <span data-ttu-id="4222b-130">다음 구성 예제에서는 필터링 범위 및 엔드포인트에 게시되는 확장 메타데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4222b-130">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="4222b-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4222b-131">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
