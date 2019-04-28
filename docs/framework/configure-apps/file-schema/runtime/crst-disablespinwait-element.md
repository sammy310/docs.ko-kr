---
title: < Crst_DisableSpinWait > 요소
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cde26250db0b3d11c51a18b7ebd378953ae0958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704832"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="85d06-102">\<Crst_DisableSpinWait > 요소</span><span class="sxs-lookup"><span data-stu-id="85d06-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="85d06-103">스핀 대기 경합이 때 중요 한 섹션의 비활성화 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span> \ 
  
 <span data-ttu-id="85d06-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="85d06-104">\<configuration></span></span>  
<span data-ttu-id="85d06-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="85d06-105">\<runtime></span></span>  
<span data-ttu-id="85d06-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="85d06-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d06-107">구문</span><span class="sxs-lookup"><span data-stu-id="85d06-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85d06-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="85d06-108">Attributes and Elements</span></span>

<span data-ttu-id="85d06-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85d06-110">특성</span><span class="sxs-lookup"><span data-stu-id="85d06-110">Attributes</span></span>  
  
|<span data-ttu-id="85d06-111">특성</span><span class="sxs-lookup"><span data-stu-id="85d06-111">Attribute</span></span>|<span data-ttu-id="85d06-112">설명</span><span class="sxs-lookup"><span data-stu-id="85d06-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85d06-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="85d06-113">**enabled**</span></span>|<span data-ttu-id="85d06-114">스핀 대기 임계 영역에 대 한 경합이 되는 경우에 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-114">Specifies whether spin-waiting for critical sections is enabled when they are contended.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="85d06-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="85d06-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="85d06-116">값</span><span class="sxs-lookup"><span data-stu-id="85d06-116">Value</span></span>|<span data-ttu-id="85d06-117">설명</span><span class="sxs-lookup"><span data-stu-id="85d06-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="85d06-118">1</span><span class="sxs-lookup"><span data-stu-id="85d06-118">1</span></span>|<span data-ttu-id="85d06-119">스핀 대기 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-119">Spin-waiting is enabled.</span></span>|  
|<span data-ttu-id="85d06-120">0</span><span class="sxs-lookup"><span data-stu-id="85d06-120">0</span></span>|<span data-ttu-id="85d06-121">스핀 대기 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-121">Spin-waiting is disabled.</span></span> <span data-ttu-id="85d06-122">이것이 기본값</span><span class="sxs-lookup"><span data-stu-id="85d06-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85d06-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="85d06-123">Child Elements</span></span>  
 <span data-ttu-id="85d06-124">없음</span><span class="sxs-lookup"><span data-stu-id="85d06-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85d06-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="85d06-125">Parent Elements</span></span>  
  
|<span data-ttu-id="85d06-126">요소</span><span class="sxs-lookup"><span data-stu-id="85d06-126">Element</span></span>|<span data-ttu-id="85d06-127">설명</span><span class="sxs-lookup"><span data-stu-id="85d06-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="85d06-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="85d06-129">다양 한 런타임 구성 설정에 대 한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="85d06-130">예제</span><span class="sxs-lookup"><span data-stu-id="85d06-130">Example</span></span>  

<span data-ttu-id="85d06-131">다음 예제에서는 비활성화 스핀-경합이 때 중요 한 섹션에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d06-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="85d06-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="85d06-132">See also</span></span>

- [<span data-ttu-id="85d06-133">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="85d06-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="85d06-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="85d06-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
