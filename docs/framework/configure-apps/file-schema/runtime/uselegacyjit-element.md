---
title: <useLegacyJit> 요소
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d79479d1836963fcbdaaf8d40bfc3648b88c4a3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663404"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="95ef3-102">\<useLegacyJit> 요소</span><span class="sxs-lookup"><span data-stu-id="95ef3-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="95ef3-103">공용 언어 런타임이 Just-In-Time 컴파일에 레거시 64비트 JIT 컴파일러를 사용할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="95ef3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="95ef3-104">\<configuration></span></span>  
<span data-ttu-id="95ef3-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="95ef3-105">\<runtime></span></span>  
<span data-ttu-id="95ef3-106">\<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="95ef3-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="95ef3-107">구문</span><span class="sxs-lookup"><span data-stu-id="95ef3-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="95ef3-108">요소 이름은 `useLegacyJit` 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95ef3-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="95ef3-109">Attributes and elements</span></span>

<span data-ttu-id="95ef3-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95ef3-111">특성</span><span class="sxs-lookup"><span data-stu-id="95ef3-111">Attributes</span></span>  
  
| <span data-ttu-id="95ef3-112">특성</span><span class="sxs-lookup"><span data-stu-id="95ef3-112">Attribute</span></span> | <span data-ttu-id="95ef3-113">설명</span><span class="sxs-lookup"><span data-stu-id="95ef3-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="95ef3-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-114">Required attribute.</span></span><br><br><span data-ttu-id="95ef3-115">런타임이 레거시 64 비트 JIT 컴파일러를 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="95ef3-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="95ef3-116">enabled attribute</span></span>  
  
| <span data-ttu-id="95ef3-117">값</span><span class="sxs-lookup"><span data-stu-id="95ef3-117">Value</span></span> | <span data-ttu-id="95ef3-118">설명</span><span class="sxs-lookup"><span data-stu-id="95ef3-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="95ef3-119">0</span><span class="sxs-lookup"><span data-stu-id="95ef3-119">0</span></span>     | <span data-ttu-id="95ef3-120">공용 언어 런타임은 .NET Framework 4.6 이상 버전에 포함 된 새로운 64 비트 JIT 컴파일러를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="95ef3-121">1</span><span class="sxs-lookup"><span data-stu-id="95ef3-121">1</span></span>     | <span data-ttu-id="95ef3-122">공용 언어 런타임에서는 이전 64 비트 JIT 컴파일러를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="95ef3-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="95ef3-123">Child elements</span></span>

<span data-ttu-id="95ef3-124">없음</span><span class="sxs-lookup"><span data-stu-id="95ef3-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="95ef3-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="95ef3-125">Parent elements</span></span>  
  
| <span data-ttu-id="95ef3-126">요소</span><span class="sxs-lookup"><span data-stu-id="95ef3-126">Element</span></span>         | <span data-ttu-id="95ef3-127">설명</span><span class="sxs-lookup"><span data-stu-id="95ef3-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="95ef3-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="95ef3-129">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="95ef3-130">설명</span><span class="sxs-lookup"><span data-stu-id="95ef3-130">Remarks</span></span>  

<span data-ttu-id="95ef3-131">4\.6 .NET Framework부터 공용 언어 런타임은 기본적으로 JIT (Just-in-time) 컴파일에 새로운 64 비트 컴파일러를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="95ef3-132">일부 경우에는 이전 버전의 64 비트 JIT 컴파일러에 의해 JIT 컴파일된 응용 프로그램 코드의 동작이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="95ef3-133">`enabled` 요소의 특성을 로`1`설정 하 여 새 64 비트 jit 컴파일러를 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 jit 컴파일러를 사용 하 여 앱을 컴파일할 수 있습니다. `<useLegacyJit>`</span><span class="sxs-lookup"><span data-stu-id="95ef3-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95ef3-134">요소 `<useLegacyJit>` 는 64 비트 JIT 컴파일에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="95ef3-135">32 비트 JIT 컴파일러를 사용 하는 컴파일은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="95ef3-136">구성 파일 설정을 사용 하는 대신 두 가지 다른 방법으로 레거시 64 비트 JIT 컴파일러를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="95ef3-137">환경 변수 설정</span><span class="sxs-lookup"><span data-stu-id="95ef3-137">Setting an environment variable</span></span>

  <span data-ttu-id="95ef3-138">환경 변수 `COMPLUS_useLegacyJit` 를 `0` (새로운 64 비트 jit 컴파일러 사용) 또는 `1` (이전 64 비트 jit 컴파일러 사용)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="95ef3-139">환경 변수에는 *전역 범위가*있습니다. 즉, 컴퓨터에서 실행 되는 모든 응용 프로그램에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="95ef3-140">설정 하는 경우 응용 프로그램 구성 파일 설정으로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="95ef3-141">환경 변수 이름은 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="95ef3-142">레지스트리 키 추가</span><span class="sxs-lookup"><span data-stu-id="95ef3-142">Adding a registry key</span></span>

  <span data-ttu-id="95ef3-143">레지스트리의 `REG_DWORD` `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 또는 키`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 중 하나에 값을 추가 하 여 레거시 64 비트 JIT 컴파일러를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="95ef3-144">값의 이름은 `useLegacyJit`입니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="95ef3-145">값이 0 이면 새 컴파일러가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="95ef3-146">값이 1 이면 레거시 64 비트 JIT 컴파일러를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="95ef3-147">레지스트리 값 이름에 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="95ef3-148">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 키에 값을 추가 하면 컴퓨터에서 실행 되는 모든 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="95ef3-149">`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 키에 값을 추가 하면 현재 사용자가 실행 하는 모든 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="95ef3-150">여러 사용자 계정을 사용 하 여 컴퓨터를 구성 하는 경우 다른 사용자에 대 한 레지스트리 키에 값을 추가 하지 않으면 현재 사용자가 실행 하는 앱만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="95ef3-151">구성 파일에 요소를 추가 하면 레지스트리 설정 (있는 경우)이 재정의 됩니다. `<useLegacyJit>`</span><span class="sxs-lookup"><span data-stu-id="95ef3-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95ef3-152">예제</span><span class="sxs-lookup"><span data-stu-id="95ef3-152">Example</span></span>  

<span data-ttu-id="95ef3-153">다음 구성 파일은 새 64 비트 JIT 컴파일러를 사용 하 여 컴파일을 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 JIT 컴파일러를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95ef3-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95ef3-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95ef3-154">See also</span></span>

- [<span data-ttu-id="95ef3-155">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="95ef3-155">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="95ef3-156">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="95ef3-156">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="95ef3-157">조치 새 64 비트 JIT 컴파일러</span><span class="sxs-lookup"><span data-stu-id="95ef3-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
