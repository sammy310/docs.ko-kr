---
description: <Crst_DisableSpinWait> 요소에 대해 자세히 알아보세요.
title: <Crst_DisableSpinWait> 요소
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: fca6fed2dabc3d1319ad030bb13bbb35a561b9aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795107"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="ff266-103">\<Crst_DisableSpinWait> 요소</span><span class="sxs-lookup"><span data-stu-id="ff266-103">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="ff266-104">경합이 있을 때 임계 영역에 대해 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-104">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="ff266-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff266-105">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff266-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ff266-106">Attributes and Elements</span></span>

<span data-ttu-id="ff266-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff266-108">특성</span><span class="sxs-lookup"><span data-stu-id="ff266-108">Attributes</span></span>  
  
|<span data-ttu-id="ff266-109">attribute</span><span class="sxs-lookup"><span data-stu-id="ff266-109">Attribute</span></span>|<span data-ttu-id="ff266-110">설명</span><span class="sxs-lookup"><span data-stu-id="ff266-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff266-111">**사용**</span><span class="sxs-lookup"><span data-stu-id="ff266-111">**enabled**</span></span>|<span data-ttu-id="ff266-112">경합이 있을 때 임계 영역에 대 한 회전 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-112">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ff266-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ff266-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="ff266-114">값</span><span class="sxs-lookup"><span data-stu-id="ff266-114">Value</span></span>|<span data-ttu-id="ff266-115">설명</span><span class="sxs-lookup"><span data-stu-id="ff266-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff266-116">1</span><span class="sxs-lookup"><span data-stu-id="ff266-116">1</span></span>|<span data-ttu-id="ff266-117">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-117">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="ff266-118">0</span><span class="sxs-lookup"><span data-stu-id="ff266-118">0</span></span>|<span data-ttu-id="ff266-119">임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-119">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="ff266-120">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-120">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff266-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ff266-121">Child Elements</span></span>  

 <span data-ttu-id="ff266-122">없음</span><span class="sxs-lookup"><span data-stu-id="ff266-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff266-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ff266-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ff266-124">요소</span><span class="sxs-lookup"><span data-stu-id="ff266-124">Element</span></span>|<span data-ttu-id="ff266-125">설명</span><span class="sxs-lookup"><span data-stu-id="ff266-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ff266-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ff266-127">다양 한 런타임 구성 설정에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-127">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff266-128">예제</span><span class="sxs-lookup"><span data-stu-id="ff266-128">Example</span></span>  

<span data-ttu-id="ff266-129">다음 예제에서는 경합이 있을 때 임계 영역에서 스핀 대기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff266-129">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff266-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff266-130">See also</span></span>

- [<span data-ttu-id="ff266-131">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ff266-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ff266-132">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ff266-132">Configuration File Schema</span></span>](../index.md)
