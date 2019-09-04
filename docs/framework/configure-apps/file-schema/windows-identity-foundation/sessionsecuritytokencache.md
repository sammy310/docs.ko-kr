---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: e949b16f76f20191b84bbbbb6e8b019d913316f0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251837"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="328c2-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="328c2-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="328c2-102">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="328c2-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="328c2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="328c2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="328c2-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="328c2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="328c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="328c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="328c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<캐시 >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="328c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="328c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sessionSecurityTokenCache >**</span><span class="sxs-lookup"><span data-stu-id="328c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328c2-108">구문</span><span class="sxs-lookup"><span data-stu-id="328c2-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="328c2-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="328c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="328c2-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="328c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="328c2-111">특성</span><span class="sxs-lookup"><span data-stu-id="328c2-111">Attributes</span></span>  
  
|<span data-ttu-id="328c2-112">특성</span><span class="sxs-lookup"><span data-stu-id="328c2-112">Attribute</span></span>|<span data-ttu-id="328c2-113">Description</span><span class="sxs-lookup"><span data-stu-id="328c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="328c2-114">type</span><span class="sxs-lookup"><span data-stu-id="328c2-114">type</span></span>|<span data-ttu-id="328c2-115"><xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스에서 파생 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="328c2-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="328c2-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="328c2-116">Child Elements</span></span>  
 <span data-ttu-id="328c2-117">없음</span><span class="sxs-lookup"><span data-stu-id="328c2-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="328c2-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="328c2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="328c2-119">요소</span><span class="sxs-lookup"><span data-stu-id="328c2-119">Element</span></span>|<span data-ttu-id="328c2-120">Description</span><span class="sxs-lookup"><span data-stu-id="328c2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="328c2-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="328c2-121">\<caches></span></span>](caches.md)|<span data-ttu-id="328c2-122">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="328c2-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="328c2-123">예제</span><span class="sxs-lookup"><span data-stu-id="328c2-123">Example</span></span>  
 <span data-ttu-id="328c2-124">다음 XML에서는 세션 보안 토큰을 보유 하는 사용자 지정 캐시의 구성 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="328c2-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="328c2-125">이 구성은 `ClaimsAwareWebFarm` 샘플에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="328c2-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="328c2-126">이 샘플에 대 한 자세한 내용은 참조 하세요. [WIF 코드 샘플 인덱스](../../../security/wif-code-sample-index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="328c2-126">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="328c2-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="328c2-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
