---
title: <switches> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153232"
---
# <a name="switches-element"></a><span data-ttu-id="866c3-102">\<> 요소 전환</span><span class="sxs-lookup"><span data-stu-id="866c3-102">\<switches> Element</span></span>
<span data-ttu-id="866c3-103">추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="866c3-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="866c3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="866c3-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="866c3-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="866c3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>스위치**</span><span class="sxs-lookup"><span data-stu-id="866c3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="866c3-107">구문</span><span class="sxs-lookup"><span data-stu-id="866c3-107">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="866c3-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="866c3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="866c3-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="866c3-110">특성</span><span class="sxs-lookup"><span data-stu-id="866c3-110">Attributes</span></span>  
 <span data-ttu-id="866c3-111">없음</span><span class="sxs-lookup"><span data-stu-id="866c3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="866c3-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="866c3-112">Child Elements</span></span>  
  
|<span data-ttu-id="866c3-113">요소</span><span class="sxs-lookup"><span data-stu-id="866c3-113">Element</span></span>|<span data-ttu-id="866c3-114">Description</span><span class="sxs-lookup"><span data-stu-id="866c3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="866c3-115">\<>추가</span><span class="sxs-lookup"><span data-stu-id="866c3-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="866c3-116">추적 스위치를 설정하는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="866c3-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="866c3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="866c3-118">요소</span><span class="sxs-lookup"><span data-stu-id="866c3-118">Element</span></span>|<span data-ttu-id="866c3-119">Description</span><span class="sxs-lookup"><span data-stu-id="866c3-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="866c3-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="866c3-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="866c3-122">설명</span><span class="sxs-lookup"><span data-stu-id="866c3-122">Remarks</span></span>  
 <span data-ttu-id="866c3-123">추적 스위치의 수준을 구성 파일에 배치하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="866c3-124">스위치가 있는 <xref:System.Diagnostics.BooleanSwitch>경우 을 켜고 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="866c3-125">스위치가 a인 <xref:System.Diagnostics.TraceSwitch>경우 다른 수준을 할당하여 응용 프로그램에서 출력하는 추적 또는 디버그 메시지 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="866c3-126">예제</span><span class="sxs-lookup"><span data-stu-id="866c3-126">Example</span></span>  
 <span data-ttu-id="866c3-127">다음 예제에서는 \*\* \<스위치>\*\* 요소를 사용하여 `General` 추적 스위치를 <xref:System.Diagnostics.TraceLevel> 수준으로 설정하고 부울 추적 스위치를 `Data` 사용하도록 설정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="866c3-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="866c3-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="866c3-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="866c3-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="866c3-129">Trace and Debug Settings Schema</span></span>](index.md)
