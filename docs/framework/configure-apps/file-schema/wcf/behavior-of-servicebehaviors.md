---
description: '다음에 대 한 자세한 정보:: <behavior><serviceBehaviors>'
title: <serviceBehaviors>의 <behavior>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: e34254661026ad6dcb3429ad1b381cc3e6718f27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639538"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="5fda7-103">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="5fda7-103">\<behavior> of \<serviceBehaviors></span></span>

<span data-ttu-id="5fda7-104">`behavior` 요소는 서비스의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-104">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="5fda7-105">각 동작은 해당 `name`으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-105">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="5fda7-106">서비스는 요소의 특성을 사용 하 여이 이름을 통해 각 동작에 연결할 수 있습니다 `behaviorConfiguration` [\<endpoint>](endpoint-element.md) .</span><span class="sxs-lookup"><span data-stu-id="5fda7-106">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="5fda7-107">따라서 설정을 다시 정의하지 않고도 엔드포인트에서 일반 동작 구성을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-107">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="5fda7-108">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-108">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5fda7-109">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fda7-109">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fda7-110">요소와 같은 Windows 워크플로 작업과 관련 된 동작 요소 [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) 는 페이지 [ \<behavior> 의 \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) 에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-110">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="5fda7-111">구문</span><span class="sxs-lookup"><span data-stu-id="5fda7-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fda7-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5fda7-112">Attributes and Elements</span></span>  

 <span data-ttu-id="5fda7-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fda7-114">특성</span><span class="sxs-lookup"><span data-stu-id="5fda7-114">Attributes</span></span>  
  
|<span data-ttu-id="5fda7-115">attribute</span><span class="sxs-lookup"><span data-stu-id="5fda7-115">Attribute</span></span>|<span data-ttu-id="5fda7-116">설명</span><span class="sxs-lookup"><span data-stu-id="5fda7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5fda7-117">name</span><span class="sxs-lookup"><span data-stu-id="5fda7-117">name</span></span>|<span data-ttu-id="5fda7-118">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="5fda7-119">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="5fda7-120">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-120">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5fda7-121">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fda7-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fda7-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5fda7-122">Child Elements</span></span>  
  
|<span data-ttu-id="5fda7-123">요소</span><span class="sxs-lookup"><span data-stu-id="5fda7-123">Element</span></span>|<span data-ttu-id="5fda7-124">설명</span><span class="sxs-lookup"><span data-stu-id="5fda7-124">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|<span data-ttu-id="5fda7-125">DataContractSerializer에 대한 구성 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-125">Contains configuration data for the DataContractSerializer.</span></span>|  
|[\<persistenceProvider>](persistenceprovider.md)|<span data-ttu-id="5fda7-126">사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-126">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[\<routing>](routing-of-servicebehavior.md)|<span data-ttu-id="5fda7-127">라우팅 서비스에 대한 런타임 액세스를 제공하여 라우팅 구성의 동적 수정을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-127">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|<span data-ttu-id="5fda7-128">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-128">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|<span data-ttu-id="5fda7-129">서비스 작업에 대한 액세스 권한을 부여하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-129">Specifies settings that authorize access to service operations.</span></span>|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="5fda7-130">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-130">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[\<serviceDebug>](servicedebug.md)|<span data-ttu-id="5fda7-131">WCF (Windows Communication Foundation) 서비스에 대 한 디버깅 및 도움말 정보 기능을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-131">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[\<serviceDiscovery>](servicediscovery.md)|<span data-ttu-id="5fda7-132">서비스 엔드포인트의 검색 기능을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-132">Specifies the discoverability of service endpoints.</span></span>|  
|[\<serviceMetadata>](servicemetadata.md)|<span data-ttu-id="5fda7-133">서비스 메타데이터 및 관련 정보의 게시를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-133">Specifies the publication of service metadata and associated information.</span></span>|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|<span data-ttu-id="5fda7-134">서비스 작업 중에 보안 이벤트의 감사를 사용하도록 하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-134">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[\<serviceThrottling>](servicethrottling.md)|<span data-ttu-id="5fda7-135">WCF 서비스의 제한 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-135">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[\<serviceTimeouts>](servicetimeouts.md)|<span data-ttu-id="5fda7-136">서비스에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-136">Specifies the timeout for a service.</span></span>|  
|[\<workflowRuntime>](workflowruntime.md)|<span data-ttu-id="5fda7-137">워크플로 기반 WCF 서비스를 호스팅하기 위한 WorkflowRuntime의 인스턴스에 대 한 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-137">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="5fda7-138">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-138">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5fda7-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5fda7-139">Parent Elements</span></span>  
  
|<span data-ttu-id="5fda7-140">요소</span><span class="sxs-lookup"><span data-stu-id="5fda7-140">Element</span></span>|<span data-ttu-id="5fda7-141">설명</span><span class="sxs-lookup"><span data-stu-id="5fda7-141">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="5fda7-142">서비스 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda7-142">A collection of service behavior elements.</span></span>|
