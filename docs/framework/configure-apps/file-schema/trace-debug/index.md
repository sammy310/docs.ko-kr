---
description: '자세히 알아보기: 추적 및 디버그 설정 스키마'
title: 추적 및 디버그 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
ms.openlocfilehash: 2429585c44952d2ee12547dab8f51662295bf02f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639654"
---
# <a name="trace-and-debug-settings-schema"></a><span data-ttu-id="49994-103">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="49994-103">Trace and Debug Settings Schema</span></span>

<span data-ttu-id="49994-104">추적 및 디버그 설정은 메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-104">Trace and debug settings specify trace listeners that collect, store, and route messages, and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="49994-105">다음 표는 각 추적 및 디버그 설정 요소의 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-105">The following table describes the function of each trace and debug settings element.</span></span>  
  
|<span data-ttu-id="49994-106">요소</span><span class="sxs-lookup"><span data-stu-id="49994-106">Element</span></span>|<span data-ttu-id="49994-107">설명</span><span class="sxs-lookup"><span data-stu-id="49994-107">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="49994-108">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-108">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="49994-109">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-109">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<add>](add-element-for-sharedlisteners.md)|<span data-ttu-id="49994-110">`sharedListeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-110">Adds a listener to the `sharedListeners` collection.</span></span>|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="49994-111">추적 스위치를 설정하는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-111">Specifies the level where a trace switch is set.</span></span>|  
|[\<assert>](assert-element.md)|<span data-ttu-id="49994-112"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-112">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="49994-113">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="49994-113">Clears the `Listeners` collection for a trace source.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="49994-114">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="49994-114">Clears the `Listeners` collection for trace.</span></span>|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="49994-115">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-115">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="49994-116">추적의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-116">Adds a filter to a listener in the `Listeners` collection for trace.</span></span>|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="49994-117">`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-117">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="49994-118">추적 소스의 `Listeners` 컬렉션에 대한 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-118">Specifies listeners for the `Listeners` collection for a trace source.</span></span>|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="49994-119">추적의 `Listeners` 컬렉션에 대한 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-119">Specifies listeners for the `Listeners` collection for trace.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="49994-120">성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-120">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="49994-121">추적의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-121">Removes a listener from the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="49994-122">추적 소스의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-122">Removes a listener from the `Listeners` collection for a trace source.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="49994-123">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49994-123">Contains listeners that any source or trace element can reference.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="49994-124">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49994-124">Contains trace sources that initiate tracing messages.</span></span>|  
|[\<source>](source-element.md)|<span data-ttu-id="49994-125">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-125">Specifies a trace source that initiates tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="49994-126">추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49994-126">Contains trace switches and the level where the trace switches are set.</span></span>|  
|[\<system.diagnostics>](system-diagnostics-element.md)|<span data-ttu-id="49994-127">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49994-127">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="49994-128">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49994-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49994-129">참조</span><span class="sxs-lookup"><span data-stu-id="49994-129">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="49994-130">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="49994-130">Configuration File Schema</span></span>](../index.md)
