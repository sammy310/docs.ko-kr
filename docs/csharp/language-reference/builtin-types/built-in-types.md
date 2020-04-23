---
title: 기본 제공 형식- C# 참조
description: C# 기본 제공 값 및 참조 형식 배우기
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bf8823c6674b1ff3f0028a50df8ce8d0f803cfc1
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389488"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="9f7a1-103">기본 제공 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9f7a1-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="9f7a1-104">다음 표에서는 C# 기본 제공 [값](value-types.md) 형식을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a1-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="9f7a1-105">C# 형식 키워드</span><span class="sxs-lookup"><span data-stu-id="9f7a1-105">C# type keyword</span></span>|<span data-ttu-id="9f7a1-106">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="9f7a1-106">.NET type</span></span>|
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
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="9f7a1-107">다음 표에서는 C# 기본 제공 [참조](../keywords/reference-types.md) 형식을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a1-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="9f7a1-108">C# 형식 키워드</span><span class="sxs-lookup"><span data-stu-id="9f7a1-108">C# type keyword</span></span>|<span data-ttu-id="9f7a1-109">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="9f7a1-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="9f7a1-110">이전 표에서 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a1-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="9f7a1-111">서로 교환하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a1-111">They are interchangeable.</span></span> <span data-ttu-id="9f7a1-112">예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a1-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="9f7a1-113">[`void`](void.md) 키워드는 형식이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a1-113">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="9f7a1-114">이 키워드는 값을 반환하지 않는 메서드의 반환 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f7a1-114">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f7a1-115">참조</span><span class="sxs-lookup"><span data-stu-id="9f7a1-115">See also</span></span>

- [<span data-ttu-id="9f7a1-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9f7a1-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9f7a1-117">C# 형식의 기본값</span><span class="sxs-lookup"><span data-stu-id="9f7a1-117">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="9f7a1-118">`dynamic` 키워드</span><span class="sxs-lookup"><span data-stu-id="9f7a1-118">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
