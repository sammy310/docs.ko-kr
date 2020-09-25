---
title: <endpointBehaviors>의 <behavior>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: d191b968e1c3fd1db0837ba7e03f210a1b00062d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201501"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="c37a5-102">\<endpointBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="c37a5-102">\<behavior> of \<endpointBehaviors></span></span>

<span data-ttu-id="c37a5-103">ph x="1" /&gt; 요소는 엔드포인트의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="c37a5-104">각 동작은 해당 `name`으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="c37a5-105">엔드포인트는 이 이름을 통해 각 동작에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="c37a5-106">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c37a5-107">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c37a5-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="c37a5-108">구문</span><span class="sxs-lookup"><span data-stu-id="c37a5-108">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c37a5-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c37a5-109">Attributes and Elements</span></span>  

 <span data-ttu-id="c37a5-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c37a5-111">특성</span><span class="sxs-lookup"><span data-stu-id="c37a5-111">Attributes</span></span>  
  
|<span data-ttu-id="c37a5-112">attribute</span><span class="sxs-lookup"><span data-stu-id="c37a5-112">Attribute</span></span>|<span data-ttu-id="c37a5-113">Description</span><span class="sxs-lookup"><span data-stu-id="c37a5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c37a5-114">name</span><span class="sxs-lookup"><span data-stu-id="c37a5-114">name</span></span>|<span data-ttu-id="c37a5-115">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-115">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="c37a5-116">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-116">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="c37a5-117">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-117">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c37a5-118">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c37a5-118">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c37a5-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c37a5-119">Child Elements</span></span>  
  
|<span data-ttu-id="c37a5-120">요소</span><span class="sxs-lookup"><span data-stu-id="c37a5-120">Element</span></span>|<span data-ttu-id="c37a5-121">설명</span><span class="sxs-lookup"><span data-stu-id="c37a5-121">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="c37a5-122">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-122">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[\<callbackDebug>](callbackdebug.md)|<span data-ttu-id="c37a5-123">WCF (Windows Communication Foundation) 콜백 개체에 대 한 서비스 디버깅을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-123">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[\<callbackTimeouts>](callbacktimeouts.md)|<span data-ttu-id="c37a5-124">클라이언트 콜백에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-124">Specifies the timeout for the client callback.</span></span>|  
|[\<clientVia>](clientvia.md)|<span data-ttu-id="c37a5-125">메시지가 이동할 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-125">Specifies the route a message should take.</span></span>|  
|[\<dataContractSerializer>](datacontractserializer.md)|<span data-ttu-id="c37a5-126">DataContractSerializer에 대한 구성 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-126">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|<span data-ttu-id="c37a5-127">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-127">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[\<enableWebScript>](enablewebscript.md)|<span data-ttu-id="c37a5-128">ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-128">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="c37a5-129">동작은 \<webHttpBinding> 표준 바인딩 또는 바인딩 요소와 함께 사용 해야 합니다 \<webMessageEncoding> .</span><span class="sxs-lookup"><span data-stu-id="c37a5-129">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="c37a5-130">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-130">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[\<soapProcessing>](soapprocessing.md)|<span data-ttu-id="c37a5-131">서로 다른 바인딩 형식과 메시지 버전 간에 메시지 마샬링을 위해 사용되는 클라이언트 엔드포인트 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-131">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[\<synchronousReceive>](synchronousreceive-element.md)|<span data-ttu-id="c37a5-132">서비스 또는 클라이언트 애플리케이션에서 메시지 수신을 위한 런타임 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-132">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="c37a5-133">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-133">It does not have any attributes or child elements.</span></span>|  
|[\<transactedBatching>](transactedbatching.md)|<span data-ttu-id="c37a5-134">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-134">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[\<webHttp>](webhttp.md)|<span data-ttu-id="c37a5-135">구성을 통해 엔드포인트에서 WebHttpBehavior를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-135">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="c37a5-136">이 동작을 표준 바인딩과 함께 사용 하면 \<webHttpBinding> WCF 서비스에 대 한 웹 프로그래밍 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-136">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c37a5-137">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c37a5-137">Parent Elements</span></span>  
  
|<span data-ttu-id="c37a5-138">요소</span><span class="sxs-lookup"><span data-stu-id="c37a5-138">Element</span></span>|<span data-ttu-id="c37a5-139">설명</span><span class="sxs-lookup"><span data-stu-id="c37a5-139">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="c37a5-140">엔드포인트 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c37a5-140">A collection of endpoint behavior elements.</span></span>|
