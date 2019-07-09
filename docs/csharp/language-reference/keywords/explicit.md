---
title: explicit 키워드 - C# 참조
ms.custom: seodec18
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: a260c6f1ccac6e09770f1cb8f43d5d872b4b2650
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610096"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="0a870-102">explicit(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0a870-102">explicit (C# Reference)</span></span>

<span data-ttu-id="0a870-103">`explicit` 키워드는 캐스트를 통해 호출해야 하는 사용자 정의 형식 변환 연산자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span>

<span data-ttu-id="0a870-104">다음 예제에서는 `Fahrenheit` 클래스에서 `Celsius` 클래스로 변환하는 연산자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-104">The following example defines the operator that converts from a `Fahrenheit` class to a `Celsius` class.</span></span> <span data-ttu-id="0a870-105">연산자는 `Fahrenheit` 클래스 또는 `Celsius` 클래스 내에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-105">The operator must be defined either inside a `Fahrenheit` class or a `Celsius` class:</span></span>

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

<span data-ttu-id="0a870-106">다음 예제와 같이 캐스트를 사용하여 정의된 변환 연산자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-106">You invoke the defined conversion operator with a cast, as the following example shows:</span></span>

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

<span data-ttu-id="0a870-107">변환 연산자는 소스 형식을 대상 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-107">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="0a870-108">소스 형식은 변환 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-108">The source type provides the conversion operator.</span></span> <span data-ttu-id="0a870-109">암시적 변환과 달리 명시적 변환 연산자는 캐스트를 통해 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-109">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="0a870-110">변환 연산으로 인해 예외가 발생하거나 정보가 손실될 경우 `explicit`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-110">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="0a870-111">이렇게 하면 컴파일러가 결과를 예측할 수 없는 변환 연산을 자동으로 호출하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-111">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>

<span data-ttu-id="0a870-112">캐스트를 생략하면 컴파일 시간 오류 CS0266이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-112">Omitting the cast results in compile-time error CS0266.</span></span>

<span data-ttu-id="0a870-113">자세한 내용은 [변환 연산자 사용](../../programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a870-113">For more information, see [Using Conversion Operators](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="example"></a><span data-ttu-id="0a870-114">예</span><span class="sxs-lookup"><span data-stu-id="0a870-114">Example</span></span>

<span data-ttu-id="0a870-115">다음 예제에서는 `Fahrenheit` 및 `Celsius` 클래스를 제공하며, 각 클래스는 다른 클래스에 명시적 변환 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-115">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a><span data-ttu-id="0a870-116">예</span><span class="sxs-lookup"><span data-stu-id="0a870-116">Example</span></span>

<span data-ttu-id="0a870-117">다음 예제에서는 한 자리 숫자를 나타내는 `Digit` 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-117">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="0a870-118">`byte`에서 `Digit`로 변환하는 연산자를 정의하지만 일부 바이트는 `Digit`로 변환할 수 없기 때문에 명시적 변환이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a870-118">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="0a870-119">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0a870-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0a870-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a870-120">See also</span></span>

- [<span data-ttu-id="0a870-121">C# 참조</span><span class="sxs-lookup"><span data-stu-id="0a870-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0a870-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0a870-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0a870-123">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="0a870-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0a870-124">implicit</span><span class="sxs-lookup"><span data-stu-id="0a870-124">implicit</span></span>](implicit.md)
- [<span data-ttu-id="0a870-125">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="0a870-125">Operator overloading</span></span>](../operators/operator-overloading.md)
- [<span data-ttu-id="0a870-126">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="0a870-126">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
- <span data-ttu-id="0a870-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)(C#의 연결된 사용자 정의 명시적 변환)</span><span class="sxs-lookup"><span data-stu-id="0a870-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
