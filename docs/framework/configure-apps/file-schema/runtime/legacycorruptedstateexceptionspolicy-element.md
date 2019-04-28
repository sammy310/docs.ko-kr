---
title: <legacyCorruptedStateExceptionsPolicy> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 777d496614435106b84b47b9aa3d35d964bc3e07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704741"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="9f637-102">\<legacyCorruptedStateExceptionsPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="9f637-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="9f637-103">공용 언어 런타임에서 액세스 위반 및 기타 손상 된 상태 예외를 catch 하는 관리 되는 코드를 허용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="9f637-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9f637-104">\<configuration></span></span>  
<span data-ttu-id="9f637-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="9f637-105">\<runtime></span></span>  
<span data-ttu-id="9f637-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="9f637-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f637-107">구문</span><span class="sxs-lookup"><span data-stu-id="9f637-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f637-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9f637-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9f637-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f637-110">특성</span><span class="sxs-lookup"><span data-stu-id="9f637-110">Attributes</span></span>  
  
|<span data-ttu-id="9f637-111">특성</span><span class="sxs-lookup"><span data-stu-id="9f637-111">Attribute</span></span>|<span data-ttu-id="9f637-112">설명</span><span class="sxs-lookup"><span data-stu-id="9f637-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9f637-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9f637-114">응용 프로그램은 catch 지정 액세스 위반과 같은 손상 된 상태 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9f637-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="9f637-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9f637-116">값</span><span class="sxs-lookup"><span data-stu-id="9f637-116">Value</span></span>|<span data-ttu-id="9f637-117">설명</span><span class="sxs-lookup"><span data-stu-id="9f637-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9f637-118">응용 프로그램은 catch 하지 않습니다 액세스 위반과 같은 손상 된 상태 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="9f637-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="9f637-120">응용 프로그램을 포착 하는 액세스 위반과 같은 손상 된 상태 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f637-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9f637-121">Child Elements</span></span>  
 <span data-ttu-id="9f637-122">없음</span><span class="sxs-lookup"><span data-stu-id="9f637-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f637-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9f637-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9f637-124">요소</span><span class="sxs-lookup"><span data-stu-id="9f637-124">Element</span></span>|<span data-ttu-id="9f637-125">설명</span><span class="sxs-lookup"><span data-stu-id="9f637-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9f637-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9f637-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f637-128">설명</span><span class="sxs-lookup"><span data-stu-id="9f637-128">Remarks</span></span>  
 <span data-ttu-id="9f637-129">.NET Framework 버전 3.5 및 이전 버전에서 공용 언어 런타임 손상 된 프로세스 상태에서 발생 한 예외를 catch 하는 관리 되는 코드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="9f637-130">액세스 위반이 발생은 이러한 유형의 예외는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="9f637-131">로 시작 합니다 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]관리 되는 코드에는 더 이상 이러한 유형의 예외 catch `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="9f637-132">그러나 이러한 변경 내용을 재정의 하 고 두 가지 방법으로 손상 된 상태 예외 처리를 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="9f637-133">설정 된 `<legacyCorruptedStateExceptionsPolicy>` 요소의 `enabled` 특성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="9f637-134">이 구성 설정은 프로세스 전체에 적용된 되며 모든 메서드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="9f637-135">또는</span><span class="sxs-lookup"><span data-stu-id="9f637-135">-or-</span></span>  
  
- <span data-ttu-id="9f637-136">적용 된 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> 특성을 메서드에 예외를 포함 하는 `catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="9f637-137">이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상.</span><span class="sxs-lookup"><span data-stu-id="9f637-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f637-138">예제</span><span class="sxs-lookup"><span data-stu-id="9f637-138">Example</span></span>  
 <span data-ttu-id="9f637-139">다음 예제에서는 응용 프로그램이 이전 동작으로 되돌려야 함을 지정 하는 방법의 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 모든 손상 된 상태 예외 오류를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f637-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f637-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f637-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="9f637-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9f637-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9f637-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9f637-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
