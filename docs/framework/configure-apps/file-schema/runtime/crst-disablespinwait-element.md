---
title: <Crst_DisableSpinWait> 요소
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 45052d99bb297ac39d058fa405fe57a7c991f738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151352"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="88640-102">\<Crst_DisableSpinWait> 요소</span><span class="sxs-lookup"><span data-stu-id="88640-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="88640-103">경합이 있을 때 임계 영역에 대해 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88640-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="88640-104">구문</span><span class="sxs-lookup"><span data-stu-id="88640-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88640-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="88640-105">Attributes and Elements</span></span>

<span data-ttu-id="88640-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88640-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88640-107">특성</span><span class="sxs-lookup"><span data-stu-id="88640-107">Attributes</span></span>  
  
|<span data-ttu-id="88640-108">attribute</span><span class="sxs-lookup"><span data-stu-id="88640-108">Attribute</span></span>|<span data-ttu-id="88640-109">설명</span><span class="sxs-lookup"><span data-stu-id="88640-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88640-110">**사용**</span><span class="sxs-lookup"><span data-stu-id="88640-110">**enabled**</span></span>|<span data-ttu-id="88640-111">경합이 있을 때 임계 영역에 대 한 회전 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88640-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="88640-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="88640-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="88640-113">Value</span><span class="sxs-lookup"><span data-stu-id="88640-113">Value</span></span>|<span data-ttu-id="88640-114">설명</span><span class="sxs-lookup"><span data-stu-id="88640-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="88640-115">1</span><span class="sxs-lookup"><span data-stu-id="88640-115">1</span></span>|<span data-ttu-id="88640-116">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88640-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="88640-117">0</span><span class="sxs-lookup"><span data-stu-id="88640-117">0</span></span>|<span data-ttu-id="88640-118">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88640-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="88640-119">이것은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="88640-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88640-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="88640-120">Child Elements</span></span>  

 <span data-ttu-id="88640-121">없음</span><span class="sxs-lookup"><span data-stu-id="88640-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88640-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="88640-122">Parent Elements</span></span>  
  
|<span data-ttu-id="88640-123">요소</span><span class="sxs-lookup"><span data-stu-id="88640-123">Element</span></span>|<span data-ttu-id="88640-124">설명</span><span class="sxs-lookup"><span data-stu-id="88640-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="88640-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="88640-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="88640-126">다양 한 런타임 구성 설정에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="88640-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="88640-127">예제</span><span class="sxs-lookup"><span data-stu-id="88640-127">Example</span></span>  

<span data-ttu-id="88640-128">다음 예제에서는 경합이 있을 때 임계 영역에서 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88640-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88640-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88640-129">See also</span></span>

- [<span data-ttu-id="88640-130">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="88640-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="88640-131">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="88640-131">Configuration File Schema</span></span>](../index.md)
