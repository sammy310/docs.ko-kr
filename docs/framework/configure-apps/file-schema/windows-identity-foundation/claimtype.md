---
description: 다음에 대해 자세히 알아보세요. <claimType>
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 55fd32edc7fb810742c3cf678b434675aebba00e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664225"
---
# \<claimType>

<span data-ttu-id="1507c-102">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="1507c-103">구문</span><span class="sxs-lookup"><span data-stu-id="1507c-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1507c-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1507c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1507c-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1507c-106">특성</span><span class="sxs-lookup"><span data-stu-id="1507c-106">Attributes</span></span>  
  
|<span data-ttu-id="1507c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="1507c-107">Attribute</span></span>|<span data-ttu-id="1507c-108">Description</span><span class="sxs-lookup"><span data-stu-id="1507c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1507c-109">type</span><span class="sxs-lookup"><span data-stu-id="1507c-109">type</span></span>|<span data-ttu-id="1507c-110">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-110">The claim type.</span></span> <span data-ttu-id="1507c-111">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-111">Typically a URI.</span></span> <span data-ttu-id="1507c-112">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-112">Required.</span></span>|  
|<span data-ttu-id="1507c-113">선택적</span><span class="sxs-lookup"><span data-stu-id="1507c-113">optional</span></span>|<span data-ttu-id="1507c-114">클레임 형식이 선택적인 지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-114">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="1507c-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-115">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1507c-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1507c-116">Child Elements</span></span>  

 <span data-ttu-id="1507c-117">없음</span><span class="sxs-lookup"><span data-stu-id="1507c-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1507c-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1507c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1507c-119">요소</span><span class="sxs-lookup"><span data-stu-id="1507c-119">Element</span></span>|<span data-ttu-id="1507c-120">설명</span><span class="sxs-lookup"><span data-stu-id="1507c-120">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="1507c-121">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1507c-121">Specifies the set of required claims for incoming security tokens.</span></span>|
