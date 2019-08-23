---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944292"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="7271f-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="7271f-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="7271f-102">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7271f-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="7271f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7271f-103">\<system.identityModel></span></span>  
<span data-ttu-id="7271f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7271f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="7271f-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="7271f-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7271f-106">구문</span><span class="sxs-lookup"><span data-stu-id="7271f-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="7271f-107">형식</span><span class="sxs-lookup"><span data-stu-id="7271f-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7271f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7271f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7271f-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7271f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7271f-110">특성</span><span class="sxs-lookup"><span data-stu-id="7271f-110">Attributes</span></span>  
  
|<span data-ttu-id="7271f-111">특성</span><span class="sxs-lookup"><span data-stu-id="7271f-111">Attribute</span></span>|<span data-ttu-id="7271f-112">설명</span><span class="sxs-lookup"><span data-stu-id="7271f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7271f-113">사용</span><span class="sxs-lookup"><span data-stu-id="7271f-113">enabled</span></span>|<span data-ttu-id="7271f-114">토큰 재생 검색이 사용 되는지 여부를 지정 하는 값입니다. 토큰 재생 검색을 사용 하도록 설정 하려면 "true"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7271f-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="7271f-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="7271f-115">expirationPeriod</span></span>|<span data-ttu-id="7271f-116">항목이 만료 된 것으로 간주 되 고 캐시에서 제거 되기 전 까지의 최대 시간을 지정 하는입니다.<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="7271f-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="7271f-117">값을 지정 <xref:System.TimeSpan> 하는 방법에 대 한 자세한 내용은 [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7271f-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7271f-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7271f-118">Child Elements</span></span>  
 <span data-ttu-id="7271f-119">없음</span><span class="sxs-lookup"><span data-stu-id="7271f-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7271f-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7271f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7271f-121">요소</span><span class="sxs-lookup"><span data-stu-id="7271f-121">Element</span></span>|<span data-ttu-id="7271f-122">설명</span><span class="sxs-lookup"><span data-stu-id="7271f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7271f-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7271f-123">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="7271f-124">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7271f-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="7271f-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="7271f-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="7271f-126">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7271f-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7271f-127">설명</span><span class="sxs-lookup"><span data-stu-id="7271f-127">Remarks</span></span>  
 <span data-ttu-id="7271f-128">요소는 요소 아래의 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 `<securityTokenHandlerConfiguration>` 처리기 컬렉션 수준에서 지정할 수 있습니다. `<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="7271f-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="7271f-129">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7271f-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="7271f-130">토큰 재생 캐시의 유형은 [ \<tokenreplaycache >](tokenreplaycache.md) 요소에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7271f-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
