---
title: 기본 제공 형식 표 - C# 참조
ms.custom: seodec18
description: 기본 제공 C# 형식의 키워드
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: d93176b850d84753106accef3bcaedab38f4ddc7
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306793"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="dc734-103">기본 제공 형식 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dc734-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="dc734-104">다음 표에서는 <xref:System> 네임스페이스에 미리 정의된 형식의 별칭인 기본 제공 C# 형식의 키워드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc734-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="dc734-105">C# 형식</span><span class="sxs-lookup"><span data-stu-id="dc734-105">C# type</span></span>|<span data-ttu-id="dc734-106">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="dc734-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="dc734-107">bool</span><span class="sxs-lookup"><span data-stu-id="dc734-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-108">byte</span><span class="sxs-lookup"><span data-stu-id="dc734-108">byte</span></span>](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="dc734-109">sbyte</span></span>](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-110">char</span><span class="sxs-lookup"><span data-stu-id="dc734-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-111">decimal</span><span class="sxs-lookup"><span data-stu-id="dc734-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-112">double</span><span class="sxs-lookup"><span data-stu-id="dc734-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-113">float</span><span class="sxs-lookup"><span data-stu-id="dc734-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-114">int</span><span class="sxs-lookup"><span data-stu-id="dc734-114">int</span></span>](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-115">uint</span><span class="sxs-lookup"><span data-stu-id="dc734-115">uint</span></span>](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-116">long</span><span class="sxs-lookup"><span data-stu-id="dc734-116">long</span></span>](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-117">ulong</span><span class="sxs-lookup"><span data-stu-id="dc734-117">ulong</span></span>](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-118">object</span><span class="sxs-lookup"><span data-stu-id="dc734-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-119">short</span><span class="sxs-lookup"><span data-stu-id="dc734-119">short</span></span>](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-120">ushort</span><span class="sxs-lookup"><span data-stu-id="dc734-120">ushort</span></span>](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="dc734-121">string</span><span class="sxs-lookup"><span data-stu-id="dc734-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="dc734-122">설명</span><span class="sxs-lookup"><span data-stu-id="dc734-122">Remarks</span></span>

<span data-ttu-id="dc734-123">`object` 및 `string`을 제외하고 표에 있는 모든 형식을 단순 형식이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc734-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="dc734-124">C# 형식 키워드와 해당 별칭은 서로 바꿔서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc734-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="dc734-125">예를 들어 다음 선언 중 하나를 사용하여 정수 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc734-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="dc734-126">[typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator) 연산자를 사용하여 지정된 형식을 나타내는 <xref:System.Type?displayProperty=nameWithType> 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dc734-126">Use the [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="dc734-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc734-127">See also</span></span>

- [<span data-ttu-id="dc734-128">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dc734-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="dc734-129">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dc734-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dc734-130">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="dc734-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dc734-131">값 형식</span><span class="sxs-lookup"><span data-stu-id="dc734-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="dc734-132">참조 형식</span><span class="sxs-lookup"><span data-stu-id="dc734-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="dc734-133">기본값 표</span><span class="sxs-lookup"><span data-stu-id="dc734-133">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="dc734-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="dc734-134">dynamic</span></span>](dynamic.md)
