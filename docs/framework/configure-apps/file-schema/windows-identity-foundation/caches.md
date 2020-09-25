---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 791c5be8aa48db2b17a42a216ad2bf5e7b5a4bc1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189879"
---
# \<caches>

<span data-ttu-id="56662-101">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56662-101">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="56662-102">구문</span><span class="sxs-lookup"><span data-stu-id="56662-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56662-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="56662-103">Attributes and Elements</span></span>  

 <span data-ttu-id="56662-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56662-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56662-105">특성</span><span class="sxs-lookup"><span data-stu-id="56662-105">Attributes</span></span>  

 <span data-ttu-id="56662-106">없음</span><span class="sxs-lookup"><span data-stu-id="56662-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56662-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="56662-107">Child Elements</span></span>  
  
|<span data-ttu-id="56662-108">요소</span><span class="sxs-lookup"><span data-stu-id="56662-108">Element</span></span>|<span data-ttu-id="56662-109">설명</span><span class="sxs-lookup"><span data-stu-id="56662-109">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="56662-110">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56662-110">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="56662-111">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 토큰 재생 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56662-111">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56662-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="56662-112">Parent Elements</span></span>  
  
|<span data-ttu-id="56662-113">요소</span><span class="sxs-lookup"><span data-stu-id="56662-113">Element</span></span>|<span data-ttu-id="56662-114">설명</span><span class="sxs-lookup"><span data-stu-id="56662-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="56662-115">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="56662-115">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="56662-116">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="56662-116">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56662-117">설명</span><span class="sxs-lookup"><span data-stu-id="56662-117">Remarks</span></span>  

 <span data-ttu-id="56662-118">요소는 요소 아래의 `<caches>` 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 처리기 컬렉션 수준에서 지정할 수 있습니다 `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="56662-118">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="56662-119">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="56662-119">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="56662-120">합니다 `<caches>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="56662-120">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="56662-121">구성 된 캐시는 클래스로 표시 됩니다 <xref:System.IdentityModel.Configuration.IdentityModelCaches> .</span><span class="sxs-lookup"><span data-stu-id="56662-121">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56662-122">예제</span><span class="sxs-lookup"><span data-stu-id="56662-122">Example</span></span>  

 <span data-ttu-id="56662-123">다음 XML에서는 세션 보안 토큰을 보유 하는 사용자 지정 캐시의 구성 ()을 보여 줍니다 <xref:System.IdentityModel.Tokens.SessionSecurityToken> .</span><span class="sxs-lookup"><span data-stu-id="56662-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="56662-124">이 구성은 샘플에서 가져온 것입니다 `ClaimsAwareWebFarm` .</span><span class="sxs-lookup"><span data-stu-id="56662-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
