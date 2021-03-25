---
description: C#의 기본 제공 nint 및 nuint 형식에 대해 알아봅니다.
title: nint 및 nuint 형식 - C# 참조
ms.date: 03/15/2021
f1_keywords:
- nint_CSharpKeyword
- nuint_CSharpKeyword
helpviewer_keywords:
- nint data type [C#]
- nuint data type [C#]
ms.openlocfilehash: fc779731d7f67fd0239f095d1dd17217a56622f6
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760825"
---
# <a name="nint-and-nuint-types-c-reference"></a><span data-ttu-id="11862-103">`nint` 및 `nuint` 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="11862-103">`nint` and `nuint` types (C# reference)</span></span>

<span data-ttu-id="11862-104">C# 9.0부터 `nint` 및 `nuint` 키워드를 사용하여 기본 크기 정수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-104">Starting in C# 9.0, you can use the `nint` and `nuint` keywords to define *native-sized integers*.</span></span> <span data-ttu-id="11862-105">이러한 정수는 32비트 프로세스에서 실행되는 경우 32비트 정수이고 64비트 프로세스에서 실행되는 경우 64비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="11862-105">These are 32-bit integers when running in a 32-bit process, or 64-bit integers when running in a 64-bit process.</span></span> <span data-ttu-id="11862-106">이들은 상호 운용성 시나리오, 하위 수준 라이브러리에 사용할 수 있고 정수 연산이 광범위하게 사용되는 시나리오에서 성능을 최적화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-106">They can be used for interop scenarios, low-level libraries, and to optimize performance in scenarios where integer math is used extensively.</span></span>

<span data-ttu-id="11862-107">기본 크기 정수 형식은 내부적으로 .NET 형식 <xref:System.IntPtr?displayProperty=nameWithType> 및 <xref:System.UIntPtr?displayProperty=nameWithType>로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11862-107">The native-sized integer types are represented internally as the .NET types <xref:System.IntPtr?displayProperty=nameWithType> and <xref:System.UIntPtr?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11862-108">다른 숫자 형식과 달리 키워드는 형식에 대한 별칭일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="11862-108">Unlike other numeric types, the keywords are not simply aliases for the types.</span></span> <span data-ttu-id="11862-109">다음 문은 서로 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-109">The following statements are not equivalent:</span></span>

```csharp
nint a = 1;
System.IntPtr a = 1;
```

<span data-ttu-id="11862-110">컴파일러는 `nint` 및 `nuint`에 대해 정수 형식에 적합한 작업 및 변환을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11862-110">The compiler provides operations and conversions for `nint` and `nuint` that are appropriate for integer types.</span></span>

## <a name="run-time-native-integer-size"></a><span data-ttu-id="11862-111">런타임 기본 정수 크기</span><span class="sxs-lookup"><span data-stu-id="11862-111">Run-time native integer size</span></span>

<span data-ttu-id="11862-112">런타임에 기본 크기 정수의 크기를 가져오려면 `sizeof()`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-112">To get the size of a native-sized integer at run time, you can use `sizeof()`.</span></span> <span data-ttu-id="11862-113">그러나 안전하지 않은 컨텍스트에서는 코드를 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11862-113">However, the code must be compiled in an unsafe context.</span></span> <span data-ttu-id="11862-114">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-114">For example:</span></span>

:::code language="csharp" source="snippets/shared/NativeIntegerTypes.cs" id="SizeOf":::

<span data-ttu-id="11862-115">정적 <xref:System.IntPtr.Size?displayProperty=nameWithType> 및 <xref:System.UIntPtr.Size?displayProperty=nameWithType> 속성에서 동등한 값을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-115">You can also get the equivalent value from the static <xref:System.IntPtr.Size?displayProperty=nameWithType> and <xref:System.UIntPtr.Size?displayProperty=nameWithType> properties.</span></span>

## <a name="minvalue-and-maxvalue"></a><span data-ttu-id="11862-116">MinValue 및 MaxValue</span><span class="sxs-lookup"><span data-stu-id="11862-116">MinValue and MaxValue</span></span>

<span data-ttu-id="11862-117">런타임에 기본 크기 정수의 최소값 및 최대값을 가져오려면 다음 예제와 같이 `MinValue` 및 `MaxValue`를 `nint` 및 `nuint` 키워드를 포함하는 정적 속성으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11862-117">To get the minimum and maximum values of native-sized integers at run time, use `MinValue` and `MaxValue` as static properties with the `nint` and `nuint` keywords, as in the following example:</span></span>

:::code language="csharp" source="snippets/shared/NativeIntegerTypes.cs" id="MinMax":::

## <a name="constants"></a><span data-ttu-id="11862-118">상수</span><span class="sxs-lookup"><span data-stu-id="11862-118">Constants</span></span>

<span data-ttu-id="11862-119">다음 범위에서 상수 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-119">You can use constant values in the following ranges:</span></span>

* <span data-ttu-id="11862-120">`nint`: <xref:System.Int32.MinValue?displayProperty=nameWithType>~<xref:System.Int32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11862-120">For `nint`: <xref:System.Int32.MinValue?displayProperty=nameWithType> to <xref:System.Int32.MaxValue?displayProperty=nameWithType>.</span></span>
* <span data-ttu-id="11862-121">`nuint`: <xref:System.UInt32.MinValue?displayProperty=nameWithType>~<xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11862-121">For `nuint`: <xref:System.UInt32.MinValue?displayProperty=nameWithType> to <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

## <a name="conversions"></a><span data-ttu-id="11862-122">변환</span><span class="sxs-lookup"><span data-stu-id="11862-122">Conversions</span></span>

<span data-ttu-id="11862-123">컴파일러는 다른 숫자 형식으로 암시적 변환과 명시적 변환을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11862-123">The compiler provides implicit and explicit conversions to other numeric types.</span></span> <span data-ttu-id="11862-124">자세한 내용은 [기본 제공 숫자 변환](numeric-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11862-124">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="literals"></a><span data-ttu-id="11862-125">리터럴</span><span class="sxs-lookup"><span data-stu-id="11862-125">Literals</span></span>

<span data-ttu-id="11862-126">기본 크기 정수 리터럴에 대한 직접 구문은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-126">There's no direct syntax for native-sized integer literals.</span></span> <span data-ttu-id="11862-127">`L`이 `long`을 나타내는 것과 같이 리터럴이 기본 크기 정수임을 나타내는 접미사는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-127">There's no suffix to indicate that a literal is a native-sized integer, such as `L` to indicate a `long`.</span></span> <span data-ttu-id="11862-128">대신 다른 정수 값의 암시적 또는 명시적 캐스트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-128">You can use implicit or explicit casts of other integer values instead.</span></span> <span data-ttu-id="11862-129">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-129">For example:</span></span>

```csharp
nint a = 42
nint a = (nint)42;
```

## <a name="unsupported-intptruintptr-members"></a><span data-ttu-id="11862-130">지원되지 않는 IntPtr/UIntPtr 멤버</span><span class="sxs-lookup"><span data-stu-id="11862-130">Unsupported IntPtr/UIntPtr members</span></span>

<span data-ttu-id="11862-131"><xref:System.IntPtr> 및 <xref:System.UIntPtr>의 다음 멤버는 `nint` 및 `nuint` 형식에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-131">The following members of <xref:System.IntPtr> and <xref:System.UIntPtr> aren't supported for `nint` and `nuint` types:</span></span>

* <span data-ttu-id="11862-132">매개 변수 있는 생성자</span><span class="sxs-lookup"><span data-stu-id="11862-132">Parameterized constructors</span></span>
* <xref:System.IntPtr.Add(System.IntPtr,System.Int32)>
* <xref:System.IntPtr.CompareTo%2A>
* <span data-ttu-id="11862-133"><xref:System.IntPtr.Size> - 대신 [sizeOf()](#run-time-native-integer-size)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11862-133"><xref:System.IntPtr.Size> - Use [sizeOf()](#run-time-native-integer-size) instead.</span></span> <span data-ttu-id="11862-134">`nint.Size`는 지원되지 않지만 `IntPtr.Size`를 사용하여 동등한 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11862-134">Although `nint.Size` isn't supported, you can use `IntPtr.Size` to get an equivalent value.</span></span>
* <xref:System.IntPtr.Subtract(System.IntPtr,System.Int32)>
* <xref:System.IntPtr.ToInt32%2A>
* <xref:System.IntPtr.ToInt64%2A>
* <xref:System.IntPtr.ToPointer%2A>
* <span data-ttu-id="11862-135"><xref:System.IntPtr.Zero> - 대신 0을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11862-135"><xref:System.IntPtr.Zero> - Use 0 instead.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="11862-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="11862-136">C# language specification</span></span>

<span data-ttu-id="11862-137">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md) 및 C# 9.0 기능 제안 노트의 [기본 크기 정수](~/_csharplang/proposals/csharp-9.0/native-integers.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11862-137">For more information, see the [C# language specification](~/_csharplang/spec/introduction.md) and the [Native-sized integers](~/_csharplang/proposals/csharp-9.0/native-integers.md) section of the C# 9.0 feature proposal notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="11862-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11862-138">See also</span></span>

- [<span data-ttu-id="11862-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="11862-139">C# reference</span></span>](../index.md)
- [<span data-ttu-id="11862-140">값 형식</span><span class="sxs-lookup"><span data-stu-id="11862-140">Value types</span></span>](value-types.md)
- [<span data-ttu-id="11862-141">정수 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="11862-141">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="11862-142">기본 제공 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="11862-142">Built-in numeric conversions</span></span>](numeric-conversions.md)
