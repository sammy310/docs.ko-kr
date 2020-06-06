---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398014"
---
# \<endpointDiscovery>
<span data-ttu-id="ac67b-101">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="ac67b-102">구문</span><span class="sxs-lookup"><span data-stu-id="ac67b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac67b-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ac67b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ac67b-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac67b-105">특성</span><span class="sxs-lookup"><span data-stu-id="ac67b-105">Attributes</span></span>  
  
|<span data-ttu-id="ac67b-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ac67b-106">Attribute</span></span>|<span data-ttu-id="ac67b-107">Description</span><span class="sxs-lookup"><span data-stu-id="ac67b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac67b-108">사용</span><span class="sxs-lookup"><span data-stu-id="ac67b-108">enabled</span></span>|<span data-ttu-id="ac67b-109">이 끝점에서 검색 기능이 사용 되는지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="ac67b-110">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac67b-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ac67b-111">Child Elements</span></span>  
  
|<span data-ttu-id="ac67b-112">요소</span><span class="sxs-lookup"><span data-stu-id="ac67b-112">Element</span></span>|<span data-ttu-id="ac67b-113">Description</span><span class="sxs-lookup"><span data-stu-id="ac67b-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="ac67b-114">엔드포인트에 대한 범위 URI의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="ac67b-115">단일 엔드포인트에 둘 이상의 범위 URI를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="ac67b-116">[\<extensions>](extensions.md)[of \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="ac67b-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="ac67b-117">엔드포인트에 대해 게시되는 사용자 지정 메타데이터를 지정할 수 있는 XML 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="ac67b-118">검색할 인터페이스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac67b-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ac67b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ac67b-120">요소</span><span class="sxs-lookup"><span data-stu-id="ac67b-120">Element</span></span>|<span data-ttu-id="ac67b-121">Description</span><span class="sxs-lookup"><span data-stu-id="ac67b-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ac67b-122">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="ac67b-123">설명</span><span class="sxs-lookup"><span data-stu-id="ac67b-123">Remarks</span></span>  
 <span data-ttu-id="ac67b-124">엔드포인트의 동작 구성에 추가되고 `enabled` 특성이 `true`로 설정되면 이 구성 요소에 대한 검색 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="ac67b-125">또한 자식 요소를 사용 하 여 [\<scopes>](scopes.md) 쿼리 중에 서비스 끝점을 필터링 하는 데 사용할 수 있는 사용자 지정 범위 uri를 지정 하 고, [\<extensions>](extensions.md) 표준 검색 가능 메타 데이터 (EPR, ContractTypeName, Bindingname, Scope 및 ListenURI)와 함께 게시 되어야 하는 사용자 지정 메타 데이터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="ac67b-126">이 구성 요소는 검색 기능에 [\<serviceDiscovery>](servicediscovery.md) 대 한 서비스 수준 제어를 제공 하는 요소에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="ac67b-127">즉, 구성에가 없는 경우에는이 요소의 설정이 무시 됩니다 [\<serviceDiscovery>](servicediscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="ac67b-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac67b-128">예제</span><span class="sxs-lookup"><span data-stu-id="ac67b-128">Example</span></span>  
 <span data-ttu-id="ac67b-129">다음 구성 예제에서는 필터링 범위 및 엔드포인트에 게시되는 확장 메타데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac67b-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac67b-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac67b-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
