---
title: <Crst_DisableSpinWait> 요소
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117647"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="c77c4-102">\<Crst_DisableSpinWait> 요소</span><span class="sxs-lookup"><span data-stu-id="c77c4-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="c77c4-103">경합이 있을 때 임계 영역에 대해 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="c77c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="c77c4-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c77c4-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c77c4-105">Attributes and Elements</span></span>

<span data-ttu-id="c77c4-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c77c4-107">특성</span><span class="sxs-lookup"><span data-stu-id="c77c4-107">Attributes</span></span>  
  
|<span data-ttu-id="c77c4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c77c4-108">Attribute</span></span>|<span data-ttu-id="c77c4-109">Description</span><span class="sxs-lookup"><span data-stu-id="c77c4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c77c4-110">**사용**</span><span class="sxs-lookup"><span data-stu-id="c77c4-110">**enabled**</span></span>|<span data-ttu-id="c77c4-111">경합이 있을 때 임계 영역에 대 한 회전 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c77c4-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c77c4-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="c77c4-113">값</span><span class="sxs-lookup"><span data-stu-id="c77c4-113">Value</span></span>|<span data-ttu-id="c77c4-114">Description</span><span class="sxs-lookup"><span data-stu-id="c77c4-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c77c4-115">1</span><span class="sxs-lookup"><span data-stu-id="c77c4-115">1</span></span>|<span data-ttu-id="c77c4-116">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="c77c4-117">0</span><span class="sxs-lookup"><span data-stu-id="c77c4-117">0</span></span>|<span data-ttu-id="c77c4-118">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="c77c4-119">이것은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c77c4-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c77c4-120">Child Elements</span></span>  
 <span data-ttu-id="c77c4-121">없음</span><span class="sxs-lookup"><span data-stu-id="c77c4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c77c4-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c77c4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c77c4-123">요소</span><span class="sxs-lookup"><span data-stu-id="c77c4-123">Element</span></span>|<span data-ttu-id="c77c4-124">Description</span><span class="sxs-lookup"><span data-stu-id="c77c4-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c77c4-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c77c4-126">다양 한 런타임 구성 설정에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c77c4-127">예제</span><span class="sxs-lookup"><span data-stu-id="c77c4-127">Example</span></span>  

<span data-ttu-id="c77c4-128">다음 예제에서는 경합이 있을 때 임계 영역에서 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c77c4-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c77c4-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c77c4-129">See also</span></span>

- [<span data-ttu-id="c77c4-130">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c77c4-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c77c4-131">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c77c4-131">Configuration File Schema</span></span>](../index.md)
