---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 1b5427210142c70c31c5f736c9b5e281dca53f33
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150871"
---
# \<claimType>

<span data-ttu-id="8b3dc-101">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="8b3dc-102">구문</span><span class="sxs-lookup"><span data-stu-id="8b3dc-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b3dc-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8b3dc-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8b3dc-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b3dc-105">특성</span><span class="sxs-lookup"><span data-stu-id="8b3dc-105">Attributes</span></span>  
  
|<span data-ttu-id="8b3dc-106">attribute</span><span class="sxs-lookup"><span data-stu-id="8b3dc-106">Attribute</span></span>|<span data-ttu-id="8b3dc-107">Description</span><span class="sxs-lookup"><span data-stu-id="8b3dc-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b3dc-108">type</span><span class="sxs-lookup"><span data-stu-id="8b3dc-108">type</span></span>|<span data-ttu-id="8b3dc-109">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-109">The claim type.</span></span> <span data-ttu-id="8b3dc-110">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-110">Typically a URI.</span></span> <span data-ttu-id="8b3dc-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-111">Required.</span></span>|  
|<span data-ttu-id="8b3dc-112">선택 사항</span><span class="sxs-lookup"><span data-stu-id="8b3dc-112">optional</span></span>|<span data-ttu-id="8b3dc-113">클레임 형식이 선택적인 지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="8b3dc-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b3dc-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8b3dc-115">Child Elements</span></span>  

 <span data-ttu-id="8b3dc-116">없음</span><span class="sxs-lookup"><span data-stu-id="8b3dc-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b3dc-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8b3dc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8b3dc-118">요소</span><span class="sxs-lookup"><span data-stu-id="8b3dc-118">Element</span></span>|<span data-ttu-id="8b3dc-119">설명</span><span class="sxs-lookup"><span data-stu-id="8b3dc-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="8b3dc-120">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3dc-120">Specifies the set of required claims for incoming security tokens.</span></span>|
