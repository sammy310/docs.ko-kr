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
ms.openlocfilehash: eb29701912a45a484b1716195b449e8a97d1d4b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149298"
---
# <a name="assert-element"></a><span data-ttu-id="d01bf-102">\<assert> 요소</span><span class="sxs-lookup"><span data-stu-id="d01bf-102">\<assert> Element</span></span>

<span data-ttu-id="d01bf-103"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a><span data-ttu-id="d01bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="d01bf-104">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d01bf-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d01bf-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d01bf-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d01bf-107">특성</span><span class="sxs-lookup"><span data-stu-id="d01bf-107">Attributes</span></span>  
  
|<span data-ttu-id="d01bf-108">attribute</span><span class="sxs-lookup"><span data-stu-id="d01bf-108">Attribute</span></span>|<span data-ttu-id="d01bf-109">설명</span><span class="sxs-lookup"><span data-stu-id="d01bf-109">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="d01bf-110">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d01bf-111">**Debug. Assert** 메서드가 **false**로 평가 될 때 메시지 상자를 표시할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-111">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="d01bf-112">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d01bf-113">디버그가 인 경우 메시지를 쓸 파일의 이름을 지정 합니다 **. Assert** 가 **false**로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-113">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="d01bf-114">assertuienabled 특성</span><span class="sxs-lookup"><span data-stu-id="d01bf-114">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="d01bf-115">Value</span><span class="sxs-lookup"><span data-stu-id="d01bf-115">Value</span></span>|<span data-ttu-id="d01bf-116">설명</span><span class="sxs-lookup"><span data-stu-id="d01bf-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="d01bf-117">메시지 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-117">Displays the message box.</span></span> <span data-ttu-id="d01bf-118">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="d01bf-119">메시지 상자를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-119">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d01bf-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d01bf-120">Child Elements</span></span>  

 <span data-ttu-id="d01bf-121">없음</span><span class="sxs-lookup"><span data-stu-id="d01bf-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d01bf-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d01bf-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d01bf-123">요소</span><span class="sxs-lookup"><span data-stu-id="d01bf-123">Element</span></span>|<span data-ttu-id="d01bf-124">설명</span><span class="sxs-lookup"><span data-stu-id="d01bf-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d01bf-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d01bf-126">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d01bf-127">설명</span><span class="sxs-lookup"><span data-stu-id="d01bf-127">Remarks</span></span>  

 <span data-ttu-id="d01bf-128">요소의 두 특성 **\<assert>** 은 모두 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-128">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="d01bf-129">메시지를 쓸 파일을 지정 하지 않고 메시지 상자를 사용 하지 않도록 설정 하거나 메시지 상자를 활성화 한 상태로 메시지를 쓸 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-129">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d01bf-130">예제</span><span class="sxs-lookup"><span data-stu-id="d01bf-130">Example</span></span>  

 <span data-ttu-id="d01bf-131">다음 예제에서는 Debug를 호출할 때 메시지 상자를 표시 하지 않도록 설정 하는 방법을 보여 줍니다 **. Assert** 및 메시지 `c:\log.txt` 를에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d01bf-131">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d01bf-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d01bf-132">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="d01bf-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d01bf-133">Trace and Debug Settings Schema</span></span>](index.md)
