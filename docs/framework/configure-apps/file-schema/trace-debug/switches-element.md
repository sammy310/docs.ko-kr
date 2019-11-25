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
ms.openlocfilehash: 4aeb3cb0cd75f0fb27e3b359b86da61a77b491c7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088797"
---
# <a name="switches-element"></a><span data-ttu-id="424fa-102">\<스위치 > 요소</span><span class="sxs-lookup"><span data-stu-id="424fa-102">\<switches> Element</span></span>
<span data-ttu-id="424fa-103">추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="424fa-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="424fa-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="424fa-105">&nbsp;[ **\<&nbsp;진단 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="424fa-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="424fa-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<스위치 >**</span><span class="sxs-lookup"><span data-stu-id="424fa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="424fa-107">구문</span><span class="sxs-lookup"><span data-stu-id="424fa-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="424fa-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="424fa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="424fa-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="424fa-110">특성</span><span class="sxs-lookup"><span data-stu-id="424fa-110">Attributes</span></span>  
 <span data-ttu-id="424fa-111">없음.</span><span class="sxs-lookup"><span data-stu-id="424fa-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="424fa-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="424fa-112">Child Elements</span></span>  
  
|<span data-ttu-id="424fa-113">요소</span><span class="sxs-lookup"><span data-stu-id="424fa-113">Element</span></span>|<span data-ttu-id="424fa-114">설명</span><span class="sxs-lookup"><span data-stu-id="424fa-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="424fa-115">\<add></span><span class="sxs-lookup"><span data-stu-id="424fa-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="424fa-116">추적 스위치를 설정하는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="424fa-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="424fa-117">Parent Elements</span></span>  
  
|<span data-ttu-id="424fa-118">요소</span><span class="sxs-lookup"><span data-stu-id="424fa-118">Element</span></span>|<span data-ttu-id="424fa-119">설명</span><span class="sxs-lookup"><span data-stu-id="424fa-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="424fa-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="424fa-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="424fa-122">주의</span><span class="sxs-lookup"><span data-stu-id="424fa-122">Remarks</span></span>  
 <span data-ttu-id="424fa-123">구성 파일에 배치 하 여 추적 스위치의 수준을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="424fa-124">스위치가 <xref:System.Diagnostics.BooleanSwitch>경우 설정 및 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="424fa-125">스위치가 <xref:System.Diagnostics.TraceSwitch>경우 다른 수준을 할당 하 여 응용 프로그램에서 출력 하는 추적 또는 디버그 메시지의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="424fa-126">예제</span><span class="sxs-lookup"><span data-stu-id="424fa-126">Example</span></span>  
 <span data-ttu-id="424fa-127">다음 예에서는 **\<스위치 >** 요소를 사용 하 여 `General` 추적 스위치를 <xref:System.Diagnostics.TraceLevel> 수준으로 설정 하 고 `Data` 부울 추적 스위치를 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="424fa-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="424fa-128">참조</span><span class="sxs-lookup"><span data-stu-id="424fa-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="424fa-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="424fa-129">Trace and Debug Settings Schema</span></span>](index.md)
