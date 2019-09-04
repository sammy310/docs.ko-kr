---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252064"
---
# <a name="claimtype"></a><span data-ttu-id="7459e-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="7459e-101">\<claimType></span></span>
<span data-ttu-id="7459e-102">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7459e-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
<span data-ttu-id="7459e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7459e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7459e-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="7459e-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="7459e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="7459e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="7459e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequired >** ](claimtyperequired.md)</span><span class="sxs-lookup"><span data-stu-id="7459e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)</span></span>\  
<span data-ttu-id="7459e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimType >**</span><span class="sxs-lookup"><span data-stu-id="7459e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7459e-108">구문</span><span class="sxs-lookup"><span data-stu-id="7459e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7459e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7459e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7459e-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7459e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7459e-111">특성</span><span class="sxs-lookup"><span data-stu-id="7459e-111">Attributes</span></span>  
  
|<span data-ttu-id="7459e-112">특성</span><span class="sxs-lookup"><span data-stu-id="7459e-112">Attribute</span></span>|<span data-ttu-id="7459e-113">설명</span><span class="sxs-lookup"><span data-stu-id="7459e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7459e-114">type</span><span class="sxs-lookup"><span data-stu-id="7459e-114">type</span></span>|<span data-ttu-id="7459e-115">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7459e-115">The claim type.</span></span> <span data-ttu-id="7459e-116">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7459e-116">Typically a URI.</span></span> <span data-ttu-id="7459e-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7459e-117">Required.</span></span>|  
|<span data-ttu-id="7459e-118">선택적</span><span class="sxs-lookup"><span data-stu-id="7459e-118">optional</span></span>|<span data-ttu-id="7459e-119">클레임 형식이 선택적인 지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7459e-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="7459e-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7459e-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7459e-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7459e-121">Child Elements</span></span>  
 <span data-ttu-id="7459e-122">없음</span><span class="sxs-lookup"><span data-stu-id="7459e-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7459e-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7459e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7459e-124">요소</span><span class="sxs-lookup"><span data-stu-id="7459e-124">Element</span></span>|<span data-ttu-id="7459e-125">설명</span><span class="sxs-lookup"><span data-stu-id="7459e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7459e-126">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="7459e-126">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="7459e-127">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7459e-127">Specifies the set of required claims for incoming security tokens.</span></span>|
