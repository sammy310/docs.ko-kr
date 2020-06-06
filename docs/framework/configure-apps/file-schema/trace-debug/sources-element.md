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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153271"
---
# <a name="sources-element"></a><span data-ttu-id="b2cee-102">\<sources> 요소</span><span class="sxs-lookup"><span data-stu-id="b2cee-102">\<sources> Element</span></span>
<span data-ttu-id="b2cee-103">추적 메시지를 시작 하는 추적 소스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-103">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="b2cee-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2cee-104">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2cee-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2cee-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b2cee-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2cee-107">특성</span><span class="sxs-lookup"><span data-stu-id="b2cee-107">Attributes</span></span>  
 <span data-ttu-id="b2cee-108">없음</span><span class="sxs-lookup"><span data-stu-id="b2cee-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2cee-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2cee-109">Child Elements</span></span>  
  
|<span data-ttu-id="b2cee-110">요소</span><span class="sxs-lookup"><span data-stu-id="b2cee-110">Element</span></span>|<span data-ttu-id="b2cee-111">Description</span><span class="sxs-lookup"><span data-stu-id="b2cee-111">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="b2cee-112">필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-112">Required element.</span></span><br /><br /> <span data-ttu-id="b2cee-113">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-113">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2cee-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2cee-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b2cee-115">요소</span><span class="sxs-lookup"><span data-stu-id="b2cee-115">Element</span></span>|<span data-ttu-id="b2cee-116">Description</span><span class="sxs-lookup"><span data-stu-id="b2cee-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b2cee-117">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b2cee-118">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2cee-119">설명</span><span class="sxs-lookup"><span data-stu-id="b2cee-119">Remarks</span></span>  
 <span data-ttu-id="b2cee-120">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-120">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2cee-121">예제</span><span class="sxs-lookup"><span data-stu-id="b2cee-121">Example</span></span>  
 <span data-ttu-id="b2cee-122">다음 예제에서는 요소를 사용 하 여 `<sources>` 추적 소스를 추가 하 `mySource` 고 라는 소스 스위치의 수준을 설정 하는 방법을 보여 줍니다 `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="b2cee-122">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="b2cee-123">콘솔에 추적 정보를 기록 하는 콘솔 추적 수신기가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2cee-123">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2cee-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2cee-124">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="b2cee-125">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b2cee-125">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
