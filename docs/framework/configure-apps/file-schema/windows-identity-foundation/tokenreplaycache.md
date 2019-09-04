---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251780"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="c2784-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="c2784-101">\<tokenReplayCache></span></span>
<span data-ttu-id="c2784-102">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2784-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="c2784-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c2784-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c2784-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c2784-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c2784-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c2784-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c2784-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<캐시 >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="c2784-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="c2784-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenReplayCache >**</span><span class="sxs-lookup"><span data-stu-id="c2784-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2784-108">구문</span><span class="sxs-lookup"><span data-stu-id="c2784-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2784-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c2784-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c2784-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c2784-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2784-111">특성</span><span class="sxs-lookup"><span data-stu-id="c2784-111">Attributes</span></span>  
  
|<span data-ttu-id="c2784-112">특성</span><span class="sxs-lookup"><span data-stu-id="c2784-112">Attribute</span></span>|<span data-ttu-id="c2784-113">설명</span><span class="sxs-lookup"><span data-stu-id="c2784-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2784-114">type</span><span class="sxs-lookup"><span data-stu-id="c2784-114">type</span></span>|<span data-ttu-id="c2784-115"><xref:System.IdentityModel.Tokens.TokenReplayCache> 클래스에서 파생 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2784-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="c2784-116">사용자 지정 `type`을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2784-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c2784-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c2784-117">Child Elements</span></span>  
 <span data-ttu-id="c2784-118">없음</span><span class="sxs-lookup"><span data-stu-id="c2784-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2784-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c2784-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c2784-120">요소</span><span class="sxs-lookup"><span data-stu-id="c2784-120">Element</span></span>|<span data-ttu-id="c2784-121">설명</span><span class="sxs-lookup"><span data-stu-id="c2784-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2784-122">\<caches></span><span class="sxs-lookup"><span data-stu-id="c2784-122">\<caches></span></span>](caches.md)|<span data-ttu-id="c2784-123">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2784-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2784-124">설명</span><span class="sxs-lookup"><span data-stu-id="c2784-124">Remarks</span></span>  
 <span data-ttu-id="c2784-125">토큰 재생 캐시는 재생 된 토큰을 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2784-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="c2784-126">토큰 재생 검색은 토큰의 최대 만료 시간을 지정 하는 [ \<tokenreplaydetection >](tokenreplaydetection.md) 요소에 의해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2784-126">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2784-127">예제</span><span class="sxs-lookup"><span data-stu-id="c2784-127">Example</span></span>  
 <span data-ttu-id="c2784-128">다음 XML에서는 재생 된 토큰을 검색 하기 위한 사용자 지정 캐시의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2784-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2784-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2784-129">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="c2784-130">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="c2784-130">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
