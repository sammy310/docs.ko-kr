---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1567c669b5e682a7a771d7bedc95a8effa474e36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113388"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="92e68-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="92e68-101">\<tokenReplayCache></span></span>
<span data-ttu-id="92e68-102">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="92e68-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="92e68-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="92e68-103">\<system.identityModel></span></span>  
<span data-ttu-id="92e68-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="92e68-104">\<identityConfiguration></span></span>  
<span data-ttu-id="92e68-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="92e68-105">\<caches></span></span>  
<span data-ttu-id="92e68-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="92e68-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e68-107">구문</span><span class="sxs-lookup"><span data-stu-id="92e68-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92e68-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="92e68-108">Attributes and Elements</span></span>  
 <span data-ttu-id="92e68-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92e68-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92e68-110">특성</span><span class="sxs-lookup"><span data-stu-id="92e68-110">Attributes</span></span>  
  
|<span data-ttu-id="92e68-111">특성</span><span class="sxs-lookup"><span data-stu-id="92e68-111">Attribute</span></span>|<span data-ttu-id="92e68-112">설명</span><span class="sxs-lookup"><span data-stu-id="92e68-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92e68-113">type</span><span class="sxs-lookup"><span data-stu-id="92e68-113">type</span></span>|<span data-ttu-id="92e68-114">형식에서 파생 되는 <xref:System.IdentityModel.Tokens.TokenReplayCache> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="92e68-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="92e68-115">사용자 지정 하는 방법에 대 한 자세한 내용은 `type`, [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92e68-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="92e68-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="92e68-116">Child Elements</span></span>  
 <span data-ttu-id="92e68-117">없음</span><span class="sxs-lookup"><span data-stu-id="92e68-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92e68-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="92e68-118">Parent Elements</span></span>  
  
|<span data-ttu-id="92e68-119">요소</span><span class="sxs-lookup"><span data-stu-id="92e68-119">Element</span></span>|<span data-ttu-id="92e68-120">설명</span><span class="sxs-lookup"><span data-stu-id="92e68-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92e68-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="92e68-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="92e68-122">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="92e68-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92e68-123">설명</span><span class="sxs-lookup"><span data-stu-id="92e68-123">Remarks</span></span>  
 <span data-ttu-id="92e68-124">재생 된 토큰을 검색 하는 토큰 재생 캐시가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92e68-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="92e68-125">토큰 재생 검색이 사용 되는 [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) 도 토큰에 대 한 최대 만료 시간을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92e68-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92e68-126">예제</span><span class="sxs-lookup"><span data-stu-id="92e68-126">Example</span></span>  
 <span data-ttu-id="92e68-127">다음 XML 재생 된 토큰을 검색 하는 것에 대 한 사용자 지정 캐시의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92e68-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92e68-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="92e68-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="92e68-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="92e68-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
