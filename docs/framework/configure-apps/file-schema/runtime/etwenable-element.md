---
title: <etwEnable> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3510cbf0a63a8031669bb7a819a8b3c7321aaea4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920772"
---
# <a name="etwenable-element"></a><span data-ttu-id="c8829-102">\<etwEnable > 요소</span><span class="sxs-lookup"><span data-stu-id="c8829-102">\<etwEnable> Element</span></span>
<span data-ttu-id="c8829-103">공용 언어 런타임 이벤트에 대해 ETW(Windows용 이벤트 추적)를 사용하도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="c8829-104">\<configuration > 요소</span><span class="sxs-lookup"><span data-stu-id="c8829-104">\<configuration> Element</span></span>  
<span data-ttu-id="c8829-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="c8829-105">\<runtime> Element</span></span>  
<span data-ttu-id="c8829-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="c8829-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8829-107">구문</span><span class="sxs-lookup"><span data-stu-id="c8829-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8829-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c8829-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c8829-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8829-110">특성</span><span class="sxs-lookup"><span data-stu-id="c8829-110">Attributes</span></span>  
  
|<span data-ttu-id="c8829-111">특성</span><span class="sxs-lookup"><span data-stu-id="c8829-111">Attribute</span></span>|<span data-ttu-id="c8829-112">설명</span><span class="sxs-lookup"><span data-stu-id="c8829-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8829-113">사용</span><span class="sxs-lookup"><span data-stu-id="c8829-113">enabled</span></span>|<span data-ttu-id="c8829-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c8829-115">ETW를 사용 하도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c8829-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c8829-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="c8829-117">값</span><span class="sxs-lookup"><span data-stu-id="c8829-117">Value</span></span>|<span data-ttu-id="c8829-118">설명</span><span class="sxs-lookup"><span data-stu-id="c8829-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c8829-119">true</span><span class="sxs-lookup"><span data-stu-id="c8829-119">true</span></span>|<span data-ttu-id="c8829-120">ETW를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-120">Enable ETW.</span></span> <span data-ttu-id="c8829-121">Windows Vista 및 Windows Server 2008 운영 체제에서 시작 하는 Windows 버전에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="c8829-122">False</span><span class="sxs-lookup"><span data-stu-id="c8829-122">false</span></span>|<span data-ttu-id="c8829-123">ETW를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-123">Disable ETW.</span></span> <span data-ttu-id="c8829-124">이는 이전 버전의 Windows에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8829-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c8829-125">Child Elements</span></span>  
 <span data-ttu-id="c8829-126">없음</span><span class="sxs-lookup"><span data-stu-id="c8829-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8829-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c8829-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c8829-128">요소</span><span class="sxs-lookup"><span data-stu-id="c8829-128">Element</span></span>|<span data-ttu-id="c8829-129">설명</span><span class="sxs-lookup"><span data-stu-id="c8829-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c8829-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c8829-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8829-132">설명</span><span class="sxs-lookup"><span data-stu-id="c8829-132">Remarks</span></span>  
 <span data-ttu-id="c8829-133">Windows Vista부터 ETW는 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="c8829-134">응용 프로그램에 대해 ETW를 사용 하지 않도록 설정 하려면이 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="c8829-135">이전 버전의 Windows에서는이 요소를 사용 하 여 응용 프로그램에 대해 ETW를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8829-136">레지스트리 설정을 사용 하 여 서버에서 전역적으로 ETW를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="c8829-137">[.NET Framework 로깅 제어](../../../performance/controlling-logging.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8829-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8829-138">예제</span><span class="sxs-lookup"><span data-stu-id="c8829-138">Example</span></span>  
 <span data-ttu-id="c8829-139">다음 예제에서는 응용 프로그램에 대해 ETW 추적을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8829-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8829-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8829-140">See also</span></span>

- [<span data-ttu-id="c8829-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c8829-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c8829-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c8829-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c8829-143">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="c8829-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
