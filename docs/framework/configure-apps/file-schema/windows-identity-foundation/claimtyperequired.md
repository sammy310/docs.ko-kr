---
description: 다음에 대해 자세히 알아보세요. <claimTypeRequired>
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: ba95c56af431a6dd81323751a42ce47160544cc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664173"
---
# \<claimTypeRequired>

<span data-ttu-id="5ce29-102">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce29-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="5ce29-103">구문</span><span class="sxs-lookup"><span data-stu-id="5ce29-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ce29-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5ce29-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5ce29-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce29-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ce29-106">특성</span><span class="sxs-lookup"><span data-stu-id="5ce29-106">Attributes</span></span>  

 <span data-ttu-id="5ce29-107">None</span><span class="sxs-lookup"><span data-stu-id="5ce29-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ce29-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5ce29-108">Child Elements</span></span>  
  
|<span data-ttu-id="5ce29-109">요소</span><span class="sxs-lookup"><span data-stu-id="5ce29-109">Element</span></span>|<span data-ttu-id="5ce29-110">설명</span><span class="sxs-lookup"><span data-stu-id="5ce29-110">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="5ce29-111">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce29-111">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ce29-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5ce29-112">Parent Elements</span></span>  
  
|<span data-ttu-id="5ce29-113">요소</span><span class="sxs-lookup"><span data-stu-id="5ce29-113">Element</span></span>|<span data-ttu-id="5ce29-114">설명</span><span class="sxs-lookup"><span data-stu-id="5ce29-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="5ce29-115">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce29-115">Specifies service-level identity settings.</span></span>|
