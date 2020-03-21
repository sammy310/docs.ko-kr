---
title: <source> 요소
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153297"
---
# <a name="source-element"></a><span data-ttu-id="8c434-102">\<소스> 요소</span><span class="sxs-lookup"><span data-stu-id="8c434-102">\<source> Element</span></span>
<span data-ttu-id="8c434-103">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="8c434-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c434-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c434-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c434-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="8c434-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c434-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="8c434-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<소스>**</span><span class="sxs-lookup"><span data-stu-id="8c434-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8c434-108">구문</span><span class="sxs-lookup"><span data-stu-id="8c434-108">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c434-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c434-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8c434-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c434-111">특성</span><span class="sxs-lookup"><span data-stu-id="8c434-111">Attributes</span></span>  
  
|<span data-ttu-id="8c434-112">attribute</span><span class="sxs-lookup"><span data-stu-id="8c434-112">Attribute</span></span>|<span data-ttu-id="8c434-113">Description</span><span class="sxs-lookup"><span data-stu-id="8c434-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="8c434-114">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8c434-115">추적 소스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="8c434-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8c434-117">응용 프로그램에서 추적 스위치 인스턴스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="8c434-118">`<switches>` 요소에서 스위치를 식별하지 않으면 이 값은 스위치의 레벨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="8c434-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8c434-120">추적 스위치의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="8c434-121">있는 경우 형식은 유효한 클래스 이름이어야 하며 빈 문자열일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="8c434-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8c434-123">해당 추적 원본에 대 한 메서드에서 식별 <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> 하는 추적 소스 별 특성에 대 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c434-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c434-124">Child Elements</span></span>  
  
|<span data-ttu-id="8c434-125">요소</span><span class="sxs-lookup"><span data-stu-id="8c434-125">Element</span></span>|<span data-ttu-id="8c434-126">Description</span><span class="sxs-lookup"><span data-stu-id="8c434-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c434-127">\<청취자></span><span class="sxs-lookup"><span data-stu-id="8c434-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="8c434-128">메시지를 수집, 저장 및 라우팅하는 리스너가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c434-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c434-129">Parent Elements</span></span>  
  
|<span data-ttu-id="8c434-130">요소</span><span class="sxs-lookup"><span data-stu-id="8c434-130">Element</span></span>|<span data-ttu-id="8c434-131">Description</span><span class="sxs-lookup"><span data-stu-id="8c434-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8c434-132">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8c434-133">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="8c434-134">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c434-135">설명</span><span class="sxs-lookup"><span data-stu-id="8c434-135">Remarks</span></span>  
 <span data-ttu-id="8c434-136">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c434-137">예제</span><span class="sxs-lookup"><span data-stu-id="8c434-137">Example</span></span>  
 <span data-ttu-id="8c434-138">다음 예제에서는 `<source>` 요소를 사용하여 추적 소스를 `mySource` 추가하고 명명된 `sourceSwitch`소스 스위치의 수준을 설정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="8c434-139">콘솔에 추적 정보를 기록하는 콘솔 추적 수신기가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c434-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>
  </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c434-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c434-140">See also</span></span>

- [<span data-ttu-id="8c434-141">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8c434-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8c434-142">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="8c434-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
