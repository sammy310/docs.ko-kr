---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 4253aec961b812b6893ee201861d2ab38048032a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942874"
---
# <a name="claimtype"></a><span data-ttu-id="85824-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="85824-101">\<claimType></span></span>
<span data-ttu-id="85824-102">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85824-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="85824-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="85824-103">\<system.identityModel></span></span>  
<span data-ttu-id="85824-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="85824-104">\<identityConfiguration></span></span>  
<span data-ttu-id="85824-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="85824-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="85824-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="85824-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85824-107">구문</span><span class="sxs-lookup"><span data-stu-id="85824-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85824-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="85824-108">Attributes and Elements</span></span>  
 <span data-ttu-id="85824-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85824-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85824-110">특성</span><span class="sxs-lookup"><span data-stu-id="85824-110">Attributes</span></span>  
  
|<span data-ttu-id="85824-111">특성</span><span class="sxs-lookup"><span data-stu-id="85824-111">Attribute</span></span>|<span data-ttu-id="85824-112">Description</span><span class="sxs-lookup"><span data-stu-id="85824-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85824-113">type</span><span class="sxs-lookup"><span data-stu-id="85824-113">type</span></span>|<span data-ttu-id="85824-114">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="85824-114">The claim type.</span></span> <span data-ttu-id="85824-115">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="85824-115">Typically a URI.</span></span> <span data-ttu-id="85824-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="85824-116">Required.</span></span>|  
|<span data-ttu-id="85824-117">선택적</span><span class="sxs-lookup"><span data-stu-id="85824-117">optional</span></span>|<span data-ttu-id="85824-118">클레임 형식이 선택적인 지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="85824-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="85824-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="85824-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85824-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="85824-120">Child Elements</span></span>  
 <span data-ttu-id="85824-121">없음</span><span class="sxs-lookup"><span data-stu-id="85824-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85824-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="85824-122">Parent Elements</span></span>  
  
|<span data-ttu-id="85824-123">요소</span><span class="sxs-lookup"><span data-stu-id="85824-123">Element</span></span>|<span data-ttu-id="85824-124">설명</span><span class="sxs-lookup"><span data-stu-id="85824-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85824-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="85824-125">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="85824-126">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85824-126">Specifies the set of required claims for incoming security tokens.</span></span>|
