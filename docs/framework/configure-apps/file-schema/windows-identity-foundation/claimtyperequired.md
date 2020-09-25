---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: a86265ba3963ebc8bea880befbcf80345529116d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203854"
---
# \<claimTypeRequired>

<span data-ttu-id="91388-101">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91388-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="91388-102">구문</span><span class="sxs-lookup"><span data-stu-id="91388-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91388-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91388-103">Attributes and Elements</span></span>  

 <span data-ttu-id="91388-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91388-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91388-105">특성</span><span class="sxs-lookup"><span data-stu-id="91388-105">Attributes</span></span>  

 <span data-ttu-id="91388-106">없음</span><span class="sxs-lookup"><span data-stu-id="91388-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91388-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91388-107">Child Elements</span></span>  
  
|<span data-ttu-id="91388-108">요소</span><span class="sxs-lookup"><span data-stu-id="91388-108">Element</span></span>|<span data-ttu-id="91388-109">설명</span><span class="sxs-lookup"><span data-stu-id="91388-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="91388-110">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91388-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91388-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91388-111">Parent Elements</span></span>  
  
|<span data-ttu-id="91388-112">요소</span><span class="sxs-lookup"><span data-stu-id="91388-112">Element</span></span>|<span data-ttu-id="91388-113">설명</span><span class="sxs-lookup"><span data-stu-id="91388-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="91388-114">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91388-114">Specifies service-level identity settings.</span></span>|
