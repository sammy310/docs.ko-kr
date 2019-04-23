---
title: <assert> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: 2f3823265e358976f970cdfa36772d2251894280
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197609"
---
# <a name="assert-element"></a><span data-ttu-id="f90a7-102">\<assert > 요소</span><span class="sxs-lookup"><span data-stu-id="f90a7-102">\<assert> Element</span></span>
<span data-ttu-id="f90a7-103"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="f90a7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f90a7-104">\<configuration></span></span>  
<span data-ttu-id="f90a7-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="f90a7-105">\<system.diagnostics></span></span>  
<span data-ttu-id="f90a7-106">\<assert></span><span class="sxs-lookup"><span data-stu-id="f90a7-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90a7-107">구문</span><span class="sxs-lookup"><span data-stu-id="f90a7-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f90a7-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f90a7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f90a7-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f90a7-110">특성</span><span class="sxs-lookup"><span data-stu-id="f90a7-110">Attributes</span></span>  
  
|<span data-ttu-id="f90a7-111">특성</span><span class="sxs-lookup"><span data-stu-id="f90a7-111">Attribute</span></span>|<span data-ttu-id="f90a7-112">설명</span><span class="sxs-lookup"><span data-stu-id="f90a7-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="f90a7-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f90a7-114">상자 메시지를 표시할 때 여부를 지정 합니다 **Debug.Assert** 메서드를 평가 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="f90a7-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f90a7-116">가 메시지를 쓸 파일의 이름을 지정 **Debug.Assert** 로 평가 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="f90a7-117">assertuienabled 특성</span><span class="sxs-lookup"><span data-stu-id="f90a7-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="f90a7-118">값</span><span class="sxs-lookup"><span data-stu-id="f90a7-118">Value</span></span>|<span data-ttu-id="f90a7-119">설명</span><span class="sxs-lookup"><span data-stu-id="f90a7-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="f90a7-120">메시지 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-120">Displays the message box.</span></span> <span data-ttu-id="f90a7-121">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="f90a7-122">메시지 상자를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f90a7-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f90a7-123">Child Elements</span></span>  
 <span data-ttu-id="f90a7-124">없음</span><span class="sxs-lookup"><span data-stu-id="f90a7-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f90a7-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f90a7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f90a7-126">요소</span><span class="sxs-lookup"><span data-stu-id="f90a7-126">Element</span></span>|<span data-ttu-id="f90a7-127">설명</span><span class="sxs-lookup"><span data-stu-id="f90a7-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f90a7-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f90a7-129">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f90a7-130">설명</span><span class="sxs-lookup"><span data-stu-id="f90a7-130">Remarks</span></span>  
 <span data-ttu-id="f90a7-131">두 특성 모두에  **\<assert >** 요소는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="f90a7-132">메시지를 쓸 파일을 지정 하지 않고 메시지 상자를 비활성화할 수 있습니다 또는 메시지 상자가 활성화 된 상태에서 메시지를 쓸 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f90a7-133">예제</span><span class="sxs-lookup"><span data-stu-id="f90a7-133">Example</span></span>  
 <span data-ttu-id="f90a7-134">다음 예제에서는 호출 하는 경우 메시지 상자 표시를 사용 하지 않도록 설정 하는 방법을 보여 줍니다 **Debug.Assert** 메시지를 쓰고 `c:\log.txt`합니다.</span><span class="sxs-lookup"><span data-stu-id="f90a7-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f90a7-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="f90a7-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="f90a7-136">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f90a7-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
