---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 4deeb1d84f2621adb7ff1b649a505138b6856ec1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790496"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="590f7-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="590f7-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="590f7-102">토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="590f7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="590f7-103">\<system.identityModel></span></span>  
<span data-ttu-id="590f7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="590f7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="590f7-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="590f7-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="590f7-106">구문</span><span class="sxs-lookup"><span data-stu-id="590f7-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="590f7-107">형식</span><span class="sxs-lookup"><span data-stu-id="590f7-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="590f7-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="590f7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="590f7-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="590f7-110">특성</span><span class="sxs-lookup"><span data-stu-id="590f7-110">Attributes</span></span>  
  
|<span data-ttu-id="590f7-111">특성</span><span class="sxs-lookup"><span data-stu-id="590f7-111">Attribute</span></span>|<span data-ttu-id="590f7-112">설명</span><span class="sxs-lookup"><span data-stu-id="590f7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="590f7-113">사용</span><span class="sxs-lookup"><span data-stu-id="590f7-113">enabled</span></span>|<span data-ttu-id="590f7-114">때 토큰 재생 검색 사용 되는지 여부를 지정 하는 값 토큰을 사용 하도록 설정 하려면 "true" 재생 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="590f7-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="590f7-115">expirationPeriod</span></span>|<span data-ttu-id="590f7-116"><xref:System.TimeSpan> 항목 만료 된 것으로 간주 되어 캐시에서 제거 하기 전의 시간을 최대 크기를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="590f7-117">지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값을 참조 하세요 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="590f7-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="590f7-118">Child Elements</span></span>  
 <span data-ttu-id="590f7-119">없음</span><span class="sxs-lookup"><span data-stu-id="590f7-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="590f7-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="590f7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="590f7-121">요소</span><span class="sxs-lookup"><span data-stu-id="590f7-121">Element</span></span>|<span data-ttu-id="590f7-122">설명</span><span class="sxs-lookup"><span data-stu-id="590f7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="590f7-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="590f7-123">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="590f7-124">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="590f7-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="590f7-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="590f7-126">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="590f7-127">설명</span><span class="sxs-lookup"><span data-stu-id="590f7-127">Remarks</span></span>  
 <span data-ttu-id="590f7-128">`<tokenReplayDetection>` 요소 아래에 있는 서비스 수준에서 지정할 수 있습니다 합니다 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준에서는 `<securityTokenHandlerConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="590f7-129">서비스에 지정 된 토큰 처리기 컬렉션의 설정을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="590f7-130">토큰 재생 캐시의 형식으로 지정 된 [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="590f7-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
