---
title: '* 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977346"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0646f-102">\* 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0646f-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="0646f-103">`*` 연산자는 두 개의 형식인 단항 포인터 간접 참조 연산자 또는 이항 곱하기 연산자에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0646f-103">The `*` operator is supported in two forms: a unary pointer indirection operator or a binary multiplication operator.</span></span>

## <a name="pointer-indirection-operator"></a><span data-ttu-id="0646f-104">포인터 간접 참조 연산자</span><span class="sxs-lookup"><span data-stu-id="0646f-104">Pointer indirection operator</span></span>

<span data-ttu-id="0646f-105">단항 `*` 연산자를 사용하여 포인터 형식 피연산자가 가리키는 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0646f-105">Use the unary `*` operator to obtain the variable to which an operand of a pointer type points.</span></span> <span data-ttu-id="0646f-106">자세한 내용은 [방법: 포인터 변수 값 가져오기](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0646f-106">For more information, see [How to: obtain the value of a pointer variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span></span>

<span data-ttu-id="0646f-107">포인터 간접 참조 연산자 `*`에는 [unsafe](../keywords/unsafe.md) 컨텍스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0646f-107">The pointer indirection operator `*` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="multiplication-operator"></a><span data-ttu-id="0646f-108">곱하기 연산자</span><span class="sxs-lookup"><span data-stu-id="0646f-108">Multiplication operator</span></span>

<span data-ttu-id="0646f-109">숫자 형식의 경우 `*` 연산자는 해당 피연산자의 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0646f-109">For numeric types, the `*` operator computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a><span data-ttu-id="0646f-110">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="0646f-110">Operator overloadability</span></span>

<span data-ttu-id="0646f-111">사용자 정의 형식은 이항 `*` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0646f-111">User-defined types can [overload](../keywords/operator.md) a binary `*` operator.</span></span> <span data-ttu-id="0646f-112">이항 `*` 연산자가 오버로드되면 [곱하기 대입 연산자](multiplication-assignment-operator.md) `*=`도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0646f-112">When a binary `*` operator is overloaded, the [multiplication assignment operator](multiplication-assignment-operator.md) `*=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0646f-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0646f-113">C# language specification</span></span>

<span data-ttu-id="0646f-114">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [포인터 간접 참조](~/_csharplang/spec/unsafe-code.md#pointer-indirection) 및 [곱하기 연산자](~/_csharplang/spec/expressions.md#multiplication-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0646f-114">For more information, see the [Pointer indirection](~/_csharplang/spec/unsafe-code.md#pointer-indirection) and [Multiplication operator](~/_csharplang/spec/expressions.md#multiplication-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0646f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0646f-115">See also</span></span>

- [<span data-ttu-id="0646f-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="0646f-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0646f-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0646f-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0646f-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="0646f-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="0646f-119">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="0646f-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)