---
description: '다음에 대 한 자세한 정보: <etwEnable> 요소'
title: <etwEnable> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 224784f47d15788ded41a5756e1d179a5a25907b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787047"
---
# <a name="etwenable-element"></a><span data-ttu-id="dff1f-103">\<etwEnable> 요소</span><span class="sxs-lookup"><span data-stu-id="dff1f-103">\<etwEnable> Element</span></span>

<span data-ttu-id="dff1f-104">공용 언어 런타임 이벤트에 대해 ETW(Windows용 이벤트 추적)를 사용하도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-104">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="dff1f-105">구문</span><span class="sxs-lookup"><span data-stu-id="dff1f-105">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dff1f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dff1f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="dff1f-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dff1f-108">특성</span><span class="sxs-lookup"><span data-stu-id="dff1f-108">Attributes</span></span>  
  
|<span data-ttu-id="dff1f-109">attribute</span><span class="sxs-lookup"><span data-stu-id="dff1f-109">Attribute</span></span>|<span data-ttu-id="dff1f-110">설명</span><span class="sxs-lookup"><span data-stu-id="dff1f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dff1f-111">사용</span><span class="sxs-lookup"><span data-stu-id="dff1f-111">enabled</span></span>|<span data-ttu-id="dff1f-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="dff1f-113">ETW를 사용 하도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-113">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="dff1f-114">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="dff1f-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="dff1f-115">값</span><span class="sxs-lookup"><span data-stu-id="dff1f-115">Value</span></span>|<span data-ttu-id="dff1f-116">설명</span><span class="sxs-lookup"><span data-stu-id="dff1f-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dff1f-117">true</span><span class="sxs-lookup"><span data-stu-id="dff1f-117">true</span></span>|<span data-ttu-id="dff1f-118">ETW를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-118">Enable ETW.</span></span> <span data-ttu-id="dff1f-119">Windows Vista 및 Windows Server 2008 운영 체제에서 시작 하는 Windows 버전에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-119">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="dff1f-120">false</span><span class="sxs-lookup"><span data-stu-id="dff1f-120">false</span></span>|<span data-ttu-id="dff1f-121">ETW를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-121">Disable ETW.</span></span> <span data-ttu-id="dff1f-122">이는 이전 버전의 Windows에 대 한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-122">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dff1f-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dff1f-123">Child Elements</span></span>  

 <span data-ttu-id="dff1f-124">없음</span><span class="sxs-lookup"><span data-stu-id="dff1f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dff1f-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dff1f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="dff1f-126">요소</span><span class="sxs-lookup"><span data-stu-id="dff1f-126">Element</span></span>|<span data-ttu-id="dff1f-127">설명</span><span class="sxs-lookup"><span data-stu-id="dff1f-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dff1f-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dff1f-129">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dff1f-130">설명</span><span class="sxs-lookup"><span data-stu-id="dff1f-130">Remarks</span></span>  

 <span data-ttu-id="dff1f-131">Windows Vista부터 ETW는 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-131">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="dff1f-132">응용 프로그램에 대해 ETW를 사용 하지 않도록 설정 하려면이 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-132">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="dff1f-133">이전 버전의 Windows에서는이 요소를 사용 하 여 응용 프로그램에 대해 ETW를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-133">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dff1f-134">레지스트리 설정을 사용 하 여 서버에서 전역적으로 ETW를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-134">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="dff1f-135">[.NET Framework 로깅 제어](../../../performance/controlling-logging.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dff1f-135">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dff1f-136">예제</span><span class="sxs-lookup"><span data-stu-id="dff1f-136">Example</span></span>  

 <span data-ttu-id="dff1f-137">다음 예제에서는 응용 프로그램에 대해 ETW 추적을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dff1f-137">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dff1f-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dff1f-138">See also</span></span>

- [<span data-ttu-id="dff1f-139">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="dff1f-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dff1f-140">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="dff1f-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dff1f-141">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="dff1f-141">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
