---
title: <sources> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153271"
---
# <a name="sources-element"></a><span data-ttu-id="9a70b-102">\<소스> 요소</span><span class="sxs-lookup"><span data-stu-id="9a70b-102">\<sources> Element</span></span>
<span data-ttu-id="9a70b-103">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="9a70b-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a70b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9a70b-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a70b-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="9a70b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<소스>**</span><span class="sxs-lookup"><span data-stu-id="9a70b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9a70b-107">구문</span><span class="sxs-lookup"><span data-stu-id="9a70b-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a70b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a70b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9a70b-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a70b-110">특성</span><span class="sxs-lookup"><span data-stu-id="9a70b-110">Attributes</span></span>  
 <span data-ttu-id="9a70b-111">없음</span><span class="sxs-lookup"><span data-stu-id="9a70b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a70b-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a70b-112">Child Elements</span></span>  
  
|<span data-ttu-id="9a70b-113">요소</span><span class="sxs-lookup"><span data-stu-id="9a70b-113">Element</span></span>|<span data-ttu-id="9a70b-114">Description</span><span class="sxs-lookup"><span data-stu-id="9a70b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a70b-115">\<소스></span><span class="sxs-lookup"><span data-stu-id="9a70b-115">\<source></span></span>](source-element.md)|<span data-ttu-id="9a70b-116">필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-116">Required element.</span></span><br /><br /> <span data-ttu-id="9a70b-117">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a70b-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a70b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9a70b-119">요소</span><span class="sxs-lookup"><span data-stu-id="9a70b-119">Element</span></span>|<span data-ttu-id="9a70b-120">Description</span><span class="sxs-lookup"><span data-stu-id="9a70b-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9a70b-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9a70b-122">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a70b-123">설명</span><span class="sxs-lookup"><span data-stu-id="9a70b-123">Remarks</span></span>  
 <span data-ttu-id="9a70b-124">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a70b-125">예제</span><span class="sxs-lookup"><span data-stu-id="9a70b-125">Example</span></span>  
 <span data-ttu-id="9a70b-126">다음 예제에서는 `<sources>` 요소를 사용하여 추적 소스를 `mySource` 추가하고 명명된 `sourceSwitch`소스 스위치의 수준을 설정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="9a70b-127">콘솔에 추적 정보를 기록하는 콘솔 추적 수신기가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a70b-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"
                     initializeData="Error" />  
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
  
## <a name="see-also"></a><span data-ttu-id="9a70b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a70b-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="9a70b-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9a70b-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9a70b-130">\<소스></span><span class="sxs-lookup"><span data-stu-id="9a70b-130">\<source></span></span>](source-element.md)
