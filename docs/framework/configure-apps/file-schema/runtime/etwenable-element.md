---
title: <etwEnable> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba411114bfb853e06c83adb42713d43f1452d9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135072"
---
# <a name="etwenable-element"></a><span data-ttu-id="6a8f5-102">\<etwEnable > 요소</span><span class="sxs-lookup"><span data-stu-id="6a8f5-102">\<etwEnable> Element</span></span>
<span data-ttu-id="6a8f5-103">공용 언어 런타임 이벤트에 대해 ETW(Windows용 이벤트 추적)를 사용하도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="6a8f5-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="6a8f5-104">\<configuration> Element</span></span>  
<span data-ttu-id="6a8f5-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="6a8f5-105">\<runtime> Element</span></span>  
<span data-ttu-id="6a8f5-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="6a8f5-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a8f5-107">구문</span><span class="sxs-lookup"><span data-stu-id="6a8f5-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a8f5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6a8f5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6a8f5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a8f5-110">특성</span><span class="sxs-lookup"><span data-stu-id="6a8f5-110">Attributes</span></span>  
  
|<span data-ttu-id="6a8f5-111">특성</span><span class="sxs-lookup"><span data-stu-id="6a8f5-111">Attribute</span></span>|<span data-ttu-id="6a8f5-112">설명</span><span class="sxs-lookup"><span data-stu-id="6a8f5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a8f5-113">사용</span><span class="sxs-lookup"><span data-stu-id="6a8f5-113">enabled</span></span>|<span data-ttu-id="6a8f5-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6a8f5-115">ETW를 사용 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6a8f5-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="6a8f5-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="6a8f5-117">값</span><span class="sxs-lookup"><span data-stu-id="6a8f5-117">Value</span></span>|<span data-ttu-id="6a8f5-118">설명</span><span class="sxs-lookup"><span data-stu-id="6a8f5-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6a8f5-119">true</span><span class="sxs-lookup"><span data-stu-id="6a8f5-119">true</span></span>|<span data-ttu-id="6a8f5-120">ETW를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-120">Enable ETW.</span></span> <span data-ttu-id="6a8f5-121">이것은 Windows Vista 및 Windows Server 2008 운영 체제를 사용 하 여 시작 하는 Windows 버전에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="6a8f5-122">False</span><span class="sxs-lookup"><span data-stu-id="6a8f5-122">false</span></span>|<span data-ttu-id="6a8f5-123">ETW를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-123">Disable ETW.</span></span> <span data-ttu-id="6a8f5-124">이것은 이전 버전의 Windows에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a8f5-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6a8f5-125">Child Elements</span></span>  
 <span data-ttu-id="6a8f5-126">없음</span><span class="sxs-lookup"><span data-stu-id="6a8f5-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a8f5-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6a8f5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6a8f5-128">요소</span><span class="sxs-lookup"><span data-stu-id="6a8f5-128">Element</span></span>|<span data-ttu-id="6a8f5-129">설명</span><span class="sxs-lookup"><span data-stu-id="6a8f5-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6a8f5-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6a8f5-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a8f5-132">설명</span><span class="sxs-lookup"><span data-stu-id="6a8f5-132">Remarks</span></span>  
 <span data-ttu-id="6a8f5-133">Windows Vista 부터는 ETW 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="6a8f5-134">이 요소를 사용 하 여 응용 프로그램에 대 한 ETW를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="6a8f5-135">Windows의 이전 버전에서는 응용 프로그램에 대 한 ETW를 사용 하도록 설정 하려면이 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a8f5-136">ETW는 사용 하도록 설정 또는 레지스트리 설정을 사용 하 여 서버에서 전역적으로 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="6a8f5-137">참조 [.NET Framework 로깅 제어](../../../../../docs/framework/performance/controlling-logging.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a8f5-138">예제</span><span class="sxs-lookup"><span data-stu-id="6a8f5-138">Example</span></span>  
 <span data-ttu-id="6a8f5-139">다음 예제에서는 응용 프로그램에 대 한 ETW 추적을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a8f5-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a8f5-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a8f5-140">See also</span></span>

- [<span data-ttu-id="6a8f5-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6a8f5-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6a8f5-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6a8f5-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="6a8f5-143">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="6a8f5-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
