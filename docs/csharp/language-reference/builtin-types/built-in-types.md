---
title: 기본 제공 형식- C# 참조
description: C# 기본 제공 값 및 참조 형식 배우기
ms.date: 03/15/2021
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.openlocfilehash: c2b1c736e17e55913ef1c593813717dd33efd6c3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759718"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="dbee1-103">기본 제공 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dbee1-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="dbee1-104">다음 표에서는 C# 기본 제공 [값](value-types.md) 형식을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="dbee1-105">C# 형식 키워드</span><span class="sxs-lookup"><span data-stu-id="dbee1-105">C# type keyword</span></span>|<span data-ttu-id="dbee1-106">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="dbee1-106">.NET type</span></span>|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`nint`](nint-nuint.md)|<xref:System.IntPtr?displayProperty=nameWithType>|
|[`nuint`](nint-nuint.md)|<xref:System.UIntPtr?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="dbee1-107">다음 표에서는 C# 기본 제공 [참조](../keywords/reference-types.md) 형식을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="dbee1-108">C# 형식 키워드</span><span class="sxs-lookup"><span data-stu-id="dbee1-108">C# type keyword</span></span>|<span data-ttu-id="dbee1-109">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="dbee1-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|
|[`dynamic`](reference-types.md#the-dynamic-type)|<xref:System.Object?displayProperty=nameWithType>|

<span data-ttu-id="dbee1-110">이전 표에서 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다([nint 및 nuint](nint-nuint.md) 제외).</span><span class="sxs-lookup"><span data-stu-id="dbee1-110">In the preceding tables, each C# type keyword from the left column (except [nint and nuint](nint-nuint.md)) is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="dbee1-111">서로 교환하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-111">They are interchangeable.</span></span> <span data-ttu-id="dbee1-112">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="dbee1-113">첫 번째 표의 마지막 두 행에 있는 `nint` 및 `nuint` 형식은 기본 크기 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-113">The `nint` and `nuint` types in the last two rows of the first table are native-sized integers.</span></span> <span data-ttu-id="dbee1-114">이들은 지정된 .NET 형식에 의해 내부적으로 표시되지만, 각 경우에 키워드와 .NET 형식을 서로 바꿔 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-114">They are represented internally by the indicated .NET types, but in each case the keyword and the .NET type are not interchangeable.</span></span> <span data-ttu-id="dbee1-115">컴파일러는 `nint` 및 `nuint`에 대한 작업 및 변환을 포인터 형식 `System.IntPtr` 및 `System.UIntPtr`에 대해 제공하지 않는 정수 형식으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-115">The compiler provides operations and conversions for `nint` and `nuint` as integer types that it doesn't provide for the pointer types `System.IntPtr` and `System.UIntPtr`.</span></span> <span data-ttu-id="dbee1-116">자세한 내용은 [`nint` 및 `nuint`형식](nint-nuint.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbee1-116">For more information, see [`nint` and `nuint` types](nint-nuint.md).</span></span>

<span data-ttu-id="dbee1-117">[`void`](void.md) 키워드는 형식이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-117">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="dbee1-118">이 키워드는 값을 반환하지 않는 메서드의 반환 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbee1-118">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbee1-119">참조</span><span class="sxs-lookup"><span data-stu-id="dbee1-119">See also</span></span>

- [<span data-ttu-id="dbee1-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dbee1-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="dbee1-121">C# 형식의 기본값</span><span class="sxs-lookup"><span data-stu-id="dbee1-121">Default values of C# types</span></span>](default-values.md)
