---
title: '[] 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835592"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="dce88-102">[] 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dce88-102">[] operator (C# Reference)</span></span>

<span data-ttu-id="dce88-103">대괄호 `[]`는 일반적으로 배열, 인덱서 또는 포인터 요소 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-103">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

<span data-ttu-id="dce88-104">포인터 요소 액세스에 대한 자세한 내용은 [방법: 포인터를 사용하여 배열 요소 액세스](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dce88-104">For more information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="dce88-105">또한 대괄호를 사용하여 [특성](../../programming-guide/concepts/attributes/index.md)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-105">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a><span data-ttu-id="dce88-106">배열 액세스</span><span class="sxs-lookup"><span data-stu-id="dce88-106">Array access</span></span>

<span data-ttu-id="dce88-107">다음 예제는 배열 요소에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-107">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

<span data-ttu-id="dce88-108">배열 인덱스가 배열의 해당 차원 범위를 벗어난 경우 <xref:System.IndexOutOfRangeException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-108">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="dce88-109">앞의 예제와 같이, 배열 형식의 선언 및 배열 인스턴스의 인스턴스화에도 대괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-109">As the preceding example shows, you also use square brackets in declaration of an array type and instantiation of array instances.</span></span>

<span data-ttu-id="dce88-110">배열에 대한 자세한 내용은 [배열](../../programming-guide/arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dce88-110">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="indexer-access"></a><span data-ttu-id="dce88-111">인덱서 액세스</span><span class="sxs-lookup"><span data-stu-id="dce88-111">Indexer access</span></span>

<span data-ttu-id="dce88-112">다음 예제는 .NET <xref:System.Collections.Generic.Dictionary%602> 형식을 사용하여 인덱서 액세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-112">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

<span data-ttu-id="dce88-113">인덱서를 사용하면 배열 인덱싱과 비슷한 방법으로 사용자 정의 형식의 인스턴스를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-113">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="dce88-114">정수여야 하는 배열 인덱스와 달리, 인덱서 인수는 임의 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-114">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="dce88-115">인덱서에 대한 자세한 내용은 [인덱서](../../programming-guide/indexers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dce88-115">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="dce88-116">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="dce88-116">Operator overloadability</span></span>

<span data-ttu-id="dce88-117">요소 액세스 `[]`는 오버로드 가능한 연산자로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-117">Element access `[]` is not considered an overloadable operator.</span></span> <span data-ttu-id="dce88-118">[인덱서](../../programming-guide/indexers/index.md)를 사용하여 사용자 정의 형식의 인덱싱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dce88-118">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dce88-119">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="dce88-119">C# language specification</span></span>

<span data-ttu-id="dce88-120">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [요소 액세스](~/_csharplang/spec/expressions.md#element-access) 및 [포인터 요소 액세스](~/_csharplang/spec/unsafe-code.md#pointer-element-access) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dce88-120">For more information, see the [Element access](~/_csharplang/spec/expressions.md#element-access) and [Pointer element access](~/_csharplang/spec/unsafe-code.md#pointer-element-access) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dce88-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dce88-121">See also</span></span>

- [<span data-ttu-id="dce88-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dce88-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dce88-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dce88-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dce88-124">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="dce88-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="dce88-125">배열</span><span class="sxs-lookup"><span data-stu-id="dce88-125">Arrays</span></span>](../../programming-guide/arrays/index.md)
- [<span data-ttu-id="dce88-126">인덱서</span><span class="sxs-lookup"><span data-stu-id="dce88-126">Indexers</span></span>](../../programming-guide/indexers/index.md)
- [<span data-ttu-id="dce88-127">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="dce88-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="dce88-128">특성</span><span class="sxs-lookup"><span data-stu-id="dce88-128">Attributes</span></span>](../../programming-guide/concepts/attributes/index.md)
- <span data-ttu-id="dce88-129">[?. 및 ?[] 연산자](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="dce88-129">[?. and ?[] operators](null-conditional-operators.md)</span></span>