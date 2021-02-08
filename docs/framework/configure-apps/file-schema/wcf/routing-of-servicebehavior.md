---
description: '다음에 대 한 자세한 정보:: <routing><serviceBehavior>'
title: <serviceBehavior>의 <routing>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 1d8a056d708b3c42aeccf3e46a0703b3fc78a17d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786891"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="314a0-103">\<serviceBehavior>의 \<routing></span><span class="sxs-lookup"><span data-stu-id="314a0-103">\<routing> of \<serviceBehavior></span></span>

<span data-ttu-id="314a0-104">라우팅 서비스에 대한 런타임 액세스를 제공하여 라우팅 구성의 동적 수정을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-104">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a><span data-ttu-id="314a0-105">구문</span><span class="sxs-lookup"><span data-stu-id="314a0-105">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="314a0-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="314a0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="314a0-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="314a0-108">특성</span><span class="sxs-lookup"><span data-stu-id="314a0-108">Attributes</span></span>  
  
|<span data-ttu-id="314a0-109">attribute</span><span class="sxs-lookup"><span data-stu-id="314a0-109">Attribute</span></span>|<span data-ttu-id="314a0-110">설명</span><span class="sxs-lookup"><span data-stu-id="314a0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="314a0-111">filterTable</span><span class="sxs-lookup"><span data-stu-id="314a0-111">filterTable</span></span>|<span data-ttu-id="314a0-112">라우팅 서비스에서 평가할 필터를 포함하는 라우팅 테이블의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-112">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="314a0-113">이 값은 `name` [\<filterTable>](filtertable.md) 섹션에 있는 요소의 특성과 일치 해야 합니다 [\<filterTables>](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="314a0-113">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="314a0-114">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="314a0-114">routeOnHeaderOnly</span></span>|<span data-ttu-id="314a0-115">필터를 사용하여 메시지 본문과 헤더를 모두 검사할지 또는 헤더만 검사할지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-115">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="314a0-116">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-116">The default is `true`.</span></span>|  
|<span data-ttu-id="314a0-117">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="314a0-117">soapProcessingEnabled</span></span>|<span data-ttu-id="314a0-118">SOAP 처리가 발생해야 하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-118">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="314a0-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="314a0-119">Child Elements</span></span>  

 <span data-ttu-id="314a0-120">없음</span><span class="sxs-lookup"><span data-stu-id="314a0-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="314a0-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="314a0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="314a0-122">요소</span><span class="sxs-lookup"><span data-stu-id="314a0-122">Element</span></span>|<span data-ttu-id="314a0-123">설명</span><span class="sxs-lookup"><span data-stu-id="314a0-123">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="314a0-124">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-124">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="314a0-125">설명</span><span class="sxs-lookup"><span data-stu-id="314a0-125">Remarks</span></span>  

 <span data-ttu-id="314a0-126">이 구성 요소가 서비스 동작 구성에 추가되면 서비스에 대한 라우팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-126">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="314a0-127">서비스에서 실제로 사용할 라우팅 테이블을 이 요소에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-127">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="314a0-128">이 구성 섹션을 사용하여 배포 패턴이 변경되는 경우 즉시 라우팅 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-128">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="314a0-129">런타임에 새로운 라우팅 설정을 사용하여 직접 작성한 라우팅 확장을 등록할 수 있습니다. 이렇게 하면 진행 중인 메시지/세션은 시작 시 적용되었던 규칙을 사용하여 그대로 유지하면서 새로운 메시지 및 세션에 업데이트된 구성 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-129">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="314a0-130">따라서 런타임 동안 라우팅 서비스를 세션에 관계없이 재활용을 줄이면서 재구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314a0-130">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
