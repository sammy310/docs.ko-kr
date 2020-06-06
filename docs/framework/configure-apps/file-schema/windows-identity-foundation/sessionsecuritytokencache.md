---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "81646074"
---
# \<sessionSecurityTokenCache>
<span data-ttu-id="cb64d-101">서비스 또는 보안 토큰 처리기 컬렉션을 사용 하 여 세션 토큰에 대 한 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb64d-101">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a><span data-ttu-id="cb64d-102">구문</span><span class="sxs-lookup"><span data-stu-id="cb64d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb64d-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cb64d-103">Attributes and Elements</span></span>  
 <span data-ttu-id="cb64d-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb64d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb64d-105">특성</span><span class="sxs-lookup"><span data-stu-id="cb64d-105">Attributes</span></span>  
  
|<span data-ttu-id="cb64d-106">attribute</span><span class="sxs-lookup"><span data-stu-id="cb64d-106">Attribute</span></span>|<span data-ttu-id="cb64d-107">Description</span><span class="sxs-lookup"><span data-stu-id="cb64d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb64d-108">type</span><span class="sxs-lookup"><span data-stu-id="cb64d-108">type</span></span>|<span data-ttu-id="cb64d-109">클래스에서 파생 되는 형식 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 입니다.</span><span class="sxs-lookup"><span data-stu-id="cb64d-109">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb64d-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cb64d-110">Child Elements</span></span>  
 <span data-ttu-id="cb64d-111">None</span><span class="sxs-lookup"><span data-stu-id="cb64d-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb64d-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cb64d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="cb64d-113">요소</span><span class="sxs-lookup"><span data-stu-id="cb64d-113">Element</span></span>|<span data-ttu-id="cb64d-114">Description</span><span class="sxs-lookup"><span data-stu-id="cb64d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="cb64d-115">서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb64d-115">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cb64d-116">예제</span><span class="sxs-lookup"><span data-stu-id="cb64d-116">Example</span></span>  
 <span data-ttu-id="cb64d-117">다음 XML에서는 세션 보안 토큰을 보유 하는 사용자 지정 캐시의 구성 ()을 보여 줍니다 <xref:System.IdentityModel.Tokens.SessionSecurityToken> .</span><span class="sxs-lookup"><span data-stu-id="cb64d-117">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="cb64d-118">이 구성은 샘플에서 가져온 것입니다 `ClaimsAwareWebFarm` .</span><span class="sxs-lookup"><span data-stu-id="cb64d-118">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="cb64d-119">이 샘플에 대 한 자세한 내용은 [WIF Code 샘플 Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cb64d-119">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb64d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb64d-120">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
