---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252158"
---
# <a name="caches"></a><span data-ttu-id="cf695-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="cf695-101">\<caches></span></span>
<span data-ttu-id="cf695-102">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
<span data-ttu-id="cf695-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cf695-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cf695-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cf695-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cf695-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cf695-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cf695-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<캐시 >**</span><span class="sxs-lookup"><span data-stu-id="cf695-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf695-107">구문</span><span class="sxs-lookup"><span data-stu-id="cf695-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf695-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cf695-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cf695-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf695-110">특성</span><span class="sxs-lookup"><span data-stu-id="cf695-110">Attributes</span></span>  
 <span data-ttu-id="cf695-111">없음</span><span class="sxs-lookup"><span data-stu-id="cf695-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf695-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cf695-112">Child Elements</span></span>  
  
|<span data-ttu-id="cf695-113">요소</span><span class="sxs-lookup"><span data-stu-id="cf695-113">Element</span></span>|<span data-ttu-id="cf695-114">Description</span><span class="sxs-lookup"><span data-stu-id="cf695-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf695-115">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="cf695-115">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="cf695-116">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="cf695-117">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="cf695-117">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="cf695-118">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf695-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cf695-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cf695-120">요소</span><span class="sxs-lookup"><span data-stu-id="cf695-120">Element</span></span>|<span data-ttu-id="cf695-121">설명</span><span class="sxs-lookup"><span data-stu-id="cf695-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf695-122">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cf695-122">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="cf695-123">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="cf695-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cf695-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="cf695-125">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf695-126">설명</span><span class="sxs-lookup"><span data-stu-id="cf695-126">Remarks</span></span>  
 <span data-ttu-id="cf695-127">요소는 요소 아래의 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 `<securityTokenHandlerConfiguration>` 처리기 컬렉션 수준에서 지정할 수 있습니다. `<caches>`</span><span class="sxs-lookup"><span data-stu-id="cf695-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="cf695-128">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="cf695-129">합니다 `<caches>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="cf695-130">구성 된 캐시는 <xref:System.IdentityModel.Configuration.IdentityModelCaches> 클래스로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf695-131">예제</span><span class="sxs-lookup"><span data-stu-id="cf695-131">Example</span></span>  
 <span data-ttu-id="cf695-132">다음 XML에서는 세션 보안 토큰을 보유 하는 사용자 지정 캐시의 구성 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="cf695-133">이 구성은 `ClaimsAwareWebFarm` 샘플에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf695-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
