---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943707"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="44dac-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="44dac-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="44dac-102">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="44dac-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="44dac-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="44dac-103">\<system.identityModel></span></span>  
<span data-ttu-id="44dac-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="44dac-104">\<identityConfiguration></span></span>  
<span data-ttu-id="44dac-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="44dac-105">\<caches></span></span>  
<span data-ttu-id="44dac-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="44dac-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44dac-107">구문</span><span class="sxs-lookup"><span data-stu-id="44dac-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44dac-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="44dac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44dac-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44dac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44dac-110">특성</span><span class="sxs-lookup"><span data-stu-id="44dac-110">Attributes</span></span>  
  
|<span data-ttu-id="44dac-111">특성</span><span class="sxs-lookup"><span data-stu-id="44dac-111">Attribute</span></span>|<span data-ttu-id="44dac-112">Description</span><span class="sxs-lookup"><span data-stu-id="44dac-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44dac-113">type</span><span class="sxs-lookup"><span data-stu-id="44dac-113">type</span></span>|<span data-ttu-id="44dac-114"><xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스에서 파생 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="44dac-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44dac-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="44dac-115">Child Elements</span></span>  
 <span data-ttu-id="44dac-116">없음</span><span class="sxs-lookup"><span data-stu-id="44dac-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44dac-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="44dac-117">Parent Elements</span></span>  
  
|<span data-ttu-id="44dac-118">요소</span><span class="sxs-lookup"><span data-stu-id="44dac-118">Element</span></span>|<span data-ttu-id="44dac-119">설명</span><span class="sxs-lookup"><span data-stu-id="44dac-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44dac-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="44dac-120">\<caches></span></span>](caches.md)|<span data-ttu-id="44dac-121">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="44dac-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="44dac-122">예제</span><span class="sxs-lookup"><span data-stu-id="44dac-122">Example</span></span>  
 <span data-ttu-id="44dac-123">다음 XML에서는 세션 보안 토큰을 보유 하는 사용자 지정 캐시의 구성 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44dac-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="44dac-124">이 구성은 `ClaimsAwareWebFarm` 샘플에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44dac-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="44dac-125">이 샘플에 대 한 자세한 내용은 참조 하세요. [WIF 코드 샘플 인덱스](../../../security/wif-code-sample-index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44dac-125">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44dac-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="44dac-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
