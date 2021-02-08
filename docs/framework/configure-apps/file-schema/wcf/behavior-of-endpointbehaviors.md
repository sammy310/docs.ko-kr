---
description: '다음에 대 한 자세한 정보:: <behavior><endpointBehaviors>'
title: <endpointBehaviors>의 <behavior>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: a72bb69cce96d72cdc00d48546244bdcde20271f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802335"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="611bf-103">\<endpointBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="611bf-103">\<behavior> of \<endpointBehaviors></span></span>

<span data-ttu-id="611bf-104">ph x="1" /&gt; 요소는 엔드포인트의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-104">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="611bf-105">각 동작은 해당 `name`으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-105">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="611bf-106">엔드포인트는 이 이름을 통해 각 동작에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-106">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="611bf-107">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-107">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="611bf-108">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="611bf-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="611bf-109">구문</span><span class="sxs-lookup"><span data-stu-id="611bf-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="611bf-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="611bf-110">Attributes and Elements</span></span>  

 <span data-ttu-id="611bf-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="611bf-112">특성</span><span class="sxs-lookup"><span data-stu-id="611bf-112">Attributes</span></span>  
  
|<span data-ttu-id="611bf-113">attribute</span><span class="sxs-lookup"><span data-stu-id="611bf-113">Attribute</span></span>|<span data-ttu-id="611bf-114">설명</span><span class="sxs-lookup"><span data-stu-id="611bf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="611bf-115">name</span><span class="sxs-lookup"><span data-stu-id="611bf-115">name</span></span>|<span data-ttu-id="611bf-116">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-116">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="611bf-117">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-117">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="611bf-118">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="611bf-119">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="611bf-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="611bf-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="611bf-120">Child Elements</span></span>  
  
|<span data-ttu-id="611bf-121">요소</span><span class="sxs-lookup"><span data-stu-id="611bf-121">Element</span></span>|<span data-ttu-id="611bf-122">설명</span><span class="sxs-lookup"><span data-stu-id="611bf-122">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="611bf-123">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-123">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[\<callbackDebug>](callbackdebug.md)|<span data-ttu-id="611bf-124">WCF (Windows Communication Foundation) 콜백 개체에 대 한 서비스 디버깅을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-124">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[\<callbackTimeouts>](callbacktimeouts.md)|<span data-ttu-id="611bf-125">클라이언트 콜백에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-125">Specifies the timeout for the client callback.</span></span>|  
|[\<clientVia>](clientvia.md)|<span data-ttu-id="611bf-126">메시지가 이동할 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-126">Specifies the route a message should take.</span></span>|  
|[\<dataContractSerializer>](datacontractserializer.md)|<span data-ttu-id="611bf-127">DataContractSerializer에 대한 구성 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-127">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|<span data-ttu-id="611bf-128">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-128">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[\<enableWebScript>](enablewebscript.md)|<span data-ttu-id="611bf-129">ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-129">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="611bf-130">동작은 \<webHttpBinding> 표준 바인딩 또는 바인딩 요소와 함께 사용 해야 합니다 \<webMessageEncoding> .</span><span class="sxs-lookup"><span data-stu-id="611bf-130">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="611bf-131">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-131">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[\<soapProcessing>](soapprocessing.md)|<span data-ttu-id="611bf-132">서로 다른 바인딩 형식과 메시지 버전 간에 메시지 마샬링을 위해 사용되는 클라이언트 엔드포인트 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-132">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[\<synchronousReceive>](synchronousreceive-element.md)|<span data-ttu-id="611bf-133">서비스 또는 클라이언트 애플리케이션에서 메시지 수신을 위한 런타임 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-133">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="611bf-134">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-134">It does not have any attributes or child elements.</span></span>|  
|[\<transactedBatching>](transactedbatching.md)|<span data-ttu-id="611bf-135">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-135">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[\<webHttp>](webhttp.md)|<span data-ttu-id="611bf-136">구성을 통해 엔드포인트에서 WebHttpBehavior를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-136">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="611bf-137">이 동작을 표준 바인딩과 함께 사용 하면 \<webHttpBinding> WCF 서비스에 대 한 웹 프로그래밍 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-137">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="611bf-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="611bf-138">Parent Elements</span></span>  
  
|<span data-ttu-id="611bf-139">요소</span><span class="sxs-lookup"><span data-stu-id="611bf-139">Element</span></span>|<span data-ttu-id="611bf-140">설명</span><span class="sxs-lookup"><span data-stu-id="611bf-140">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="611bf-141">엔드포인트 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="611bf-141">A collection of endpoint behavior elements.</span></span>|
