---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944071"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="8f611-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="8f611-101">\<tokenReplayCache></span></span>
<span data-ttu-id="8f611-102">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f611-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="8f611-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8f611-103">\<system.identityModel></span></span>  
<span data-ttu-id="8f611-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8f611-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8f611-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="8f611-105">\<caches></span></span>  
<span data-ttu-id="8f611-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="8f611-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f611-107">구문</span><span class="sxs-lookup"><span data-stu-id="8f611-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f611-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8f611-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8f611-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8f611-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f611-110">특성</span><span class="sxs-lookup"><span data-stu-id="8f611-110">Attributes</span></span>  
  
|<span data-ttu-id="8f611-111">특성</span><span class="sxs-lookup"><span data-stu-id="8f611-111">Attribute</span></span>|<span data-ttu-id="8f611-112">Description</span><span class="sxs-lookup"><span data-stu-id="8f611-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f611-113">type</span><span class="sxs-lookup"><span data-stu-id="8f611-113">type</span></span>|<span data-ttu-id="8f611-114"><xref:System.IdentityModel.Tokens.TokenReplayCache> 클래스에서 파생 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f611-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="8f611-115">사용자 지정 `type`을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f611-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="8f611-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8f611-116">Child Elements</span></span>  
 <span data-ttu-id="8f611-117">없음</span><span class="sxs-lookup"><span data-stu-id="8f611-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f611-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8f611-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8f611-119">요소</span><span class="sxs-lookup"><span data-stu-id="8f611-119">Element</span></span>|<span data-ttu-id="8f611-120">설명</span><span class="sxs-lookup"><span data-stu-id="8f611-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f611-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="8f611-121">\<caches></span></span>](caches.md)|<span data-ttu-id="8f611-122">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f611-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f611-123">설명</span><span class="sxs-lookup"><span data-stu-id="8f611-123">Remarks</span></span>  
 <span data-ttu-id="8f611-124">토큰 재생 캐시는 재생 된 토큰을 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f611-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="8f611-125">토큰 재생 검색은 토큰의 최대 만료 시간을 지정 하는 [ \<tokenreplaydetection >](tokenreplaydetection.md) 요소에 의해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f611-125">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f611-126">예제</span><span class="sxs-lookup"><span data-stu-id="8f611-126">Example</span></span>  
 <span data-ttu-id="8f611-127">다음 XML에서는 재생 된 토큰을 검색 하기 위한 사용자 지정 캐시의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f611-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f611-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="8f611-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="8f611-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="8f611-129">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
