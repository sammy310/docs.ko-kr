---
description: 다음에 대해 자세히 알아보세요. <caches>
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: ebc2fa66ab8b657f7cc3741668c9f27fc60510b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681840"
---
# \<caches>

<span data-ttu-id="89dda-102">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="89dda-103">구문</span><span class="sxs-lookup"><span data-stu-id="89dda-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89dda-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="89dda-104">Attributes and Elements</span></span>  

 <span data-ttu-id="89dda-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89dda-106">특성</span><span class="sxs-lookup"><span data-stu-id="89dda-106">Attributes</span></span>  

 <span data-ttu-id="89dda-107">None</span><span class="sxs-lookup"><span data-stu-id="89dda-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89dda-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="89dda-108">Child Elements</span></span>  
  
|<span data-ttu-id="89dda-109">요소</span><span class="sxs-lookup"><span data-stu-id="89dda-109">Element</span></span>|<span data-ttu-id="89dda-110">설명</span><span class="sxs-lookup"><span data-stu-id="89dda-110">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="89dda-111">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-111">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="89dda-112">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-112">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89dda-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="89dda-113">Parent Elements</span></span>  
  
|<span data-ttu-id="89dda-114">요소</span><span class="sxs-lookup"><span data-stu-id="89dda-114">Element</span></span>|<span data-ttu-id="89dda-115">설명</span><span class="sxs-lookup"><span data-stu-id="89dda-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="89dda-116">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-116">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="89dda-117">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-117">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89dda-118">설명</span><span class="sxs-lookup"><span data-stu-id="89dda-118">Remarks</span></span>  

 <span data-ttu-id="89dda-119">요소는 요소 아래의 `<caches>` 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 처리기 컬렉션 수준에서 지정할 수 있습니다 `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="89dda-119">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="89dda-120">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-120">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="89dda-121">합니다 `<caches>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="89dda-121">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="89dda-122">구성 된 캐시는 클래스로 표시 됩니다 <xref:System.IdentityModel.Configuration.IdentityModelCaches> .</span><span class="sxs-lookup"><span data-stu-id="89dda-122">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89dda-123">예제</span><span class="sxs-lookup"><span data-stu-id="89dda-123">Example</span></span>  

 <span data-ttu-id="89dda-124">다음 XML에서는 세션 보안 토큰을 보유 하는 사용자 지정 캐시의 구성 ()을 보여 줍니다 <xref:System.IdentityModel.Tokens.SessionSecurityToken> .</span><span class="sxs-lookup"><span data-stu-id="89dda-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="89dda-125">이 구성은 샘플에서 가져온 것입니다 `ClaimsAwareWebFarm` .</span><span class="sxs-lookup"><span data-stu-id="89dda-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
