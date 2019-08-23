---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941973"
---
# <a name="caches"></a><span data-ttu-id="ffb44-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="ffb44-101">\<caches></span></span>
<span data-ttu-id="ffb44-102">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="ffb44-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ffb44-103">\<system.identityModel></span></span>  
<span data-ttu-id="ffb44-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ffb44-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ffb44-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="ffb44-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb44-106">구문</span><span class="sxs-lookup"><span data-stu-id="ffb44-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffb44-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ffb44-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ffb44-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffb44-109">특성</span><span class="sxs-lookup"><span data-stu-id="ffb44-109">Attributes</span></span>  
 <span data-ttu-id="ffb44-110">없음</span><span class="sxs-lookup"><span data-stu-id="ffb44-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ffb44-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ffb44-111">Child Elements</span></span>  
  
|<span data-ttu-id="ffb44-112">요소</span><span class="sxs-lookup"><span data-stu-id="ffb44-112">Element</span></span>|<span data-ttu-id="ffb44-113">설명</span><span class="sxs-lookup"><span data-stu-id="ffb44-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffb44-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="ffb44-114">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="ffb44-115">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="ffb44-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="ffb44-116">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="ffb44-117">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ffb44-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ffb44-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ffb44-119">요소</span><span class="sxs-lookup"><span data-stu-id="ffb44-119">Element</span></span>|<span data-ttu-id="ffb44-120">설명</span><span class="sxs-lookup"><span data-stu-id="ffb44-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffb44-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ffb44-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ffb44-122">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ffb44-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="ffb44-123">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ffb44-124">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffb44-125">설명</span><span class="sxs-lookup"><span data-stu-id="ffb44-125">Remarks</span></span>  
 <span data-ttu-id="ffb44-126">요소는 요소 아래의 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 `<securityTokenHandlerConfiguration>` 처리기 컬렉션 수준에서 지정할 수 있습니다. `<caches>`</span><span class="sxs-lookup"><span data-stu-id="ffb44-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ffb44-127">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="ffb44-128">합니다 `<caches>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="ffb44-129">구성 된 캐시는 <xref:System.IdentityModel.Configuration.IdentityModelCaches> 클래스로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffb44-130">예제</span><span class="sxs-lookup"><span data-stu-id="ffb44-130">Example</span></span>  
 <span data-ttu-id="ffb44-131">다음 XML에서는 세션 보안 토큰을 보유 하는 사용자 지정 캐시의 구성 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="ffb44-132">이 구성은 `ClaimsAwareWebFarm` 샘플에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffb44-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
