---
title: <source>에 대한 <listeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: b7144b0a7004ba32b21cbc98513df574a5a9e1d9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195183"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="33134-102">\<source>에 대한 \<listeners> 요소</span><span class="sxs-lookup"><span data-stu-id="33134-102">\<listeners> Element for \<source></span></span>

<span data-ttu-id="33134-103">의 컬렉션에서 수신기를 추가 하거나 제거 <xref:System.Diagnostics.TraceSource.Listeners%2A> <xref:System.Diagnostics.TraceSource> 합니다.</span><span class="sxs-lookup"><span data-stu-id="33134-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="33134-104">수신기는 추적 출력을 로그, 창 또는 텍스트 파일과 같은 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="33134-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**  
  
## <a name="syntax"></a><span data-ttu-id="33134-105">구문</span><span class="sxs-lookup"><span data-stu-id="33134-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33134-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="33134-106">Attributes and Elements</span></span>  

 <span data-ttu-id="33134-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33134-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33134-108">특성</span><span class="sxs-lookup"><span data-stu-id="33134-108">Attributes</span></span>  

 <span data-ttu-id="33134-109">없음</span><span class="sxs-lookup"><span data-stu-id="33134-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33134-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="33134-110">Child Elements</span></span>  
  
|<span data-ttu-id="33134-111">요소</span><span class="sxs-lookup"><span data-stu-id="33134-111">Element</span></span>|<span data-ttu-id="33134-112">설명</span><span class="sxs-lookup"><span data-stu-id="33134-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="33134-113">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33134-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="33134-114">컬렉션에서 수신기를 제거 합니다 `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="33134-114">Removes a listener from the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="33134-115">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="33134-115">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33134-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="33134-116">Parent Elements</span></span>  
  
|<span data-ttu-id="33134-117">요소</span><span class="sxs-lookup"><span data-stu-id="33134-117">Element</span></span>|<span data-ttu-id="33134-118">설명</span><span class="sxs-lookup"><span data-stu-id="33134-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="33134-119">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="33134-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="33134-120">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33134-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="33134-121">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33134-121">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="33134-122">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33134-122">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33134-123">설명</span><span class="sxs-lookup"><span data-stu-id="33134-123">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="33134-124">구성 파일</span><span class="sxs-lookup"><span data-stu-id="33134-124">Configuration File</span></span>  

 <span data-ttu-id="33134-125">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33134-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33134-126">예제</span><span class="sxs-lookup"><span data-stu-id="33134-126">Example</span></span>  

 <span data-ttu-id="33134-127">다음 예제에서는 요소를 사용 하 여 `<listeners>` 콘솔 추적 수신기를 소스에 추가 하 `mySource` 고 기본 추적 수신기를 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33134-127">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33134-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33134-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="33134-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="33134-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="33134-130">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="33134-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
