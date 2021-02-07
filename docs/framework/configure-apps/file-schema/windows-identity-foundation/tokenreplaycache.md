---
description: 다음에 대해 자세히 알아보세요. <tokenReplayCache>
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 793b1f88a9eeb0ebce4cd440e248e81377f17e9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749001"
---
# \<tokenReplayCache>

<span data-ttu-id="0f601-102">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="0f601-103">구문</span><span class="sxs-lookup"><span data-stu-id="0f601-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f601-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0f601-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0f601-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f601-106">특성</span><span class="sxs-lookup"><span data-stu-id="0f601-106">Attributes</span></span>  
  
|<span data-ttu-id="0f601-107">attribute</span><span class="sxs-lookup"><span data-stu-id="0f601-107">Attribute</span></span>|<span data-ttu-id="0f601-108">Description</span><span class="sxs-lookup"><span data-stu-id="0f601-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f601-109">type</span><span class="sxs-lookup"><span data-stu-id="0f601-109">type</span></span>|<span data-ttu-id="0f601-110">클래스에서 파생 되는 형식 <xref:System.IdentityModel.Tokens.TokenReplayCache> 입니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-110">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="0f601-111">사용자 지정을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f601-111">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="0f601-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0f601-112">Child Elements</span></span>  

 <span data-ttu-id="0f601-113">없음</span><span class="sxs-lookup"><span data-stu-id="0f601-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f601-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0f601-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0f601-115">요소</span><span class="sxs-lookup"><span data-stu-id="0f601-115">Element</span></span>|<span data-ttu-id="0f601-116">설명</span><span class="sxs-lookup"><span data-stu-id="0f601-116">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="0f601-117">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-117">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f601-118">설명</span><span class="sxs-lookup"><span data-stu-id="0f601-118">Remarks</span></span>  

 <span data-ttu-id="0f601-119">토큰 재생 캐시는 재생 된 토큰을 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-119">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="0f601-120">토큰 재생 검색은 토큰 [\<tokenReplayDetection>](tokenreplaydetection.md) 의 최대 만료 시간을 지정 하는 요소에 의해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-120">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f601-121">예제</span><span class="sxs-lookup"><span data-stu-id="0f601-121">Example</span></span>  

 <span data-ttu-id="0f601-122">다음 XML에서는 재생 된 토큰을 검색 하기 위한 사용자 지정 캐시의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-122">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f601-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f601-123">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
