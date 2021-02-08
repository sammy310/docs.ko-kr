---
description: 다음에 대해 자세히 알아보세요. <tokenReplayDetection>
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a8a6b754a3282afe4f2932296b06b84c09fb6f1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786540"
---
# \<tokenReplayDetection>

<span data-ttu-id="51d14-102">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d14-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="51d14-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="51d14-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="51d14-104">Type</span><span class="sxs-lookup"><span data-stu-id="51d14-104">Type</span></span>  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51d14-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="51d14-105">Attributes and Elements</span></span>  

 <span data-ttu-id="51d14-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51d14-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51d14-107">특성</span><span class="sxs-lookup"><span data-stu-id="51d14-107">Attributes</span></span>  
  
|<span data-ttu-id="51d14-108">attribute</span><span class="sxs-lookup"><span data-stu-id="51d14-108">Attribute</span></span>|<span data-ttu-id="51d14-109">설명</span><span class="sxs-lookup"><span data-stu-id="51d14-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51d14-110">사용</span><span class="sxs-lookup"><span data-stu-id="51d14-110">enabled</span></span>|<span data-ttu-id="51d14-111">토큰 재생 검색이 사용 되는지 여부를 지정 하는 값입니다. 토큰 재생 검색을 사용 하도록 설정 하려면 "true"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d14-111">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="51d14-112">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="51d14-112">expirationPeriod</span></span>|<span data-ttu-id="51d14-113"><xref:System.TimeSpan>항목이 만료 된 것으로 간주 되 고 캐시에서 제거 되기 전 까지의 최대 시간을 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="51d14-113">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="51d14-114">값을 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51d14-114">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51d14-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="51d14-115">Child Elements</span></span>  

 <span data-ttu-id="51d14-116">없음</span><span class="sxs-lookup"><span data-stu-id="51d14-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51d14-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="51d14-117">Parent Elements</span></span>  
  
|<span data-ttu-id="51d14-118">요소</span><span class="sxs-lookup"><span data-stu-id="51d14-118">Element</span></span>|<span data-ttu-id="51d14-119">설명</span><span class="sxs-lookup"><span data-stu-id="51d14-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="51d14-120">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d14-120">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="51d14-121">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d14-121">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51d14-122">설명</span><span class="sxs-lookup"><span data-stu-id="51d14-122">Remarks</span></span>  

 <span data-ttu-id="51d14-123">요소는 요소 아래의 `<tokenReplayDetection>` 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 처리기 컬렉션 수준에서 지정할 수 있습니다 `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="51d14-123">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="51d14-124">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d14-124">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="51d14-125">토큰 재생 캐시의 형식은 요소에 의해 지정 됩니다 [\<tokenReplayCache>](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="51d14-125">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
