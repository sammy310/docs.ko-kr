---
title: C# 형식의 기본값 - C# 참조
description: bool, char, int, float, double 등과 같은 C# 형식의 기본값에 대해 알아보세요.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 93b6079b9a3bbf6d537094cab9dfb305ace7f6bf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625867"
---
# <a name="default-values-of-c-types-c-reference"></a><span data-ttu-id="9a04b-103">C# 형식의 기본값(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9a04b-103">Default values of C# types (C# reference)</span></span>

<span data-ttu-id="9a04b-104">다음 표는 C# 형식의 기본값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="9a04b-105">형식</span><span class="sxs-lookup"><span data-stu-id="9a04b-105">Type</span></span>|<span data-ttu-id="9a04b-106">기본값</span><span class="sxs-lookup"><span data-stu-id="9a04b-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="9a04b-107">임의 참조 형식</span><span class="sxs-lookup"><span data-stu-id="9a04b-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="9a04b-108">임의 [기본 제공 정수 숫자 유형](integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="9a04b-108">Any [built-in integral numeric type](integral-numeric-types.md)</span></span>|<span data-ttu-id="9a04b-109">0(영)</span><span class="sxs-lookup"><span data-stu-id="9a04b-109">0 (zero)</span></span>|
|<span data-ttu-id="9a04b-110">임의 [기본 제공 부동 소수점 숫자 유형](floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="9a04b-110">Any [built-in floating-point numeric type](floating-point-numeric-types.md)</span></span>|<span data-ttu-id="9a04b-111">0(영)</span><span class="sxs-lookup"><span data-stu-id="9a04b-111">0 (zero)</span></span>|
|[<span data-ttu-id="9a04b-112">bool</span><span class="sxs-lookup"><span data-stu-id="9a04b-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="9a04b-113">char</span><span class="sxs-lookup"><span data-stu-id="9a04b-113">char</span></span>](char.md)|<span data-ttu-id="9a04b-114">`'\0'`(U+0000)</span><span class="sxs-lookup"><span data-stu-id="9a04b-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="9a04b-115">enum</span><span class="sxs-lookup"><span data-stu-id="9a04b-115">enum</span></span>](enum.md)|<span data-ttu-id="9a04b-116">식 `(E)0`로 생성한 값이며 여기서 `E`는 열거형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="9a04b-117">struct</span><span class="sxs-lookup"><span data-stu-id="9a04b-117">struct</span></span>](struct.md)|<span data-ttu-id="9a04b-118">모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="9a04b-119">Any [Null 허용 값 형식](nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="9a04b-119">Any [nullable value type](nullable-value-types.md)</span></span>|<span data-ttu-id="9a04b-120"><xref:System.Nullable%601.HasValue%2A> 속성은 `false`이고 <xref:System.Nullable%601.Value%2A> 속성은 정의되지 않은 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="9a04b-121">이 기본값은 null 허용 값 형식의 *null* 값으로도 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="9a04b-122">[기본 연산자](../operators/default.md)를 사용하여 다음 예제와 같이 형식의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="9a04b-123">C# 7.1부터 [`default` 리터럴](../operators/default.md#default-literal)을 사용하여 해당 형식의 기본값으로 변수를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="9a04b-124">값 형식의 경우 암시적 매개 변수 없는 생성자를 사용하여 다음 예제와 같은 형식의 기본값도 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

<span data-ttu-id="9a04b-125">런타임에 <xref:System.Type?displayProperty=nameWithType> 인스턴스가 값 형식을 나타내는 경우, <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> 메서드를 사용하면 매개 변수가 없는 생성자를 호출하여 형식의 기본값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a04b-125">At run time, if the <xref:System.Type?displayProperty=nameWithType> instance represents a value type, you can use the <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> method to invoke the parameterless constructor to obtain the default value of the type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9a04b-126">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="9a04b-126">C# language specification</span></span>

<span data-ttu-id="9a04b-127">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a04b-127">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="9a04b-128">기본값</span><span class="sxs-lookup"><span data-stu-id="9a04b-128">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="9a04b-129">기본 생성자</span><span class="sxs-lookup"><span data-stu-id="9a04b-129">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="9a04b-130">참조</span><span class="sxs-lookup"><span data-stu-id="9a04b-130">See also</span></span>

- [<span data-ttu-id="9a04b-131">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9a04b-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9a04b-132">생성자</span><span class="sxs-lookup"><span data-stu-id="9a04b-132">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
