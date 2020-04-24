---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646074"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="b2ae3-101">\<세션보안토큰캐시></span><span class="sxs-lookup"><span data-stu-id="b2ae3-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="b2ae3-102">서비스 또는 보안 토큰 처리기 컬렉션으로 세션 토큰에 대한 캐시를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ae3-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="b2ae3-103">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b2ae3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b2ae3-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b2ae3-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b2ae3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b2ae3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b2ae3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<캐시>**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="b2ae3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="b2ae3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<세션보안토큰캐시>**</span><span class="sxs-lookup"><span data-stu-id="b2ae3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ae3-108">구문</span><span class="sxs-lookup"><span data-stu-id="b2ae3-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2ae3-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2ae3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b2ae3-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ae3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2ae3-111">특성</span><span class="sxs-lookup"><span data-stu-id="b2ae3-111">Attributes</span></span>  
  
|<span data-ttu-id="b2ae3-112">attribute</span><span class="sxs-lookup"><span data-stu-id="b2ae3-112">Attribute</span></span>|<span data-ttu-id="b2ae3-113">Description</span><span class="sxs-lookup"><span data-stu-id="b2ae3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2ae3-114">type</span><span class="sxs-lookup"><span data-stu-id="b2ae3-114">type</span></span>|<span data-ttu-id="b2ae3-115">클래스에서 파생되는 형식입니다. <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="b2ae3-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2ae3-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2ae3-116">Child Elements</span></span>  
 <span data-ttu-id="b2ae3-117">None</span><span class="sxs-lookup"><span data-stu-id="b2ae3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2ae3-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2ae3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b2ae3-119">요소</span><span class="sxs-lookup"><span data-stu-id="b2ae3-119">Element</span></span>|<span data-ttu-id="b2ae3-120">Description</span><span class="sxs-lookup"><span data-stu-id="b2ae3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2ae3-121">\<캐시></span><span class="sxs-lookup"><span data-stu-id="b2ae3-121">\<caches></span></span>](caches.md)|<span data-ttu-id="b2ae3-122">서비스 또는 보안 토큰 처리기 컬렉션에서 사용하는 캐시를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ae3-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2ae3-123">예제</span><span class="sxs-lookup"><span data-stu-id="b2ae3-123">Example</span></span>  
 <span data-ttu-id="b2ae3-124">다음 XML은 세션 보안 토큰()을<xref:System.IdentityModel.Tokens.SessionSecurityToken>보유하기 위한 사용자 지정 캐시의 구성을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ae3-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="b2ae3-125">구성은 `ClaimsAwareWebFarm` 샘플에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2ae3-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="b2ae3-126">이 샘플에 대한 자세한 내용은 [WIF 코드 샘플 인덱스](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2ae3-126">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2ae3-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2ae3-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
