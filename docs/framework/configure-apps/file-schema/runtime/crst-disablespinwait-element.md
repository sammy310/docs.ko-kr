---
title: < Crst_DisableSpinWait > 요소
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52dd671f1fbf6fda5bdc92c0935784181eb4b03
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663836"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="b400b-102">\<Crst_DisableSpinWait > 요소</span><span class="sxs-lookup"><span data-stu-id="b400b-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="b400b-103">경합이 있을 때 임계 영역에 대해 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="b400b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b400b-104">\<configuration></span></span>  
<span data-ttu-id="b400b-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b400b-105">\<runtime></span></span>  
<span data-ttu-id="b400b-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="b400b-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b400b-107">구문</span><span class="sxs-lookup"><span data-stu-id="b400b-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b400b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b400b-108">Attributes and Elements</span></span>

<span data-ttu-id="b400b-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b400b-110">특성</span><span class="sxs-lookup"><span data-stu-id="b400b-110">Attributes</span></span>  
  
|<span data-ttu-id="b400b-111">특성</span><span class="sxs-lookup"><span data-stu-id="b400b-111">Attribute</span></span>|<span data-ttu-id="b400b-112">설명</span><span class="sxs-lookup"><span data-stu-id="b400b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b400b-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="b400b-113">**enabled**</span></span>|<span data-ttu-id="b400b-114">경합이 있을 때 임계 영역에 대 한 회전 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b400b-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="b400b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b400b-116">값</span><span class="sxs-lookup"><span data-stu-id="b400b-116">Value</span></span>|<span data-ttu-id="b400b-117">설명</span><span class="sxs-lookup"><span data-stu-id="b400b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b400b-118">1</span><span class="sxs-lookup"><span data-stu-id="b400b-118">1</span></span>|<span data-ttu-id="b400b-119">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="b400b-120">0</span><span class="sxs-lookup"><span data-stu-id="b400b-120">0</span></span>|<span data-ttu-id="b400b-121">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="b400b-122">이것은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b400b-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b400b-123">Child Elements</span></span>  
 <span data-ttu-id="b400b-124">없음</span><span class="sxs-lookup"><span data-stu-id="b400b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b400b-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b400b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b400b-126">요소</span><span class="sxs-lookup"><span data-stu-id="b400b-126">Element</span></span>|<span data-ttu-id="b400b-127">설명</span><span class="sxs-lookup"><span data-stu-id="b400b-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b400b-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b400b-129">다양 한 런타임 구성 설정에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b400b-130">예제</span><span class="sxs-lookup"><span data-stu-id="b400b-130">Example</span></span>  

<span data-ttu-id="b400b-131">다음 예제에서는 경합이 있을 때 임계 영역에서 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b400b-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b400b-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="b400b-132">See also</span></span>

- [<span data-ttu-id="b400b-133">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b400b-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b400b-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b400b-134">Configuration File Schema</span></span>](../index.md)
