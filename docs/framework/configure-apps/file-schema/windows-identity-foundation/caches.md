---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750789"
---
# <a name="caches"></a><span data-ttu-id="61200-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="61200-101">\<caches></span></span>
<span data-ttu-id="61200-102">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="61200-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="61200-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="61200-103">\<system.identityModel></span></span>  
<span data-ttu-id="61200-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="61200-104">\<identityConfiguration></span></span>  
<span data-ttu-id="61200-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="61200-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61200-106">구문</span><span class="sxs-lookup"><span data-stu-id="61200-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61200-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="61200-107">Attributes and Elements</span></span>  
 <span data-ttu-id="61200-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61200-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61200-109">특성</span><span class="sxs-lookup"><span data-stu-id="61200-109">Attributes</span></span>  
 <span data-ttu-id="61200-110">없음</span><span class="sxs-lookup"><span data-stu-id="61200-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61200-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="61200-111">Child Elements</span></span>  
  
|<span data-ttu-id="61200-112">요소</span><span class="sxs-lookup"><span data-stu-id="61200-112">Element</span></span>|<span data-ttu-id="61200-113">설명</span><span class="sxs-lookup"><span data-stu-id="61200-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61200-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="61200-114">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="61200-115">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="61200-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="61200-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="61200-116">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="61200-117">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="61200-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61200-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="61200-118">Parent Elements</span></span>  
  
|<span data-ttu-id="61200-119">요소</span><span class="sxs-lookup"><span data-stu-id="61200-119">Element</span></span>|<span data-ttu-id="61200-120">설명</span><span class="sxs-lookup"><span data-stu-id="61200-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61200-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="61200-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="61200-122">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61200-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="61200-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="61200-123">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="61200-124">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61200-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61200-125">설명</span><span class="sxs-lookup"><span data-stu-id="61200-125">Remarks</span></span>  
 <span data-ttu-id="61200-126">`<caches>` 요소 아래에 있는 서비스 수준에서 지정할 수 있습니다 합니다 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준에서는 `<securityTokenHandlerConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="61200-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="61200-127">서비스에 지정 된 토큰 처리기 컬렉션의 설정을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="61200-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="61200-128">합니다 `<caches>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="61200-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="61200-129">구성 된 캐시 표시 됩니다는 <xref:System.IdentityModel.Configuration.IdentityModelCaches> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="61200-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61200-130">예제</span><span class="sxs-lookup"><span data-stu-id="61200-130">Example</span></span>  
 <span data-ttu-id="61200-131">다음 XML 세션 보안 토큰을 보관 하기 위한 사용자 지정 캐시 구성을 보여 줍니다 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="61200-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="61200-132">구성에서 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="61200-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
