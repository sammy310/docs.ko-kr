---
title: <shadowCopyVerifyByTimestamp> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 160f14c856735e1ceac8635506aea52454faea43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115736"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="55957-102">\<shadowCopyVerifyByTimestamp> 요소</span><span class="sxs-lookup"><span data-stu-id="55957-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="55957-103">섀도 복사가 .NET Framework 4에서 도입 된 기본 시작 동작을 사용 하는지 아니면 이전 버전의 .NET Framework의 시작 동작으로 돌아가는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55957-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
<span data-ttu-id="55957-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55957-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55957-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="55957-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="55957-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<p >**</span><span class="sxs-lookup"><span data-stu-id="55957-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55957-107">구문</span><span class="sxs-lookup"><span data-stu-id="55957-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55957-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="55957-108">Attributes and Elements</span></span>  
 <span data-ttu-id="55957-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="55957-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55957-110">특성</span><span class="sxs-lookup"><span data-stu-id="55957-110">Attributes</span></span>  
  
|<span data-ttu-id="55957-111">특성</span><span class="sxs-lookup"><span data-stu-id="55957-111">Attribute</span></span>|<span data-ttu-id="55957-112">설명</span><span class="sxs-lookup"><span data-stu-id="55957-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55957-113">사용</span><span class="sxs-lookup"><span data-stu-id="55957-113">enabled</span></span>|<span data-ttu-id="55957-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="55957-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="55957-115">어셈블리를 섀도 복사 하기 전에 어셈블리가 업데이트 되었는지 여부를 확인 하기 위해 섀도 복사를 사용 하는 응용 프로그램 도메인이 시작 시 어셈블리 타임 스탬프를 비교 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55957-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="55957-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="55957-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="55957-117">값</span><span class="sxs-lookup"><span data-stu-id="55957-117">Value</span></span>|<span data-ttu-id="55957-118">설명</span><span class="sxs-lookup"><span data-stu-id="55957-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="55957-119">true</span><span class="sxs-lookup"><span data-stu-id="55957-119">true</span></span>|<span data-ttu-id="55957-120">시작 시는 섀도 복사본 디렉터리에 마지막으로 복사 된 이후 업데이트 된 어셈블리만 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="55957-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="55957-121">.NET Framework 4의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="55957-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="55957-122">False</span><span class="sxs-lookup"><span data-stu-id="55957-122">false</span></span>|<span data-ttu-id="55957-123">시작 시 모든 파일을 복사 하는 이전 버전의 .NET Framework의 시작 동작으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="55957-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55957-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="55957-124">Child Elements</span></span>  
 <span data-ttu-id="55957-125">없음.</span><span class="sxs-lookup"><span data-stu-id="55957-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55957-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="55957-126">Parent Elements</span></span>  
  
|<span data-ttu-id="55957-127">요소</span><span class="sxs-lookup"><span data-stu-id="55957-127">Element</span></span>|<span data-ttu-id="55957-128">설명</span><span class="sxs-lookup"><span data-stu-id="55957-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="55957-129">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="55957-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="55957-130">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55957-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55957-131">주의</span><span class="sxs-lookup"><span data-stu-id="55957-131">Remarks</span></span>  
 <span data-ttu-id="55957-132">.NET Framework 4부터 어셈블리는 타임 스탬프가 섀도 복사본 디렉터리에 마지막으로 복사 된 이후에 변경 된 것을 나타내는 경우에만 섀도 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55957-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="55957-133">이렇게 하면 섀도 복사 [어셈블리](../../../app-domains/shadow-copy-assemblies.md)에 설명 된 대로 섀도 복사를 사용 하는 많은 응용 프로그램의 시작 시간이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55957-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="55957-134">어셈블리 업데이트의 높은 비율과 빈도를 갖는 애플리케이션은 이 동작 변경이 도움이 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55957-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="55957-135">이 경우 이 요소를 사용하여 이전 버전의 .NET Framework의 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55957-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55957-136">예제</span><span class="sxs-lookup"><span data-stu-id="55957-136">Example</span></span>  
 <span data-ttu-id="55957-137">다음 예제에서는 .NET Framework 4에서 섀도 복사의 기본 시작 동작을 사용 하지 않도록 설정 하 고 이전 버전의 .NET Framework의 시작 동작으로 되돌리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55957-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="55957-138">참조</span><span class="sxs-lookup"><span data-stu-id="55957-138">See also</span></span>

- [<span data-ttu-id="55957-139">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="55957-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="55957-140">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="55957-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="55957-141">어셈블리 섀도 복사</span><span class="sxs-lookup"><span data-stu-id="55957-141">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
