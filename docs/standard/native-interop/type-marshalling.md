---
title: 형식 마샬링 - .NET
description: .NET에서 형식을 네이티브 표현으로 마샬링하는 방법을 알아봅니다.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: b4846f2e6cd945a25ec6a747c9038d48fe115559
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185417"
---
# <a name="type-marshalling"></a><span data-ttu-id="06fa6-103">형식 마샬링</span><span class="sxs-lookup"><span data-stu-id="06fa6-103">Type marshalling</span></span>

<span data-ttu-id="06fa6-104">**마샬링**은 관리 코드와 네이티브 코드 간에 변환해야 하는 경우 형식을 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-104">**Marshalling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="06fa6-105">관리 코드와 비관리 코드의 형식이 서로 다르기 때문에 마샬링이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-105">Marshalling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="06fa6-106">예를 들어 관리 코드에서는 `String`을 사용하지만 관리되지 않는 환경에서는 문자열이 유니코드(“와이드”), 비유니코드, null 종료, ASCII 등일 수 있습니다. 기본적으로 P/Invoke 하위 시스템은 이 문서에 설명된 기본 동작에 따라 올바른 작업을 수행하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="06fa6-107">그러나 추가 제어가 필요한 경우 [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) 특성을 사용하여 관리되지 않는 쪽에서 필요한 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="06fa6-108">예를 들어 문자열을 null 종료 ANSI 문자열로 보내려는 경우 다음과 같이 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshalling-common-types"></a><span data-ttu-id="06fa6-109">일반 형식을 마샬링하기 위한 기본 규칙</span><span class="sxs-lookup"><span data-stu-id="06fa6-109">Default rules for marshalling common types</span></span>

<span data-ttu-id="06fa6-110">일반적으로 런타임은 최소한의 사용자 작업이 필요하도록 마샬링 시 “올바른 작업”을 수행하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-110">Generally, the runtime tries to do the "right thing" when marshalling to require the least amount of work from you.</span></span> <span data-ttu-id="06fa6-111">다음 표에서는 매개 변수 또는 필드에 사용할 때 각 형식이 기본적으로 마샬링되는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-111">The following tables describe how each type is marshalled by default when used in a parameter or field.</span></span> <span data-ttu-id="06fa6-112">C99/C++11 고정 너비 정수 및 문자 형식은 다음 표의 내용이 모든 플랫폼에 적용되도록 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="06fa6-113">맞춤 및 크기 요구 사항이 이러한 형식과 동일한 모든 네이티브 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="06fa6-114">이 첫 번째 표에서는 마샬링이 P/Invoke 및 필드 마샬링에 대해 동일한 다양한 형식의 매핑을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-114">This first table describes the mappings for various types for whom the marshalling is the same for both P/Invoke and field marshalling.</span></span>

| <span data-ttu-id="06fa6-115">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-115">.NET Type</span></span> | <span data-ttu-id="06fa6-116">네이티브 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="06fa6-117">P/Invoke 또는 구조체의 `CharSet`에 따라 `char` 또는 `char16_t`입니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="06fa6-118">[문자 집합 문서](charset.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06fa6-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="06fa6-119">P/Invoke 또는 구조체의 `CharSet`에 따라 `char*` 또는 `char16_t*`입니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="06fa6-120">[문자 집합 문서](charset.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06fa6-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="06fa6-121">.NET 포인터 형식(예:</span><span class="sxs-lookup"><span data-stu-id="06fa6-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="06fa6-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="06fa6-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="06fa6-123">`System.Runtime.InteropServices.SafeHandle`에서 파생된 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="06fa6-124">`System.Runtime.InteropServices.CriticalHandle`에서 파생된 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="06fa6-125">Win32 `BOOL` 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="06fa6-126">COM `DECIMAL` 구조체</span><span class="sxs-lookup"><span data-stu-id="06fa6-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="06fa6-127">.NET 대리자</span><span class="sxs-lookup"><span data-stu-id="06fa6-127">.NET Delegate</span></span> | <span data-ttu-id="06fa6-128">네이티브 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="06fa6-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="06fa6-129">Win32 `DATE` 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="06fa6-130">Win32 `GUID` 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="06fa6-131">매개 변수 또는 구조체로 마샬링하는 경우 마샬링의 몇 가지 범주에 다른 기본값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-131">A few categories of marshalling have different defaults if you're marshalling as a parameter or structure.</span></span>

| <span data-ttu-id="06fa6-132">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-132">.NET Type</span></span> | <span data-ttu-id="06fa6-133">네이티브 형식(매개 변수)</span><span class="sxs-lookup"><span data-stu-id="06fa6-133">Native Type (Parameter)</span></span> | <span data-ttu-id="06fa6-134">네이티브 형식(필드)</span><span class="sxs-lookup"><span data-stu-id="06fa6-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="06fa6-135">.NET 배열</span><span class="sxs-lookup"><span data-stu-id="06fa6-135">.NET array</span></span> | <span data-ttu-id="06fa6-136">배열 요소의 네이티브 표현 배열 시작을 가리키는 포인터</span><span class="sxs-lookup"><span data-stu-id="06fa6-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="06fa6-137">`[MarshalAs]` 특성이 없으면 허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="06fa6-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="06fa6-138">`LayoutKind`가 `Sequential` 또는 `Explicit`인 클래스</span><span class="sxs-lookup"><span data-stu-id="06fa6-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="06fa6-139">클래스의 네이티브 표현을 가리키는 포인터</span><span class="sxs-lookup"><span data-stu-id="06fa6-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="06fa6-140">클래스의 네이티브 표현</span><span class="sxs-lookup"><span data-stu-id="06fa6-140">The native representation of the class</span></span> |

<span data-ttu-id="06fa6-141">다음 표에는 Windows 전용인 기본 마샬링 규칙이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-141">The following table includes the default marshalling rules that are Windows-only.</span></span> <span data-ttu-id="06fa6-142">비 Windows 플랫폼에서는 다음 형식을 마샬링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="06fa6-143">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-143">.NET Type</span></span> | <span data-ttu-id="06fa6-144">네이티브 형식(매개 변수)</span><span class="sxs-lookup"><span data-stu-id="06fa6-144">Native Type (Parameter)</span></span> | <span data-ttu-id="06fa6-145">네이티브 형식(필드)</span><span class="sxs-lookup"><span data-stu-id="06fa6-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="06fa6-146">COM 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06fa6-146">COM interface</span></span> | <span data-ttu-id="06fa6-147">`[MarshalAs]` 특성이 없으면 허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="06fa6-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="06fa6-148">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="06fa6-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="06fa6-149">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="06fa6-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="06fa6-150">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="06fa6-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="06fa6-151">1601년 1월 1일 자정 이후의 틱 수를 나타내는 `int64_t`</span><span class="sxs-lookup"><span data-stu-id="06fa6-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="06fa6-152">1601년 1월 1일 자정 이후의 틱 수를 나타내는 `int64_t`</span><span class="sxs-lookup"><span data-stu-id="06fa6-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="06fa6-153">일부 형식은 필드가 아닌 매개 변수로만 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-153">Some types can only be marshalled as parameters and not as fields.</span></span> <span data-ttu-id="06fa6-154">해당 형식은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="06fa6-155">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="06fa6-155">.NET Type</span></span> | <span data-ttu-id="06fa6-156">네이티브 형식(매개 변수만 해당)</span><span class="sxs-lookup"><span data-stu-id="06fa6-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="06fa6-157">P/Invoke의 `CharSet`에 따라 `char*` 또는 `char16_t*`입니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="06fa6-158">[문자 집합 문서](charset.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06fa6-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="06fa6-159">`va_list`(Windows x86/x64/arm64만 해당)</span><span class="sxs-lookup"><span data-stu-id="06fa6-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="06fa6-160">이러한 기본값이 원하는 동작을 정확히 수행하지 않는 경우 매개 변수의 마샬링 방식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-160">If these defaults don't do exactly what you want, you can customize how parameters are marshalled.</span></span> <span data-ttu-id="06fa6-161">[매개 변수 마샬링](customize-parameter-marshalling.md) 문서에서는 여러 매개 변수 형식의 마샬링 방식을 사용자 지정하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-161">The [parameter marshalling](customize-parameter-marshalling.md) article walks you through how to customize how different parameter types are marshalled.</span></span>

## <a name="marshalling-classes-and-structs"></a><span data-ttu-id="06fa6-162">클래스 및 구조체 마샬링</span><span class="sxs-lookup"><span data-stu-id="06fa6-162">Marshalling classes and structs</span></span>

<span data-ttu-id="06fa6-163">형식 마샬링의 또 다른 측면은 관리되지 않는 메서드에 구조체를 전달하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-163">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="06fa6-164">예를 들어 관리되지 않는 일부 메서드의 경우 매개 변수로 구조체가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-164">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="06fa6-165">이러한 경우 관리형 부분에서 해당 구조체 또는 클래스를 만들어 매개 변수로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-165">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="06fa6-166">그러나 클래스 정의만으로는 충분하지 않습니다. 클래스의 필드를 비관리형 구조체에 매핑하는 방법도 마샬러에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-166">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="06fa6-167">여기서 `StructLayout` 특성이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-167">Here the `StructLayout` attribute becomes useful.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="06fa6-168">앞의 코드는 `GetSystemTime()` 함수를 호출하는 간단한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-168">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="06fa6-169">흥미로운 부분은 줄 4에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-169">The interesting bit is on line 4.</span></span> <span data-ttu-id="06fa6-170">특성이 클래스의 필드를 다른 쪽(비관리)의 구조체에 순차적으로 매핑하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-170">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="06fa6-171">즉, 다음 예제와 같이 비관리형 구조체에 대응해야 하므로 필드의 이름 지정은 중요하지 않고 해당 순서만 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-171">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

<span data-ttu-id="06fa6-172">구조체에 대한 기본 마샬링이 필요한 것이 아닌 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-172">Sometimes the default marshalling for your structure doesn't do what you need.</span></span> <span data-ttu-id="06fa6-173">[구조 마샬링 사용자 지정](./customize-struct-marshalling.md) 문서에서는 구조체의 마샬링 방식을 사용자 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06fa6-173">The [Customizing structure marshalling](./customize-struct-marshalling.md) article teaches you how to customize how your structure is marshaled.</span></span>
