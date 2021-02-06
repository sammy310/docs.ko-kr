---
description: '에 대 한 자세한 정보: <listeners> 요소 <trace>'
title: <trace>에 대한 <listeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 25f6d4b49eeb57b25b4afbbdfdba484d6d7eea3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639629"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="832ea-103">\<trace>에 대한 \<listeners> 요소</span><span class="sxs-lookup"><span data-stu-id="832ea-103">\<listeners> Element for \<trace></span></span>

<span data-ttu-id="832ea-104">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-104">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="832ea-105">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-105">Listeners direct the tracing output to an appropriate target.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a><span data-ttu-id="832ea-106">구문</span><span class="sxs-lookup"><span data-stu-id="832ea-106">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="832ea-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="832ea-107">Attributes and Elements</span></span>  

 <span data-ttu-id="832ea-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="832ea-109">특성</span><span class="sxs-lookup"><span data-stu-id="832ea-109">Attributes</span></span>  

 <span data-ttu-id="832ea-110">없음</span><span class="sxs-lookup"><span data-stu-id="832ea-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="832ea-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="832ea-111">Child Elements</span></span>  
  
|<span data-ttu-id="832ea-112">요소</span><span class="sxs-lookup"><span data-stu-id="832ea-112">Element</span></span>|<span data-ttu-id="832ea-113">설명</span><span class="sxs-lookup"><span data-stu-id="832ea-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="832ea-114">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-114">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="832ea-115">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-115">Clears the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="832ea-116">컬렉션에서 수신기를 제거 합니다 `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="832ea-116">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="832ea-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="832ea-117">Parent Elements</span></span>  
  
|<span data-ttu-id="832ea-118">요소</span><span class="sxs-lookup"><span data-stu-id="832ea-118">Element</span></span>|<span data-ttu-id="832ea-119">설명</span><span class="sxs-lookup"><span data-stu-id="832ea-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="832ea-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="832ea-121">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-121">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="832ea-122">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-122">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="832ea-123">설명</span><span class="sxs-lookup"><span data-stu-id="832ea-123">Remarks</span></span>  

 <span data-ttu-id="832ea-124"><xref:System.Diagnostics.Debug>및 <xref:System.Diagnostics.Trace> 클래스는 동일한 **Listeners** 컬렉션을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-124">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="832ea-125">이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가 하는 경우 다른 클래스는 동일한 수신기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-125">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="832ea-126">.NET Framework와 함께 제공 되는 수신기 클래스는 클래스에서 파생 <xref:System.Diagnostics.TraceListener> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-126">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="832ea-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="832ea-127">Configuration File</span></span>  

 <span data-ttu-id="832ea-128">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="832ea-129">예제</span><span class="sxs-lookup"><span data-stu-id="832ea-129">Example</span></span>  

 <span data-ttu-id="832ea-130">다음 예제에서는 요소를 사용 하 여 수신기 **\<listeners>** `MyListener` 및 수신기 `MyEventListener` 컬렉션에  를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-130">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="832ea-131">`MyListener` 이라는 파일을 만들고 `MyListener.log` 출력을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-131">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="832ea-132">`MyEventListener` 이벤트 로그에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="832ea-132">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="832ea-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="832ea-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="832ea-134">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="832ea-134">Trace and Debug Settings Schema</span></span>](index.md)
