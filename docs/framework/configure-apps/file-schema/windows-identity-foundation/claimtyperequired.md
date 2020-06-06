---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252061"
---
# \<claimTypeRequired>
<span data-ttu-id="d04b0-101">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04b0-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="d04b0-102">구문</span><span class="sxs-lookup"><span data-stu-id="d04b0-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d04b0-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d04b0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d04b0-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d04b0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d04b0-105">특성</span><span class="sxs-lookup"><span data-stu-id="d04b0-105">Attributes</span></span>  
 <span data-ttu-id="d04b0-106">None</span><span class="sxs-lookup"><span data-stu-id="d04b0-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d04b0-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d04b0-107">Child Elements</span></span>  
  
|<span data-ttu-id="d04b0-108">요소</span><span class="sxs-lookup"><span data-stu-id="d04b0-108">Element</span></span>|<span data-ttu-id="d04b0-109">Description</span><span class="sxs-lookup"><span data-stu-id="d04b0-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="d04b0-110">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04b0-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d04b0-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d04b0-111">Parent Elements</span></span>  
  
|<span data-ttu-id="d04b0-112">요소</span><span class="sxs-lookup"><span data-stu-id="d04b0-112">Element</span></span>|<span data-ttu-id="d04b0-113">Description</span><span class="sxs-lookup"><span data-stu-id="d04b0-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="d04b0-114">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04b0-114">Specifies service-level identity settings.</span></span>|
