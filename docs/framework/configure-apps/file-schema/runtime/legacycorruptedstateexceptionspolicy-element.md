---
description: '다음에 대 한 자세한 정보: <legacyCorruptedStateExceptionsPolicy> 요소'
title: <legacyCorruptedStateExceptionsPolicy> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: 34082c0779b09400a875894359cf7cf501173508
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786956"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="66c01-103">\<legacyCorruptedStateExceptionsPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="66c01-103">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>

<span data-ttu-id="66c01-104">공용 언어 런타임에서 관리 코드에서 액세스 위반 및 기타 손상 된 상태 예외를 catch 할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-104">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="66c01-105">구문</span><span class="sxs-lookup"><span data-stu-id="66c01-105">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66c01-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="66c01-106">Attributes and Elements</span></span>  

 <span data-ttu-id="66c01-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66c01-108">특성</span><span class="sxs-lookup"><span data-stu-id="66c01-108">Attributes</span></span>  
  
|<span data-ttu-id="66c01-109">attribute</span><span class="sxs-lookup"><span data-stu-id="66c01-109">Attribute</span></span>|<span data-ttu-id="66c01-110">설명</span><span class="sxs-lookup"><span data-stu-id="66c01-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="66c01-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="66c01-112">응용 프로그램에서 액세스 위반과 같은 손상 된 상태 예외 오류를 catch 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-112">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="66c01-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="66c01-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="66c01-114">값</span><span class="sxs-lookup"><span data-stu-id="66c01-114">Value</span></span>|<span data-ttu-id="66c01-115">설명</span><span class="sxs-lookup"><span data-stu-id="66c01-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="66c01-116">응용 프로그램은 액세스 위반과 같은 손상 된 상태 예외 오류를 catch 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-116">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="66c01-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="66c01-118">응용 프로그램은 액세스 위반과 같은 손상 된 상태 예외 오류를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-118">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66c01-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="66c01-119">Child Elements</span></span>  

 <span data-ttu-id="66c01-120">없음</span><span class="sxs-lookup"><span data-stu-id="66c01-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66c01-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="66c01-121">Parent Elements</span></span>  
  
|<span data-ttu-id="66c01-122">요소</span><span class="sxs-lookup"><span data-stu-id="66c01-122">Element</span></span>|<span data-ttu-id="66c01-123">설명</span><span class="sxs-lookup"><span data-stu-id="66c01-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="66c01-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="66c01-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66c01-126">설명</span><span class="sxs-lookup"><span data-stu-id="66c01-126">Remarks</span></span>  

 <span data-ttu-id="66c01-127">.NET Framework 버전 3.5 및 이전 버전에서 공용 언어 런타임에서는 관리 코드를 허용 하 여 손상 된 프로세스 상태에 의해 발생 한 예외를 catch 했습니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-127">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="66c01-128">액세스 위반은 이러한 형식의 예외에 대 한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-128">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="66c01-129">.NET Framework 4부터 관리 코드는 더 이상 블록에서 이러한 형식의 예외를 catch 하지 않습니다 `catch` .</span><span class="sxs-lookup"><span data-stu-id="66c01-129">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="66c01-130">그러나 다음과 같은 두 가지 방법으로이 변경을 재정의 하 고 손상 된 상태 예외 처리를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-130">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="66c01-131">`<legacyCorruptedStateExceptionsPolicy>`요소의 `enabled` 특성을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-131">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="66c01-132">이 구성 설정은 processwide로 적용 되 고 모든 메서드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-132">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="66c01-133">또는</span><span class="sxs-lookup"><span data-stu-id="66c01-133">-or-</span></span>  
  
- <span data-ttu-id="66c01-134"><xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType>예외 블록이 포함 된 메서드에 특성을 적용 합니다 `catch` .</span><span class="sxs-lookup"><span data-stu-id="66c01-134">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="66c01-135">이 구성 요소는 .NET Framework 4 이상 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-135">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66c01-136">예제</span><span class="sxs-lookup"><span data-stu-id="66c01-136">Example</span></span>  

 <span data-ttu-id="66c01-137">다음 예제에서는 응용 프로그램이 .NET Framework 4 이전의 동작으로 되돌아가고 모든 손상 상태 예외 오류를 catch 하도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66c01-137">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66c01-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66c01-138">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="66c01-139">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="66c01-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="66c01-140">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="66c01-140">Configuration File Schema</span></span>](../index.md)
