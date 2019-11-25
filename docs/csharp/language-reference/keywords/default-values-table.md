---
title: 기본값 표 - C# 참조
ms.custom: seodec18
description: C# 형식의 기본값을 알아봅니다.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 2f1ad5cc029b93261153e46d854cd8bf3e31ce92
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428531"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="d78eb-103">기본값 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d78eb-103">Default values table (C# reference)</span></span>

<span data-ttu-id="d78eb-104">다음 표는 C# 형식의 기본값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="d78eb-105">형식</span><span class="sxs-lookup"><span data-stu-id="d78eb-105">Type</span></span>|<span data-ttu-id="d78eb-106">기본값</span><span class="sxs-lookup"><span data-stu-id="d78eb-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="d78eb-107">임의 참조 형식</span><span class="sxs-lookup"><span data-stu-id="d78eb-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="d78eb-108">임의 [기본 제공 정수 숫자 유형](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="d78eb-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="d78eb-109">0(영)</span><span class="sxs-lookup"><span data-stu-id="d78eb-109">0 (zero)</span></span>|
|<span data-ttu-id="d78eb-110">임의 [기본 제공 부동 소수점 숫자 유형](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="d78eb-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="d78eb-111">0(영)</span><span class="sxs-lookup"><span data-stu-id="d78eb-111">0 (zero)</span></span>|
|[<span data-ttu-id="d78eb-112">bool</span><span class="sxs-lookup"><span data-stu-id="d78eb-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="d78eb-113">char</span><span class="sxs-lookup"><span data-stu-id="d78eb-113">char</span></span>](../builtin-types/char.md)|<span data-ttu-id="d78eb-114">`'\0'`(U+0000)</span><span class="sxs-lookup"><span data-stu-id="d78eb-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="d78eb-115">enum</span><span class="sxs-lookup"><span data-stu-id="d78eb-115">enum</span></span>](enum.md)|<span data-ttu-id="d78eb-116">식 `(E)0`로 생성한 값이며 여기서 `E`는 열거형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="d78eb-117">struct</span><span class="sxs-lookup"><span data-stu-id="d78eb-117">struct</span></span>](struct.md)|<span data-ttu-id="d78eb-118">모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="d78eb-119">Any [Null 허용 값 형식](../builtin-types/nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="d78eb-119">Any [nullable value type](../builtin-types/nullable-value-types.md)</span></span>|<span data-ttu-id="d78eb-120"><xref:System.Nullable%601.HasValue%2A> 속성은 `false`이고 <xref:System.Nullable%601.Value%2A> 속성은 정의되지 않은 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="d78eb-121">이 기본값은 null 허용 값 형식의 *null* 값으로도 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="d78eb-122">[기본 연산자](../operators/default.md)를 사용하여 다음 예제와 같이 형식의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="d78eb-123">C# 7.1부터 [`default` 리터럴](../operators/default.md#default-literal)을 사용하여 해당 형식의 기본값으로 변수를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="d78eb-124">값 형식의 경우 암시적 매개 변수 없는 생성자를 사용하여 다음 예제와 같은 형식의 기본값도 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d78eb-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="d78eb-125">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d78eb-125">C# language specification</span></span>

<span data-ttu-id="d78eb-126">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d78eb-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="d78eb-127">기본값</span><span class="sxs-lookup"><span data-stu-id="d78eb-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="d78eb-128">기본 생성자</span><span class="sxs-lookup"><span data-stu-id="d78eb-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="d78eb-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d78eb-129">See also</span></span>

- [<span data-ttu-id="d78eb-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d78eb-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d78eb-131">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d78eb-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="d78eb-132">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="d78eb-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="d78eb-133">생성자</span><span class="sxs-lookup"><span data-stu-id="d78eb-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
