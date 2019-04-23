---
title: 기본 상호 운용성 모범 사례 - .NET
description: .NET에서 기본 구성 요소와 인터페이스하는 모범 사례를 알아봅니다.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 6702d469abf317b3b1f545ce79b980e8581ab5f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196660"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="51246-103">기본 상호 운용성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="51246-103">Native interoperability best practices</span></span>

<span data-ttu-id="51246-104">.NET에서는 기본 상호 운용성 코드를 사용자 지정하는 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="51246-105">이 문서에는 Microsoft .NET 팀이 네이티브 상호 운용성을 위해 따르는 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="51246-106">일반 지침</span><span class="sxs-lookup"><span data-stu-id="51246-106">General guidance</span></span>

<span data-ttu-id="51246-107">이 섹션의 지침은 모든 interop 시나리오에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="51246-108">**✔️** 호출하려는 네이티브 메서드와 동일한 명명 및 대문자 표시를 메서드와 매개 변수에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-108">**✔️ DO** use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="51246-109">**✔️** 상수 값에 동일한 명명 및 대문자 표시를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-109">**✔️ CONSIDER** using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="51246-110">**✔️** 네이티브 형식에 가장 가깝게 매핑되는 .NET 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-110">**✔️ DO** use .NET types that map closest to the native type.</span></span> <span data-ttu-id="51246-111">예를 들어 C#에서 네이티브 형식이 `unsigned int`인 경우 `uint`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="51246-112">**✔️** 기본 동작과 다른 동작을 원하는 경우에만 `[In]` 및 `[Out]` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-112">**✔️ DO** only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="51246-113">**✔** 네이티브 배열 버퍼를 풀하려는 경우 <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType>을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-113">**✔️ CONSIDER** using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="51246-114">**✔️** 네이티브 라이브러리와 동일한 이름 및 대문자 표시를 사용하여 P/Invoke 선언을 클래스에 래핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-114">**✔️ CONSIDER** wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="51246-115">이렇게 하면 `[DllImport]` 특성이 C# `nameof` 언어 기능을 사용하여 네이티브 라이브러리의 이름을 전달하고 네이티브 라이브러리 이름의 철자가 잘못 입력되지 않았는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="51246-116">DllImport 특성 설정</span><span class="sxs-lookup"><span data-stu-id="51246-116">DllImport attribute settings</span></span>

| <span data-ttu-id="51246-117">설정</span><span class="sxs-lookup"><span data-stu-id="51246-117">Setting</span></span> | <span data-ttu-id="51246-118">기본값</span><span class="sxs-lookup"><span data-stu-id="51246-118">Default</span></span> | <span data-ttu-id="51246-119">권장 사항</span><span class="sxs-lookup"><span data-stu-id="51246-119">Recommendation</span></span> | <span data-ttu-id="51246-120">세부 정보</span><span class="sxs-lookup"><span data-stu-id="51246-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="51246-121">기본값 유지</span><span class="sxs-lookup"><span data-stu-id="51246-121">keep default</span></span>  | <span data-ttu-id="51246-122">이 옵션을 명시적으로 false로 설정하면 실패한 HRESULT 반환 값이 예외로 바뀝니다(그 결과로 정의의 반환 값은 Null이 됨).</span><span class="sxs-lookup"><span data-stu-id="51246-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="51246-123">API에 따라 다름</span><span class="sxs-lookup"><span data-stu-id="51246-123">depends on the API</span></span>  | <span data-ttu-id="51246-124">API에서 GetLastError를 사용하는 경우 이 옵션을 true로 설정하고, Marshal.GetLastWin32Error를 사용하여 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51246-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="51246-125">API에서 오류가 있음을 나타내는 조건을 설정하는 경우 실수로 덮어쓰지 않도록 다른 호출을 수행하기 전에 오류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51246-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="51246-126">`CharSet.None`(`CharSet.Ansi` 동작으로 대체됨)</span><span class="sxs-lookup"><span data-stu-id="51246-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="51246-127">정의에 문자열 또는 문자가 있는 경우 명시적으로 `CharSet.Unicode` 또는 `CharSet.Ansi` 사용</span><span class="sxs-lookup"><span data-stu-id="51246-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="51246-128">문자열의 마샬링 동작과 `false`인 경우 `ExactSpelling`에서 수행하는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-128">This specifies marshalling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="51246-129">`CharSet.Ansi`는 Unix에서 실제로 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="51246-130">_대부분_의 경우 Windows에서는 유니코드, Unix에서는 UTF8이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="51246-131">자세한 내용은 [문자 집합 문서](./charset.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51246-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="51246-132">이 옵션을 true로 설정하면 `CharSet` 설정 값(`CharSet.Ansi`는 “A”, `CharSet.Unicode`는 “W”)에 따라 “A” 또는 “W” 접미사가 있는 대체 함수 이름을 런타임이 찾지 않으므로 성능이 약간 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="51246-133">문자열 매개 변수</span><span class="sxs-lookup"><span data-stu-id="51246-133">String parameters</span></span>

<span data-ttu-id="51246-134">CharSet가 유니코드이거나 인수가 명시적으로 `[MarshalAs(UnmanagedType.LPWSTR)]`로 표시되고 문자열이 값으로 전달되는 경우(`ref` 또는 `out` 아님), 문자열이 고정되며 네이티브 코드에서 직접 사용됩니다(복사되지 않음).</span><span class="sxs-lookup"><span data-stu-id="51246-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="51246-135">문자열을 명시적으로 ANSI 처리하려는 경우가 아니면, `[DllImport]`를 `Charset.Unicode`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="51246-136">**❌** `[Out] string` 매개 변수를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-136">**❌ DO NOT** use `[Out] string` parameters.</span></span> <span data-ttu-id="51246-137">`[Out]` 특성을 사용하여 값으로 전달된 문자열 매개 변수는 문자열이 인턴 지정된 문자열인 경우 런타임을 불안정하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="51246-138">문자열 인터닝에 대한 자세한 내용은 <xref:System.String.Intern%2A?displayProperty=nameWithType> 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51246-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="51246-139">**❌** `StringBuilder` 매개 변수를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-139">**❌ AVOID** `StringBuilder` parameters.</span></span> <span data-ttu-id="51246-140">`StringBuilder` 마샬링은 ‘항상’ 네이티브 버퍼 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51246-140">`StringBuilder` marshalling *always* creates a native buffer copy.</span></span> <span data-ttu-id="51246-141">따라서 매우 비효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="51246-142">문자열을 사용하는 Windows API를 호출하는 일반적인 시나리오를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="51246-143">원하는 용량의 SB 생성(관리 용량 할당) **{1}**</span><span class="sxs-lookup"><span data-stu-id="51246-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="51246-144">호출</span><span class="sxs-lookup"><span data-stu-id="51246-144">Invoke</span></span>
   1. <span data-ttu-id="51246-145">네이티브 버퍼 할당 **{2}**</span><span class="sxs-lookup"><span data-stu-id="51246-145">Allocates a native buffer **{2}**</span></span>  
   2. <span data-ttu-id="51246-146">`[In]`_(`StringBuilder` 매개 변수의 기본값)_ 인 경우 콘텐츠 복사</span><span class="sxs-lookup"><span data-stu-id="51246-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>  
   3. <span data-ttu-id="51246-147">`[Out]` **{3}**_(`StringBuilder`의 기본값)_ 인 경우 새로 할당된 관리형 배열에 네이티브 버퍼 복사</span><span class="sxs-lookup"><span data-stu-id="51246-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>  
3. <span data-ttu-id="51246-148">`ToString()`이 다른 관리형 배열 **{4}** 할당</span><span class="sxs-lookup"><span data-stu-id="51246-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="51246-149">네이티브 코드에서 문자열을 가져오는 *{4}* 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="51246-150">이를 제한하는 가장 좋은 방법은 다른 호출에서 `StringBuilder`를 재사용하는 것이지만, 여전히 *1*개 할당만 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="51246-151">`ArrayPool`의 문자 버퍼를 사용하고 캐시하는 것이 훨씬 더 좋습니다. 그러면 후속 호출에서는 `ToString()`의 할당에만 바로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="51246-152">`StringBuilder`의 다른 문제는 항상 반환 버퍼 백업을 첫 번째 Null에 복사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="51246-153">다시 전달된 문자열이 종료되지 않았거나 이중 Null 종료 문자열인 경우 P/Invoke가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="51246-154">`StringBuilder`를 사용하는 경우 유의할 마지막 문제는 interop에 대해 항상 고려되는 숨겨진 Null이 용량에 포함되지 **않는**다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="51246-155">대부분의 API가 Null을 ‘포함’하는 버퍼 크기를 원하기 때문에 이 동작이 잘못 파악되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="51246-156">이로 인해 불필요한 할당이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="51246-157">또한 이 문제로 인해 런타임이 복사본 최소화를 위해 `StringBuilder` 마샬링을 최적화할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshalling to minimize copies.</span></span>

<span data-ttu-id="51246-158">**✔️** `ArrayPool`의 `char[]`을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-158">**✔️ CONSIDER** using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="51246-159">문자열 마샬링에 대한 자세한 내용은 [문자열의 기본 마샬링](../../framework/interop/default-marshaling-for-strings.md) 및 [문자열 마샬링 사용자 지정](customize-parameter-marshalling.md#customizing-string-parameters)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51246-159">For more information on string marshalling, see [Default Marshalling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshalling](customize-parameter-marshalling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="51246-160">__Windows 특정__</span><span class="sxs-lookup"><span data-stu-id="51246-160">__Windows Specific__</span></span>  
> <span data-ttu-id="51246-161">`[Out]` 문자열에 대해 CLR에서는 기본적으로 `CoTaskMemFree`를 사용하여 문자열을 해제하거나, `UnmanagedType.BSTR`로 표시된 문자열에 `SysStringFree`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-161">For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>  
<span data-ttu-id="51246-162">**출력 문자열 버퍼가 있는 대부분의 API의 경우:**</span><span class="sxs-lookup"><span data-stu-id="51246-162">**For most APIs with an output string buffer:**</span></span>  
> <span data-ttu-id="51246-163">전달된 문자 수에 Null이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-163">The passed in character count must include the null.</span></span> <span data-ttu-id="51246-164">반환된 값이 전달된 문자 수보다 작으면 호출이 성공하고 값은 후행 Null이 ‘없는’ 문자 수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-164">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="51246-165">그렇지 않으면 개수는 Null 문자를 ‘포함’하는 필수 버퍼 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-165">Otherwise the count is the required size of the buffer *including* the null character.</span></span>  
> - <span data-ttu-id="51246-166">5를 전달하면 4가 반환됩니다. 문자열이 4자이며 하나의 후행 Null로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-166">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="51246-167">5를 전달하면 6이 반환됩니다. 문자열이 5자이며 Null을 포함하려면 6자 버퍼가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-167">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>  
> [<span data-ttu-id="51246-168">문자열에 대한 Windows 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51246-168">Windows Data Types for Strings</span></span>](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="51246-169">부울 매개 변수 및 필드</span><span class="sxs-lookup"><span data-stu-id="51246-169">Boolean parameters and fields</span></span>

<span data-ttu-id="51246-170">부울은 문제가 발생하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-170">Booleans are easy to mess up.</span></span> <span data-ttu-id="51246-171">기본적으로 .NET `bool`은 4바이트 값인 Windows `BOOL`로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-171">By default, a .NET `bool` is marshalled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="51246-172">그러나 C 및 C++의 `_Bool` 및 `bool` 형식은 ‘1’바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-172">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="51246-173">이로 인해 반환 값의 절반이 버려지고 ‘잠재적’으로 결과가 변경될 수 있기 때문에 버그를 추적하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-173">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="51246-174">.NET `bool` 값을 C 또는 C++ `bool` 형식으로 마샬링하는 방법에 대한 자세한 내용은 [부울 필드 마샬링 사용자 지정](customize-struct-marshalling.md#customizing-boolean-field-marshalling) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51246-174">For more for information on marshalling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshalling](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span></span>

## <a name="guids"></a><span data-ttu-id="51246-175">GUID</span><span class="sxs-lookup"><span data-stu-id="51246-175">GUIDs</span></span>

<span data-ttu-id="51246-176">GUID는 시그니처에 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-176">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="51246-177">많은 Windows API는 `REFIID`와 같은 `GUID&` 형식 별칭을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-177">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="51246-178">ref로 전달된 경우 `ref` 또는 `[MarshalAs(UnmanagedType.LPStruct)]` 특성으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-178">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="51246-179">GUID</span><span class="sxs-lookup"><span data-stu-id="51246-179">GUID</span></span> | <span data-ttu-id="51246-180">by-ref GUID</span><span class="sxs-lookup"><span data-stu-id="51246-180">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="51246-181">**❌** `ref` GUID 매개 변수 이외의 항목에는 `[MarshalAs(UnmanagedType.LPStruct)]`를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-181">**❌ DO NOT** Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="51246-182">blittable 형식</span><span class="sxs-lookup"><span data-stu-id="51246-182">Blittable types</span></span>

<span data-ttu-id="51246-183">blittable 형식은 관리 코드와 네이티브 코드에 동일한 비트 수준 표현이 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-183">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="51246-184">따라서 네이티브 코드로(에서) 마샬링하기 위해 다른 형식으로 변환하지 않아도 되며, 이로 인해 성능이 향상되기 때문에 이 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-184">As such they do not need to be converted to another format to be marshalled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="51246-185">**blittable 형식:**</span><span class="sxs-lookup"><span data-stu-id="51246-185">**Blittable types:**</span></span>

- <span data-ttu-id="51246-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span><span class="sxs-lookup"><span data-stu-id="51246-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="51246-187">blittable 형식의 비중첩 1차원 배열(예: `int[]`)</span><span class="sxs-lookup"><span data-stu-id="51246-187">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="51246-188">인스턴스 필드에 blittable 값 형식만 사용하는, 고정 레이아웃의 구조체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="51246-188">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="51246-189">고정 레이아웃에는 `[StructLayout(LayoutKind.Sequential)]` 또는 `[StructLayout(LayoutKind.Explicit)]`이 필요함</span><span class="sxs-lookup"><span data-stu-id="51246-189">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="51246-190">구조체는 기본적으로 `LayoutKind.Sequential`이고, 클래스는 `LayoutKind.Auto`임</span><span class="sxs-lookup"><span data-stu-id="51246-190">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="51246-191">**비 blittable:**</span><span class="sxs-lookup"><span data-stu-id="51246-191">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="51246-192">**때때로 blittable**:</span><span class="sxs-lookup"><span data-stu-id="51246-192">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="51246-193">`char`, `string`</span><span class="sxs-lookup"><span data-stu-id="51246-193">`char`, `string`</span></span>

<span data-ttu-id="51246-194">blittable 형식이 참조로 전달된 경우 중간 버퍼에 복사되는 대신 마샬러에 의해 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-194">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="51246-195">클래스는 본질적으로 참조로 전달되고, 구조체는 `ref` 또는 `out`과 함께 사용할 경우 참조로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-195">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="51246-196">`char`는 1차원 배열의 blittable이거나, 포함하는 형식의 일부인 경우 `[StructLayout]` 및 `CharSet = CharSet.Unicode`로 명시적으로 표시됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="51246-196">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="51246-197">`string`은 다른 형식에 포함되지 않고 `[MarshalAs(UnmanagedType.LPWStr)]`로 표시된 인수로 전달되거나 `[DllImport]`에 `CharSet = CharSet.Unicode`가 설정되어 있는 경우 blittable입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-197">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="51246-198">고정 `GCHandle` 만들기를 시도하면 형식이 blittable인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-198">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="51246-199">형식이 문자열이 아니거나 blittable로 간주되지 않는 경우 `GCHandle.Alloc`에서 `ArgumentException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-199">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="51246-200">**✔️** 가능한 경우 구조체를 blittable로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-200">**✔️ DO** make your structures blittable when possible.</span></span>

<span data-ttu-id="51246-201">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51246-201">For more information, see:</span></span>

- [<span data-ttu-id="51246-202">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="51246-202">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)  
- [<span data-ttu-id="51246-203">형식 마샬링</span><span class="sxs-lookup"><span data-stu-id="51246-203">Type Marshalling</span></span>](type-marshalling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="51246-204">관리형 개체를 활성 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="51246-204">Keeping managed objects alive</span></span>

<span data-ttu-id="51246-205">`GC.KeepAlive()`는 KeepAlive 메서드가 적중될 때까지 개체가 범위 내에 유지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-205">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="51246-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef)를 사용하면 마샬러가 P/Invoke 기간에 개체를 활성 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="51246-207">메서드 시그니처에 `IntPtr` 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-207">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="51246-208">`SafeHandle`은 이 클래스를 효과적으로 대체하며 대신 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-208">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="51246-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle)을 사용하면 관리형 개체를 고정하고 개체에 대한 네이티브 포인터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="51246-210">기본 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-210">The basic pattern is:</span></span>  

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="51246-211">고정은 `GCHandle`의 기본값이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="51246-211">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="51246-212">다른 주요 패턴은 네이티브 코드를 통해 관리형 개체에 대한 참조를 전달하고, 일반적으로 콜백을 사용하여 관리 코드에 다시 전달하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-212">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="51246-213">패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-213">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="51246-214">메모리 누수를 방지하려면 `GCHandle`을 명시적으로 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-214">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="51246-215">일반적인 Windows 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51246-215">Common Windows data types</span></span>

<span data-ttu-id="51246-216">Windows API에서 일반적으로 사용되는 데이터 형식과 Windows 코드를 호출할 때 사용할 C# 형식 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-216">Here is a list of data types commonly used in Windows APIs and which C# types to use when calling into the Windows code.</span></span>

<span data-ttu-id="51246-217">다음 형식은 이름과 관계없이 32비트 및 64비트 Windows에서 동일한 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="51246-217">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="51246-218">너비</span><span class="sxs-lookup"><span data-stu-id="51246-218">Width</span></span> | <span data-ttu-id="51246-219">Windows</span><span class="sxs-lookup"><span data-stu-id="51246-219">Windows</span></span>          | <span data-ttu-id="51246-220">C(Windows)</span><span class="sxs-lookup"><span data-stu-id="51246-220">C (Windows)</span></span>          | <span data-ttu-id="51246-221">C#</span><span class="sxs-lookup"><span data-stu-id="51246-221">C#</span></span>       | <span data-ttu-id="51246-222">대체</span><span class="sxs-lookup"><span data-stu-id="51246-222">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="51246-223">32</span><span class="sxs-lookup"><span data-stu-id="51246-223">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="51246-224">8</span><span class="sxs-lookup"><span data-stu-id="51246-224">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="51246-225">8</span><span class="sxs-lookup"><span data-stu-id="51246-225">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="51246-226">8</span><span class="sxs-lookup"><span data-stu-id="51246-226">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="51246-227">8</span><span class="sxs-lookup"><span data-stu-id="51246-227">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="51246-228">16</span><span class="sxs-lookup"><span data-stu-id="51246-228">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="51246-229">16</span><span class="sxs-lookup"><span data-stu-id="51246-229">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="51246-230">16</span><span class="sxs-lookup"><span data-stu-id="51246-230">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="51246-231">16</span><span class="sxs-lookup"><span data-stu-id="51246-231">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="51246-232">16</span><span class="sxs-lookup"><span data-stu-id="51246-232">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="51246-233">32</span><span class="sxs-lookup"><span data-stu-id="51246-233">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="51246-234">32</span><span class="sxs-lookup"><span data-stu-id="51246-234">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="51246-235">32</span><span class="sxs-lookup"><span data-stu-id="51246-235">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="51246-236">32</span><span class="sxs-lookup"><span data-stu-id="51246-236">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="51246-237">64</span><span class="sxs-lookup"><span data-stu-id="51246-237">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="51246-238">64</span><span class="sxs-lookup"><span data-stu-id="51246-238">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="51246-239">64</span><span class="sxs-lookup"><span data-stu-id="51246-239">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="51246-240">64</span><span class="sxs-lookup"><span data-stu-id="51246-240">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="51246-241">64</span><span class="sxs-lookup"><span data-stu-id="51246-241">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="51246-242">32</span><span class="sxs-lookup"><span data-stu-id="51246-242">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="51246-243">32</span><span class="sxs-lookup"><span data-stu-id="51246-243">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |

<span data-ttu-id="51246-244">다음 형식은 포인터로, 플랫폼의 너비를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="51246-244">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="51246-245">이러한 형식에는 `IntPtr`/`UIntPtr`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-245">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="51246-246">서명된 포인터 형식(`IntPtr` 사용)</span><span class="sxs-lookup"><span data-stu-id="51246-246">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="51246-247">서명되지 않은 포인터 형식(`UIntPtr` 사용)</span><span class="sxs-lookup"><span data-stu-id="51246-247">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="51246-248">C `void*`인 Windows `PVOID`는 `IntPtr` 또는 `UIntPtr`로 마샬링할 수 있지만, 가능한 경우 `void*`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-248">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="51246-249">Windows 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51246-249">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="51246-250">데이터 형식 범위</span><span class="sxs-lookup"><span data-stu-id="51246-250">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="51246-251">구조체</span><span class="sxs-lookup"><span data-stu-id="51246-251">Structs</span></span>

<span data-ttu-id="51246-252">관리형 구조체는 스택에 생성되며, 메서드가 반환될 때까지 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-252">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="51246-253">정의상, “고정”되며 GC에 의해 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-253">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="51246-254">네이티브 코드에서 현재 메서드의 끝을 지나 포인터를 사용하지 않는 경우에도 안전하지 않은 코드 블록의 주소를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-254">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="51246-255">blittable 구조체는 마샬링 계층에서 직접 사용할 수 있으므로 성능이 훨씬 더 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="51246-255">Blittable structs are much more performant as they can simply be used directly by the marshalling layer.</span></span> <span data-ttu-id="51246-256">구조체를 blittable로 설정합니다(예: `bool` 사용 안 함).</span><span class="sxs-lookup"><span data-stu-id="51246-256">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="51246-257">자세한 내용은 [blittable 형식](#blittable-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51246-257">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="51246-258">구조체가 blittable인 경우 성능 향상을 위해 `Marshal.SizeOf<MyStruct>()` 대신 `sizeof()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-258">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="51246-259">위에서 언급한 대로, 고정 `GCHandle` 만들기를 시도하여 형식이 blittable인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-259">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="51246-260">형식이 문자열이 아니거나 blittable로 간주되지 않는 경우 `GCHandle.Alloc`에서 `ArgumentException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="51246-260">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="51246-261">정의의 구조체 포인터는 `ref`에 의해 전달되거나 `unsafe` 및 `*`를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-261">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="51246-262">**✔️** 공식 플랫폼 문서 또는 헤더에 사용되는 모양 및 이름에 최대한 가깝게 관리형 구조체를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="51246-262">**✔️ DO** match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="51246-263">**✔️** 성능 개선을 위해 blittable 구조체에 `Marshal.SizeOf<MyStruct>()` 대신 C# `sizeof()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-263">**✔️ DO** use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="51246-264">`INT_PTR Reserved1[2]` 등의 배열을 두 개의 `IntPtr` 필드인 `Reserved1a` 및 `Reserved1b`로 마샬링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-264">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="51246-265">네이티브 배열이 기본 형식인 경우 `fixed` 키워드를 사용하여 보다 명확하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-265">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="51246-266">예를 들어 `SYSTEM_PROCESS_INFORMATION`은 네이티브 헤더에서 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-266">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="51246-267">C#에서는 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-267">In C#, we can write it like this:</span></span>

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

<span data-ttu-id="51246-268">그러나 고정 버퍼에는 몇 가지 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-268">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="51246-269">비 blittable 형식의 고정 버퍼는 올바르게 마샬링되지 않으므로, 현재 위치 배열을 여러 개의 개별 필드로 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51246-269">Fixed buffers of non-blittable types won't be correctly marshalled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="51246-270">또한 .NET Framework 및 .NET Core 3.0 이전 버전에서 고정 버퍼 필드가 포함된 구조체를 비 blittable 구조체 내에 중첩하면 고정 버퍼 필드는 네이티브 코드로 올바르게 마샬링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51246-270">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshalled to native code.</span></span>
