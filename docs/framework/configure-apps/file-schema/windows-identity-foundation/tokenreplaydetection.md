---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251767"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="c54b8-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="c54b8-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="c54b8-102">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54b8-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
<span data-ttu-id="c54b8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c54b8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c54b8-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c54b8-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c54b8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c54b8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c54b8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenReplayDetection >**</span><span class="sxs-lookup"><span data-stu-id="c54b8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c54b8-107">구문</span><span class="sxs-lookup"><span data-stu-id="c54b8-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="c54b8-108">형식</span><span class="sxs-lookup"><span data-stu-id="c54b8-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c54b8-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c54b8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c54b8-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c54b8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c54b8-111">특성</span><span class="sxs-lookup"><span data-stu-id="c54b8-111">Attributes</span></span>  
  
|<span data-ttu-id="c54b8-112">특성</span><span class="sxs-lookup"><span data-stu-id="c54b8-112">Attribute</span></span>|<span data-ttu-id="c54b8-113">설명</span><span class="sxs-lookup"><span data-stu-id="c54b8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c54b8-114">enabled</span><span class="sxs-lookup"><span data-stu-id="c54b8-114">enabled</span></span>|<span data-ttu-id="c54b8-115">토큰 재생 검색이 사용 되는지 여부를 지정 하는 값입니다. 토큰 재생 검색을 사용 하도록 설정 하려면 "true"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54b8-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="c54b8-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="c54b8-116">expirationPeriod</span></span>|<span data-ttu-id="c54b8-117">항목이 만료 된 것으로 간주 되 고 캐시에서 제거 되기 전 까지의 최대 시간을 지정 하는입니다.<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="c54b8-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="c54b8-118">값을 지정 <xref:System.TimeSpan> 하는 방법에 대 한 자세한 내용은 [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c54b8-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c54b8-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c54b8-119">Child Elements</span></span>  
 <span data-ttu-id="c54b8-120">없음</span><span class="sxs-lookup"><span data-stu-id="c54b8-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c54b8-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c54b8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c54b8-122">요소</span><span class="sxs-lookup"><span data-stu-id="c54b8-122">Element</span></span>|<span data-ttu-id="c54b8-123">설명</span><span class="sxs-lookup"><span data-stu-id="c54b8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c54b8-124">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c54b8-124">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="c54b8-125">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54b8-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="c54b8-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="c54b8-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="c54b8-127">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54b8-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c54b8-128">설명</span><span class="sxs-lookup"><span data-stu-id="c54b8-128">Remarks</span></span>  
 <span data-ttu-id="c54b8-129">요소는 요소 아래의 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 `<securityTokenHandlerConfiguration>` 처리기 컬렉션 수준에서 지정할 수 있습니다. `<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="c54b8-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="c54b8-130">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c54b8-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="c54b8-131">토큰 재생 캐시의 유형은 [ \<tokenreplaycache >](tokenreplaycache.md) 요소에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c54b8-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
