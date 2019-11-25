---
title: <source> 요소
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: b59144f4772c940f8c7e6ca19aa21666069b4b55
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088824"
---
# <a name="source-element"></a><span data-ttu-id="ec373-102">\<source > 요소</span><span class="sxs-lookup"><span data-stu-id="ec373-102">\<source> Element</span></span>
<span data-ttu-id="ec373-103">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="ec373-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec373-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ec373-105">&nbsp;[ **\<&nbsp;진단 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="ec373-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="ec373-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**원본**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="ec373-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\</span></span>
<span data-ttu-id="ec373-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**원본 >**</span><span class="sxs-lookup"><span data-stu-id="ec373-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ec373-108">구문</span><span class="sxs-lookup"><span data-stu-id="ec373-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec373-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ec373-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ec373-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec373-111">특성</span><span class="sxs-lookup"><span data-stu-id="ec373-111">Attributes</span></span>  
  
|<span data-ttu-id="ec373-112">특성</span><span class="sxs-lookup"><span data-stu-id="ec373-112">Attribute</span></span>|<span data-ttu-id="ec373-113">설명</span><span class="sxs-lookup"><span data-stu-id="ec373-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ec373-114">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ec373-115">추적 원본의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="ec373-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ec373-117">응용 프로그램에서 추적 스위치 인스턴스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="ec373-118">스위치가 `<switches>` 요소에서 식별 되지 않은 경우이 값은 스위치의 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="ec373-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ec373-120">추적 스위치의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="ec373-121">있는 경우 형식은 올바른 클래스 이름 이어야 하며 빈 문자열일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="ec373-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ec373-123">해당 추적 소스에 대 한 <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> 메서드로 식별 되는 추적 소스 관련 특성의 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec373-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ec373-124">Child Elements</span></span>  
  
|<span data-ttu-id="ec373-125">요소</span><span class="sxs-lookup"><span data-stu-id="ec373-125">Element</span></span>|<span data-ttu-id="ec373-126">설명</span><span class="sxs-lookup"><span data-stu-id="ec373-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec373-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="ec373-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="ec373-128">메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec373-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ec373-129">Parent Elements</span></span>  
  
|<span data-ttu-id="ec373-130">요소</span><span class="sxs-lookup"><span data-stu-id="ec373-130">Element</span></span>|<span data-ttu-id="ec373-131">설명</span><span class="sxs-lookup"><span data-stu-id="ec373-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ec373-132">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ec373-133">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="ec373-134">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec373-135">주의</span><span class="sxs-lookup"><span data-stu-id="ec373-135">Remarks</span></span>  
 <span data-ttu-id="ec373-136">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec373-137">예제</span><span class="sxs-lookup"><span data-stu-id="ec373-137">Example</span></span>  
 <span data-ttu-id="ec373-138">다음 예제에서는 `<source>` 요소를 사용 하 여 추적 소스 `mySource`를 추가 하 고 `sourceSwitch`라는 원본 스위치의 수준을 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="ec373-139">콘솔에 추적 정보를 기록 하는 콘솔 추적 수신기가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec373-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec373-140">참조</span><span class="sxs-lookup"><span data-stu-id="ec373-140">See also</span></span>

- [<span data-ttu-id="ec373-141">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ec373-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ec373-142">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="ec373-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
