---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251767"
---
# \<tokenReplayDetection>
<span data-ttu-id="65380-101">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65380-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="65380-102">구문</span><span class="sxs-lookup"><span data-stu-id="65380-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="65380-103">Type</span><span class="sxs-lookup"><span data-stu-id="65380-103">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65380-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="65380-104">Attributes and Elements</span></span>  
 <span data-ttu-id="65380-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65380-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65380-106">특성</span><span class="sxs-lookup"><span data-stu-id="65380-106">Attributes</span></span>  
  
|<span data-ttu-id="65380-107">attribute</span><span class="sxs-lookup"><span data-stu-id="65380-107">Attribute</span></span>|<span data-ttu-id="65380-108">Description</span><span class="sxs-lookup"><span data-stu-id="65380-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65380-109">사용</span><span class="sxs-lookup"><span data-stu-id="65380-109">enabled</span></span>|<span data-ttu-id="65380-110">토큰 재생 검색이 사용 되는지 여부를 지정 하는 값입니다. 토큰 재생 검색을 사용 하도록 설정 하려면 "true"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65380-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="65380-111">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="65380-111">expirationPeriod</span></span>|<span data-ttu-id="65380-112"><xref:System.TimeSpan>항목이 만료 된 것으로 간주 되 고 캐시에서 제거 되기 전 까지의 최대 시간을 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="65380-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="65380-113">값을 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65380-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65380-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="65380-114">Child Elements</span></span>  
 <span data-ttu-id="65380-115">None</span><span class="sxs-lookup"><span data-stu-id="65380-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65380-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="65380-116">Parent Elements</span></span>  
  
|<span data-ttu-id="65380-117">요소</span><span class="sxs-lookup"><span data-stu-id="65380-117">Element</span></span>|<span data-ttu-id="65380-118">Description</span><span class="sxs-lookup"><span data-stu-id="65380-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="65380-119">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65380-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="65380-120">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="65380-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65380-121">설명</span><span class="sxs-lookup"><span data-stu-id="65380-121">Remarks</span></span>  
 <span data-ttu-id="65380-122">요소는 요소 아래의 `<tokenReplayDetection>` 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 처리기 컬렉션 수준에서 지정할 수 있습니다 `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="65380-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="65380-123">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="65380-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="65380-124">토큰 재생 캐시의 형식은 요소에 의해 지정 됩니다 [\<tokenReplayCache>](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="65380-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
