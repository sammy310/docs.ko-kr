---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252061"
---
# <a name="claimtyperequired"></a><span data-ttu-id="586c7-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="586c7-101">\<claimTypeRequired></span></span>
<span data-ttu-id="586c7-102">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
<span data-ttu-id="586c7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="586c7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="586c7-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="586c7-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="586c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="586c7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="586c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimTypeRequired >**</span><span class="sxs-lookup"><span data-stu-id="586c7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="586c7-107">구문</span><span class="sxs-lookup"><span data-stu-id="586c7-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="586c7-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="586c7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="586c7-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="586c7-110">특성</span><span class="sxs-lookup"><span data-stu-id="586c7-110">Attributes</span></span>  
 <span data-ttu-id="586c7-111">없음</span><span class="sxs-lookup"><span data-stu-id="586c7-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="586c7-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="586c7-112">Child Elements</span></span>  
  
|<span data-ttu-id="586c7-113">요소</span><span class="sxs-lookup"><span data-stu-id="586c7-113">Element</span></span>|<span data-ttu-id="586c7-114">Description</span><span class="sxs-lookup"><span data-stu-id="586c7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="586c7-115">\<claimType></span><span class="sxs-lookup"><span data-stu-id="586c7-115">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="586c7-116">들어오는 보안 토큰에 대 한 단일 선택적 또는 필수 클레임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="586c7-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="586c7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="586c7-118">요소</span><span class="sxs-lookup"><span data-stu-id="586c7-118">Element</span></span>|<span data-ttu-id="586c7-119">설명</span><span class="sxs-lookup"><span data-stu-id="586c7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="586c7-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="586c7-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="586c7-121">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="586c7-121">Specifies service-level identity settings.</span></span>|
