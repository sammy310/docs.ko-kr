---
title: 기본 상호 운용성 모범 사례 - .NET
description: .NET에서 기본 구성 요소와 인터페이스하는 모범 사례를 알아봅니다.
ms.date: 01/18/2019
ms.openlocfilehash: 9486256b815856c0c283f5fe231be3d35d6e8f00
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742755"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="74af9-103">기본 상호 운용성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="74af9-103">Native interoperability best practices</span></span>

<span data-ttu-id="74af9-104">.NET에서는 기본 상호 운용성 코드를 사용자 지정하는 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="74af9-105">이 문서에는 Microsoft .NET 팀이 네이티브 상호 운용성을 위해 따르는 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="74af9-106">일반 지침</span><span class="sxs-lookup"><span data-stu-id="74af9-106">General guidance</span></span>

<span data-ttu-id="74af9-107">이 섹션의 지침은 모든 interop 시나리오에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="74af9-108">메서드 및 매개 변수에 대해 호출 하려는 네이티브 메서드로 동일한 이름 및 대/소문자를 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-108">✔️ DO use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="74af9-109">상수 값에 대해 동일한 이름 지정 및 대문자 표시를 사용 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="74af9-109">✔️ CONSIDER using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="74af9-110">✔️ 네이티브 형식과 가장 가깝게 매핑되는 .NET 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-110">✔️ DO use .NET types that map closest to the native type.</span></span> <span data-ttu-id="74af9-111">예를 들어 C#에서 네이티브 형식이 `unsigned int`인 경우 `uint`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="74af9-112">원하는 동작이 기본 동작과 다를 경우에만 ✔️ `[In]` 및 `[Out]` 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-112">✔️ DO only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="74af9-113">✔️ <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType>를 사용 하 여 네이티브 배열 버퍼를 풀 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-113">✔️ CONSIDER using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="74af9-114">네이티브 라이브러리와 이름 및 대/소문자가 동일한 클래스에서 P/Invoke 선언을 래핑하는 것이 좋습니다. ✔️</span><span class="sxs-lookup"><span data-stu-id="74af9-114">✔️ CONSIDER wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="74af9-115">이렇게 하면 `[DllImport]` 특성이 C# `nameof` 언어 기능을 사용하여 네이티브 라이브러리의 이름을 전달하고 네이티브 라이브러리 이름의 철자가 잘못 입력되지 않았는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="74af9-116">DllImport 특성 설정</span><span class="sxs-lookup"><span data-stu-id="74af9-116">DllImport attribute settings</span></span>

| <span data-ttu-id="74af9-117">설정</span><span class="sxs-lookup"><span data-stu-id="74af9-117">Setting</span></span> | <span data-ttu-id="74af9-118">기본</span><span class="sxs-lookup"><span data-stu-id="74af9-118">Default</span></span> | <span data-ttu-id="74af9-119">권장 구성</span><span class="sxs-lookup"><span data-stu-id="74af9-119">Recommendation</span></span> | <span data-ttu-id="74af9-120">자세히</span><span class="sxs-lookup"><span data-stu-id="74af9-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="74af9-121">기본값 유지</span><span class="sxs-lookup"><span data-stu-id="74af9-121">keep default</span></span>  | <span data-ttu-id="74af9-122">이 옵션을 명시적으로 false로 설정하면 실패한 HRESULT 반환 값이 예외로 바뀝니다(그 결과로 정의의 반환 값은 Null이 됨).</span><span class="sxs-lookup"><span data-stu-id="74af9-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="74af9-123">API에 따라 다름</span><span class="sxs-lookup"><span data-stu-id="74af9-123">depends on the API</span></span>  | <span data-ttu-id="74af9-124">API에서 GetLastError를 사용하는 경우 이 옵션을 true로 설정하고, Marshal.GetLastWin32Error를 사용하여 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="74af9-125">API에서 오류가 있음을 나타내는 조건을 설정하는 경우 실수로 덮어쓰지 않도록 다른 호출을 수행하기 전에 오류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="74af9-126">`CharSet.None`(`CharSet.Ansi` 동작으로 대체됨)</span><span class="sxs-lookup"><span data-stu-id="74af9-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="74af9-127">정의에 문자열 또는 문자가 있는 경우 명시적으로 `CharSet.Unicode` 또는 `CharSet.Ansi` 사용</span><span class="sxs-lookup"><span data-stu-id="74af9-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="74af9-128">문자열의 마샬링 동작과 `false`인 경우 `ExactSpelling`에서 수행하는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-128">This specifies marshaling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="74af9-129">`CharSet.Ansi`는 Unix에서 실제로 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="74af9-130">_대부분_의 경우 Windows에서는 유니코드, Unix에서는 UTF8이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="74af9-131">자세한 내용은 [문자 집합 문서](./charset.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74af9-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="74af9-132">이 옵션을 true로 설정하면 `CharSet` 설정 값(`CharSet.Ansi`는 “A”, `CharSet.Unicode`는 “W”)에 따라 “A” 또는 “W” 접미사가 있는 대체 함수 이름을 런타임이 찾지 않으므로 성능이 약간 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="74af9-133">문자열 매개 변수</span><span class="sxs-lookup"><span data-stu-id="74af9-133">String parameters</span></span>

<span data-ttu-id="74af9-134">CharSet이 유니코드 이거나 인수가 `[MarshalAs(UnmanagedType.LPWSTR)]`로 명시적으로 표시 되 _고_ 문자열이 값 (`ref` 또는 `out`)으로 전달 되는 경우 문자열은 복사 되지 않고 네이티브 코드에서 직접 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="74af9-135">문자열을 명시적으로 ANSI 처리하려는 경우가 아니면, `[DllImport]`를 `Charset.Unicode`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="74af9-136">❌ `[Out] string` 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-136">❌ DO NOT use `[Out] string` parameters.</span></span> <span data-ttu-id="74af9-137">`[Out]` 특성을 사용하여 값으로 전달된 문자열 매개 변수는 문자열이 인턴 지정된 문자열인 경우 런타임을 불안정하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="74af9-138">문자열 인터닝에 대한 자세한 내용은 <xref:System.String.Intern%2A?displayProperty=nameWithType> 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74af9-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="74af9-139">❌ `StringBuilder` 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-139">❌ AVOID `StringBuilder` parameters.</span></span> <span data-ttu-id="74af9-140">`StringBuilder` 마샬링은 *항상* 네이티브 버퍼 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-140">`StringBuilder` marshaling *always* creates a native buffer copy.</span></span> <span data-ttu-id="74af9-141">따라서 매우 비효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="74af9-142">문자열을 사용하는 Windows API를 호출하는 일반적인 시나리오를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="74af9-143">원하는 용량의 SB 생성(관리 용량 할당) **{1}**</span><span class="sxs-lookup"><span data-stu-id="74af9-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="74af9-144">호출</span><span class="sxs-lookup"><span data-stu-id="74af9-144">Invoke</span></span>
   1. <span data-ttu-id="74af9-145">네이티브 버퍼 할당 **{2}**</span><span class="sxs-lookup"><span data-stu-id="74af9-145">Allocates a native buffer **{2}**</span></span>
   2. <span data-ttu-id="74af9-146">`[In]` 경우 _(`StringBuilder` 매개 변수의 기본값)_ 콘텐츠를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>
   3. <span data-ttu-id="74af9-147">**{3}** `[Out]` 경우에는 네이티브 버퍼를 새로 할당 된 관리 되는 배열에 복사 합니다 _(`StringBuilder`에 대 한 기본값 이기도)_ .</span><span class="sxs-lookup"><span data-stu-id="74af9-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>
3. <span data-ttu-id="74af9-148">`ToString()`이 다른 관리형 배열 **{4}** 할당</span><span class="sxs-lookup"><span data-stu-id="74af9-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="74af9-149">네이티브 코드에서 문자열을 가져오는 *{4}* 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="74af9-150">이를 제한하는 가장 좋은 방법은 다른 호출에서 `StringBuilder`를 재사용하는 것이지만, 여전히 *1*개 할당만 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="74af9-151">`ArrayPool`의 문자 버퍼를 사용하고 캐시하는 것이 훨씬 더 좋습니다. 그러면 후속 호출에서는 `ToString()`의 할당에만 바로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="74af9-152">`StringBuilder`의 다른 문제는 항상 반환 버퍼 백업을 첫 번째 Null에 복사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="74af9-153">다시 전달된 문자열이 종료되지 않았거나 이중 Null 종료 문자열인 경우 P/Invoke가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="74af9-154">`StringBuilder`를 사용하는 경우 유의할 마지막 문제는 interop에 대해 항상 고려되는 숨겨진 Null이 용량에 포함되지 **않는**다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="74af9-155">대부분의 API가 Null을 ‘포함’하는 버퍼 크기를 원하기 때문에 이 동작이 잘못 파악되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="74af9-156">이로 인해 불필요한 할당이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="74af9-157">또한 이 문제로 인해 런타임이 복사본 최소화를 위해 `StringBuilder` 마샬링을 최적화할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshaling to minimize copies.</span></span>

<span data-ttu-id="74af9-158">✔️ `ArrayPool`에서 `char[]`를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-158">✔️ CONSIDER using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="74af9-159">문자열 마샬링에 대한 자세한 내용은 [문자열의 기본 마샬링](../../framework/interop/default-marshaling-for-strings.md) 및 [문자열 마샬링 사용자 지정](customize-parameter-marshaling.md#customizing-string-parameters)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74af9-159">For more information on string marshaling, see [Default Marshaling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshaling](customize-parameter-marshaling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="74af9-160">__Windows 관련__ `[Out]` 문자열의 경우 CLR은 기본적으로 `CoTaskMemFree`를 사용 하 여 `UnmanagedType.BSTR`로 표시 된 문자열에 대 한 문자열 또는 `SysStringFree`를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-160">__Windows Specific__ For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>
> <span data-ttu-id="74af9-161">**출력 문자열 버퍼를 사용 하는 대부분의 api:** 전달 된 문자 수는 null을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-161">**For most APIs with an output string buffer:** The passed in character count must include the null.</span></span> <span data-ttu-id="74af9-162">반환된 값이 전달된 문자 수보다 작으면 호출이 성공하고 값은 후행 Null이 ‘없는’ 문자 수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-162">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="74af9-163">그렇지 않으면 개수는 Null 문자를 ‘포함’하는 필수 버퍼 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-163">Otherwise the count is the required size of the buffer *including* the null character.</span></span>
>
> - <span data-ttu-id="74af9-164">5를 전달 하 고, 4를 전달 합니다. 문자열은 후행 null을 포함 하는 4 자 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-164">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="74af9-165">5를 전달 하 고, 6을 전달 합니다. 문자열의 길이가 5 자이 고 null을 보유 하기 위해 6 문자 버퍼가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-165">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>
> [<span data-ttu-id="74af9-166">문자열에 대한 Windows 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="74af9-166">Windows Data Types for Strings</span></span>](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="74af9-167">부울 매개 변수 및 필드</span><span class="sxs-lookup"><span data-stu-id="74af9-167">Boolean parameters and fields</span></span>

<span data-ttu-id="74af9-168">부울은 문제가 발생하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-168">Booleans are easy to mess up.</span></span> <span data-ttu-id="74af9-169">기본적으로 .NET `bool`은 4바이트 값인 Windows `BOOL`로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-169">By default, a .NET `bool` is marshaled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="74af9-170">그러나 C 및 C++의 `_Bool` 및 `bool` 형식은 ‘1’바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-170">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="74af9-171">이로 인해 반환 값의 절반이 버려지고 ‘잠재적’으로 결과가 변경될 수 있기 때문에 버그를 추적하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-171">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="74af9-172">.NET `bool` 값을 C 또는 C++ `bool` 형식으로 마샬링하는 방법에 대한 자세한 내용은 [부울 필드 마샬링 사용자 지정](customize-struct-marshaling.md#customizing-boolean-field-marshaling) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74af9-172">For more for information on marshaling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshaling](customize-struct-marshaling.md#customizing-boolean-field-marshaling).</span></span>

## <a name="guids"></a><span data-ttu-id="74af9-173">GUID</span><span class="sxs-lookup"><span data-stu-id="74af9-173">GUIDs</span></span>

<span data-ttu-id="74af9-174">GUID는 시그니처에 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-174">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="74af9-175">많은 Windows API는 `REFIID`와 같은 `GUID&` 형식 별칭을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-175">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="74af9-176">ref로 전달된 경우 `ref` 또는 `[MarshalAs(UnmanagedType.LPStruct)]` 특성으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-176">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="74af9-177">GUID</span><span class="sxs-lookup"><span data-stu-id="74af9-177">GUID</span></span> | <span data-ttu-id="74af9-178">by-ref GUID</span><span class="sxs-lookup"><span data-stu-id="74af9-178">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="74af9-179">❌ `ref` GUID 매개 변수 이외의 항목에는 `[MarshalAs(UnmanagedType.LPStruct)]` 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-179">❌ DO NOT Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="74af9-180">blittable 형식</span><span class="sxs-lookup"><span data-stu-id="74af9-180">Blittable types</span></span>

<span data-ttu-id="74af9-181">blittable 형식은 관리 코드와 네이티브 코드에 동일한 비트 수준 표현이 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-181">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="74af9-182">따라서 네이티브 코드로(에서) 마샬링하기 위해 다른 형식으로 변환하지 않아도 되며, 이로 인해 성능이 향상되기 때문에 이 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-182">As such they do not need to be converted to another format to be marshaled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="74af9-183">**blittable 형식:**</span><span class="sxs-lookup"><span data-stu-id="74af9-183">**Blittable types:**</span></span>

- <span data-ttu-id="74af9-184">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span><span class="sxs-lookup"><span data-stu-id="74af9-184">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="74af9-185">blittable 형식의 비중첩 1차원 배열(예: `int[]`)</span><span class="sxs-lookup"><span data-stu-id="74af9-185">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="74af9-186">인스턴스 필드에 blittable 값 형식만 사용하는, 고정 레이아웃의 구조체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="74af9-186">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="74af9-187">고정 레이아웃에는 `[StructLayout(LayoutKind.Sequential)]` 또는 `[StructLayout(LayoutKind.Explicit)]`이 필요함</span><span class="sxs-lookup"><span data-stu-id="74af9-187">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="74af9-188">구조체는 기본적으로 `LayoutKind.Sequential`이고, 클래스는 `LayoutKind.Auto`임</span><span class="sxs-lookup"><span data-stu-id="74af9-188">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="74af9-189">**비 blittable:**</span><span class="sxs-lookup"><span data-stu-id="74af9-189">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="74af9-190">**때때로 blittable**:</span><span class="sxs-lookup"><span data-stu-id="74af9-190">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="74af9-191">`char`, `string`</span><span class="sxs-lookup"><span data-stu-id="74af9-191">`char`, `string`</span></span>

<span data-ttu-id="74af9-192">blittable 형식이 참조로 전달된 경우 중간 버퍼에 복사되는 대신 마샬러에 의해 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-192">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="74af9-193">클래스는 본질적으로 참조로 전달되고, 구조체는 `ref` 또는 `out`과 함께 사용할 경우 참조로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-193">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="74af9-194">`char`는 1차원 배열의 blittable이거나, 포함하는 형식의 일부인 경우 `[StructLayout]` 및 `CharSet = CharSet.Unicode`로 명시적으로 표시됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="74af9-194">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="74af9-195">`string`은 다른 형식에 포함되지 않고 `[MarshalAs(UnmanagedType.LPWStr)]`로 표시된 인수로 전달되거나 `[DllImport]`에 `CharSet = CharSet.Unicode`가 설정되어 있는 경우 blittable입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-195">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="74af9-196">고정 `GCHandle` 만들기를 시도하면 형식이 blittable인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-196">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="74af9-197">형식이 문자열이 아니거나 blittable로 간주되지 않는 경우 `GCHandle.Alloc`에서 `ArgumentException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-197">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="74af9-198">가능 하면 구조체를 blittable으로 설정 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-198">✔️ DO make your structures blittable when possible.</span></span>

<span data-ttu-id="74af9-199">자세한 내용은  항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74af9-199">For more information, see:</span></span>

- [<span data-ttu-id="74af9-200">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="74af9-200">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)
- [<span data-ttu-id="74af9-201">형식 마샬링</span><span class="sxs-lookup"><span data-stu-id="74af9-201">Type Marshaling</span></span>](type-marshaling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="74af9-202">관리형 개체를 활성 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="74af9-202">Keeping managed objects alive</span></span>

<span data-ttu-id="74af9-203">`GC.KeepAlive()`는 KeepAlive 메서드가 적중될 때까지 개체가 범위 내에 유지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-203">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="74af9-204">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef)를 사용하면 마샬러가 P/Invoke 기간에 개체를 활성 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-204">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="74af9-205">메서드 시그니처에 `IntPtr` 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-205">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="74af9-206">`SafeHandle`은 이 클래스를 효과적으로 대체하며 대신 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-206">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="74af9-207">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle)을 사용하면 관리형 개체를 고정하고 개체에 대한 네이티브 포인터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-207">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="74af9-208">기본 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-208">The basic pattern is:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="74af9-209">고정은 `GCHandle`의 기본값이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-209">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="74af9-210">다른 주요 패턴은 네이티브 코드를 통해 관리형 개체에 대한 참조를 전달하고, 일반적으로 콜백을 사용하여 관리 코드에 다시 전달하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-210">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="74af9-211">패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-211">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="74af9-212">메모리 누수를 방지하려면 `GCHandle`을 명시적으로 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-212">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="74af9-213">일반적인 Windows 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="74af9-213">Common Windows data types</span></span>

<span data-ttu-id="74af9-214">Windows API에서 일반적으로 사용되는 데이터 형식과 Windows 코드를 호출할 때 사용할 C# 형식 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-214">Here is a list of data types commonly used in Windows APIs and which C# types to use when calling into the Windows code.</span></span>

<span data-ttu-id="74af9-215">다음 형식은 이름과 관계없이 32비트 및 64비트 Windows에서 동일한 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-215">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="74af9-216">너비</span><span class="sxs-lookup"><span data-stu-id="74af9-216">Width</span></span> | <span data-ttu-id="74af9-217">Windows</span><span class="sxs-lookup"><span data-stu-id="74af9-217">Windows</span></span>          | <span data-ttu-id="74af9-218">C(Windows)</span><span class="sxs-lookup"><span data-stu-id="74af9-218">C (Windows)</span></span>          | <span data-ttu-id="74af9-219">C#</span><span class="sxs-lookup"><span data-stu-id="74af9-219">C#</span></span>       | <span data-ttu-id="74af9-220">대체</span><span class="sxs-lookup"><span data-stu-id="74af9-220">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="74af9-221">32</span><span class="sxs-lookup"><span data-stu-id="74af9-221">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="74af9-222">8</span><span class="sxs-lookup"><span data-stu-id="74af9-222">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="74af9-223">8</span><span class="sxs-lookup"><span data-stu-id="74af9-223">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="74af9-224">8</span><span class="sxs-lookup"><span data-stu-id="74af9-224">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="74af9-225">8</span><span class="sxs-lookup"><span data-stu-id="74af9-225">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="74af9-226">16</span><span class="sxs-lookup"><span data-stu-id="74af9-226">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="74af9-227">16</span><span class="sxs-lookup"><span data-stu-id="74af9-227">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="74af9-228">16</span><span class="sxs-lookup"><span data-stu-id="74af9-228">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="74af9-229">16</span><span class="sxs-lookup"><span data-stu-id="74af9-229">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="74af9-230">16</span><span class="sxs-lookup"><span data-stu-id="74af9-230">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="74af9-231">32</span><span class="sxs-lookup"><span data-stu-id="74af9-231">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="74af9-232">32</span><span class="sxs-lookup"><span data-stu-id="74af9-232">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="74af9-233">32</span><span class="sxs-lookup"><span data-stu-id="74af9-233">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="74af9-234">32</span><span class="sxs-lookup"><span data-stu-id="74af9-234">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="74af9-235">64개</span><span class="sxs-lookup"><span data-stu-id="74af9-235">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="74af9-236">64개</span><span class="sxs-lookup"><span data-stu-id="74af9-236">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="74af9-237">64개</span><span class="sxs-lookup"><span data-stu-id="74af9-237">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="74af9-238">64개</span><span class="sxs-lookup"><span data-stu-id="74af9-238">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="74af9-239">64개</span><span class="sxs-lookup"><span data-stu-id="74af9-239">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="74af9-240">32</span><span class="sxs-lookup"><span data-stu-id="74af9-240">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="74af9-241">32</span><span class="sxs-lookup"><span data-stu-id="74af9-241">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |

<span data-ttu-id="74af9-242">다음 형식은 포인터로, 플랫폼의 너비를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-242">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="74af9-243">이러한 형식에는 `IntPtr`/`UIntPtr`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-243">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="74af9-244">서명된 포인터 형식(`IntPtr` 사용)</span><span class="sxs-lookup"><span data-stu-id="74af9-244">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="74af9-245">서명되지 않은 포인터 형식(`UIntPtr` 사용)</span><span class="sxs-lookup"><span data-stu-id="74af9-245">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="74af9-246">C `void*`인 Windows `PVOID`는 `IntPtr` 또는 `UIntPtr`로 마샬링할 수 있지만, 가능한 경우 `void*`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-246">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="74af9-247">Windows 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="74af9-247">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="74af9-248">데이터 형식 범위</span><span class="sxs-lookup"><span data-stu-id="74af9-248">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="74af9-249">Structs</span><span class="sxs-lookup"><span data-stu-id="74af9-249">Structs</span></span>

<span data-ttu-id="74af9-250">관리형 구조체는 스택에 생성되며, 메서드가 반환될 때까지 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-250">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="74af9-251">정의상, “고정”되며 GC에 의해 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-251">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="74af9-252">네이티브 코드에서 현재 메서드의 끝을 지나 포인터를 사용하지 않는 경우에도 안전하지 않은 코드 블록의 주소를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-252">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="74af9-253">blittable 구조체는 마샬링 계층에서 직접 사용할 수 있으므로 성능이 훨씬 더 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-253">Blittable structs are much more performant as they can simply be used directly by the marshaling layer.</span></span> <span data-ttu-id="74af9-254">구조체를 blittable로 설정합니다(예: `bool` 사용 안 함).</span><span class="sxs-lookup"><span data-stu-id="74af9-254">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="74af9-255">자세한 내용은 [blittable 형식](#blittable-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74af9-255">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="74af9-256">구조체가 blittable인 경우 성능 향상을 위해 `Marshal.SizeOf<MyStruct>()` 대신 `sizeof()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-256">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="74af9-257">위에서 언급한 대로, 고정 `GCHandle` 만들기를 시도하여 형식이 blittable인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-257">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="74af9-258">형식이 문자열이 아니거나 blittable로 간주되지 않는 경우 `GCHandle.Alloc`에서 `ArgumentException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-258">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="74af9-259">정의의 구조체 포인터는 `ref`에 의해 전달되거나 `unsafe` 및 `*`를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-259">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="74af9-260">✔️는 관리 되는 구조체를 공식 플랫폼 설명서 또는 헤더에 사용 되는 모양 및 이름에 최대한 가깝게 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-260">✔️ DO match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="74af9-261">✔️는 blittable 구조 C# 에 대해 `Marshal.SizeOf<MyStruct>()` 대신 `sizeof()`를 사용 하 여 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-261">✔️ DO use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="74af9-262">`INT_PTR Reserved1[2]` 등의 배열을 두 개의 `IntPtr` 필드인 `Reserved1a` 및 `Reserved1b`로 마샬링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-262">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="74af9-263">네이티브 배열이 기본 형식인 경우 `fixed` 키워드를 사용하여 보다 명확하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-263">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="74af9-264">예를 들어 `SYSTEM_PROCESS_INFORMATION`은 네이티브 헤더에서 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-264">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="74af9-265">C#에서는 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-265">In C#, we can write it like this:</span></span>

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

<span data-ttu-id="74af9-266">그러나 고정 버퍼에는 몇 가지 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-266">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="74af9-267">비 blittable 형식의 고정 버퍼는 올바르게 마샬링되지 않으므로, 현재 위치 배열을 여러 개의 개별 필드로 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-267">Fixed buffers of non-blittable types won't be correctly marshaled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="74af9-268">또한 .NET Framework 및 .NET Core 3.0 이전 버전에서 고정 버퍼 필드가 포함된 구조체를 비 blittable 구조체 내에 중첩하면 고정 버퍼 필드는 네이티브 코드로 올바르게 마샬링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74af9-268">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshaled to native code.</span></span>
