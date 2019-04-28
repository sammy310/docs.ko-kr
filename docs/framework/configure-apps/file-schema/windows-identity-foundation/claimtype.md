---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 6bc185572528d4229ee53f1421eaa5bf27b053e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667225"
---
# <a name="claimtype"></a><span data-ttu-id="fda84-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="fda84-101">\<claimType></span></span>
<span data-ttu-id="fda84-102">들어오는 보안 토큰에 대 한 단일 옵션 또는 필요한 클레임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fda84-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="fda84-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fda84-103">\<system.identityModel></span></span>  
<span data-ttu-id="fda84-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fda84-104">\<identityConfiguration></span></span>  
<span data-ttu-id="fda84-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="fda84-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="fda84-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="fda84-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda84-107">구문</span><span class="sxs-lookup"><span data-stu-id="fda84-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fda84-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fda84-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fda84-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fda84-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fda84-110">특성</span><span class="sxs-lookup"><span data-stu-id="fda84-110">Attributes</span></span>  
  
|<span data-ttu-id="fda84-111">특성</span><span class="sxs-lookup"><span data-stu-id="fda84-111">Attribute</span></span>|<span data-ttu-id="fda84-112">설명</span><span class="sxs-lookup"><span data-stu-id="fda84-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fda84-113">type</span><span class="sxs-lookup"><span data-stu-id="fda84-113">type</span></span>|<span data-ttu-id="fda84-114">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fda84-114">The claim type.</span></span> <span data-ttu-id="fda84-115">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fda84-115">Typically a URI.</span></span> <span data-ttu-id="fda84-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fda84-116">Required.</span></span>|  
|<span data-ttu-id="fda84-117">선택적</span><span class="sxs-lookup"><span data-stu-id="fda84-117">optional</span></span>|<span data-ttu-id="fda84-118">클레임 형식이 선택 사항 인지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fda84-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="fda84-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fda84-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fda84-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fda84-120">Child Elements</span></span>  
 <span data-ttu-id="fda84-121">없음</span><span class="sxs-lookup"><span data-stu-id="fda84-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fda84-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fda84-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fda84-123">요소</span><span class="sxs-lookup"><span data-stu-id="fda84-123">Element</span></span>|<span data-ttu-id="fda84-124">설명</span><span class="sxs-lookup"><span data-stu-id="fda84-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fda84-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="fda84-125">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="fda84-126">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda84-126">Specifies the set of required claims for incoming security tokens.</span></span>|
