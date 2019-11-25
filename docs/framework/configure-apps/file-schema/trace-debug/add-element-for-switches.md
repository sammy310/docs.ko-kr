---
title: <switches>에 대한 <add> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088954"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="2af8e-102">\<스위치에 대 한 > 요소를 추가 \<</span><span class="sxs-lookup"><span data-stu-id="2af8e-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="2af8e-103">추적 스위치를 설정하는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-103">Specifies the level where a trace switch is set.</span></span>  

<span data-ttu-id="2af8e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2af8e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2af8e-105">&nbsp;[ **\<&nbsp;진단 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="2af8e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="2af8e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<스위치**](switches-element.md) ></span><span class="sxs-lookup"><span data-stu-id="2af8e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)</span></span>\
<span data-ttu-id="2af8e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**추가** ></span><span class="sxs-lookup"><span data-stu-id="2af8e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2af8e-108">구문</span><span class="sxs-lookup"><span data-stu-id="2af8e-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2af8e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2af8e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2af8e-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2af8e-111">특성</span><span class="sxs-lookup"><span data-stu-id="2af8e-111">Attributes</span></span>  
  
|<span data-ttu-id="2af8e-112">특성</span><span class="sxs-lookup"><span data-stu-id="2af8e-112">Attribute</span></span>|<span data-ttu-id="2af8e-113">설명</span><span class="sxs-lookup"><span data-stu-id="2af8e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2af8e-114">**name**</span><span class="sxs-lookup"><span data-stu-id="2af8e-114">**name**</span></span>|<span data-ttu-id="2af8e-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="2af8e-116">스위치의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-116">Specifies the name of the switch.</span></span> <span data-ttu-id="2af8e-117">이 특성의 값은 switch 생성자에 전달 되는 *displayName* 매개 변수에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="2af8e-118">**value**</span><span class="sxs-lookup"><span data-stu-id="2af8e-118">**value**</span></span>|<span data-ttu-id="2af8e-119">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="2af8e-120">스위치의 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2af8e-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2af8e-121">Child Elements</span></span>  
 <span data-ttu-id="2af8e-122">없음.</span><span class="sxs-lookup"><span data-stu-id="2af8e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2af8e-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2af8e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2af8e-124">요소</span><span class="sxs-lookup"><span data-stu-id="2af8e-124">Element</span></span>|<span data-ttu-id="2af8e-125">설명</span><span class="sxs-lookup"><span data-stu-id="2af8e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2af8e-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="2af8e-127">추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2af8e-128">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2af8e-129">주의</span><span class="sxs-lookup"><span data-stu-id="2af8e-129">Remarks</span></span>  
 <span data-ttu-id="2af8e-130">구성 파일에 배치 하 여 추적 스위치의 수준을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="2af8e-131">스위치가 <xref:System.Diagnostics.BooleanSwitch>경우 설정 및 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="2af8e-132">스위치가 <xref:System.Diagnostics.TraceSwitch>경우 다른 수준을 할당 하 여 응용 프로그램에서 출력 하는 추적 또는 디버그 메시지의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2af8e-133">예제</span><span class="sxs-lookup"><span data-stu-id="2af8e-133">Example</span></span>  
 <span data-ttu-id="2af8e-134">다음 예에서는 **\<> 요소 추가** 를 사용 하 여 `General` 추적 스위치를 <xref:System.Diagnostics.TraceLevel> 수준으로 설정 하 고 `Data` 부울 추적 스위치를 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2af8e-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2af8e-135">참조</span><span class="sxs-lookup"><span data-stu-id="2af8e-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="2af8e-136">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2af8e-136">Trace and Debug Settings Schema</span></span>](index.md)
