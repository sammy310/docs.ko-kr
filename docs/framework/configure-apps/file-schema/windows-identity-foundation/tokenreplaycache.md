---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5e695bb56b59da40ce9e83f9f4f77d0d22d0b40f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202424"
---
# \<tokenReplayCache>

<span data-ttu-id="c822e-101">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822e-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="c822e-102">구문</span><span class="sxs-lookup"><span data-stu-id="c822e-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c822e-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c822e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c822e-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c822e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c822e-105">특성</span><span class="sxs-lookup"><span data-stu-id="c822e-105">Attributes</span></span>  
  
|<span data-ttu-id="c822e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="c822e-106">Attribute</span></span>|<span data-ttu-id="c822e-107">Description</span><span class="sxs-lookup"><span data-stu-id="c822e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c822e-108">type</span><span class="sxs-lookup"><span data-stu-id="c822e-108">type</span></span>|<span data-ttu-id="c822e-109">클래스에서 파생 되는 형식 <xref:System.IdentityModel.Tokens.TokenReplayCache> 입니다.</span><span class="sxs-lookup"><span data-stu-id="c822e-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="c822e-110">사용자 지정을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c822e-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c822e-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c822e-111">Child Elements</span></span>  

 <span data-ttu-id="c822e-112">없음</span><span class="sxs-lookup"><span data-stu-id="c822e-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c822e-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c822e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c822e-114">요소</span><span class="sxs-lookup"><span data-stu-id="c822e-114">Element</span></span>|<span data-ttu-id="c822e-115">설명</span><span class="sxs-lookup"><span data-stu-id="c822e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="c822e-116">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c822e-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c822e-117">설명</span><span class="sxs-lookup"><span data-stu-id="c822e-117">Remarks</span></span>  

 <span data-ttu-id="c822e-118">토큰 재생 캐시는 재생 된 토큰을 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822e-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="c822e-119">토큰 재생 검색은 토큰 [\<tokenReplayDetection>](tokenreplaydetection.md) 의 최대 만료 시간을 지정 하는 요소에 의해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c822e-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c822e-120">예제</span><span class="sxs-lookup"><span data-stu-id="c822e-120">Example</span></span>  

 <span data-ttu-id="c822e-121">다음 XML에서는 재생 된 토큰을 검색 하기 위한 사용자 지정 캐시의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c822e-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c822e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c822e-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
