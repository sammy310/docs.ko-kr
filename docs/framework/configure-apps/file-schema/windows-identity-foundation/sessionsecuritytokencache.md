---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207801"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="80430-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="80430-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="80430-102">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="80430-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="80430-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="80430-103">\<system.identityModel></span></span>  
<span data-ttu-id="80430-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="80430-104">\<identityConfiguration></span></span>  
<span data-ttu-id="80430-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="80430-105">\<caches></span></span>  
<span data-ttu-id="80430-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="80430-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80430-107">구문</span><span class="sxs-lookup"><span data-stu-id="80430-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80430-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="80430-108">Attributes and Elements</span></span>  
 <span data-ttu-id="80430-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80430-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80430-110">특성</span><span class="sxs-lookup"><span data-stu-id="80430-110">Attributes</span></span>  
  
|<span data-ttu-id="80430-111">특성</span><span class="sxs-lookup"><span data-stu-id="80430-111">Attribute</span></span>|<span data-ttu-id="80430-112">설명</span><span class="sxs-lookup"><span data-stu-id="80430-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80430-113">type</span><span class="sxs-lookup"><span data-stu-id="80430-113">type</span></span>|<span data-ttu-id="80430-114">형식에서 파생 되는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80430-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80430-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="80430-115">Child Elements</span></span>  
 <span data-ttu-id="80430-116">없음</span><span class="sxs-lookup"><span data-stu-id="80430-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80430-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="80430-117">Parent Elements</span></span>  
  
|<span data-ttu-id="80430-118">요소</span><span class="sxs-lookup"><span data-stu-id="80430-118">Element</span></span>|<span data-ttu-id="80430-119">설명</span><span class="sxs-lookup"><span data-stu-id="80430-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80430-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="80430-120">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="80430-121">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="80430-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80430-122">예제</span><span class="sxs-lookup"><span data-stu-id="80430-122">Example</span></span>  
 <span data-ttu-id="80430-123">다음 XML 세션 보안 토큰을 보관 하기 위한 사용자 지정 캐시 구성을 보여 줍니다 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="80430-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="80430-124">구성에서 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="80430-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="80430-125">이 샘플에 대 한 자세한 내용은 참조 하세요. [WIF 코드 샘플 인덱스](../../../../../docs/framework/security/wif-code-sample-index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80430-125">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80430-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="80430-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
