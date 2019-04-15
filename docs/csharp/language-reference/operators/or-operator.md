---
title: '| 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 38f8e21dbd07868441e0c4fbb6074f9897905222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312880"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="66d48-102">| 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="66d48-102">| operator (C# Reference)</span></span>

<span data-ttu-id="66d48-103">이항 `|` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66d48-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="66d48-104">정수 형식의 경우 `|` 연산자는 해당 피연산자의 비트 OR 연산자를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="66d48-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="66d48-105">`bool` 피연산자의 경우 `|` 연산자는 해당 피연산자의 논리적 OR 연산을 계산합니다. 즉, 피연산자가 둘 다 `false`일 경우에만 결과가 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="66d48-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="66d48-106">주의</span><span class="sxs-lookup"><span data-stu-id="66d48-106">Remarks</span></span>

<span data-ttu-id="66d48-107">이진 `|` 연산자는 [기존 OR 연산자](boolean-logical-operators.md#conditional-logical-or-operator-) `||`와 달리 첫 번째 연산자의 값에 상관없이 두 피연산자를 모두 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="66d48-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||`.</span></span>

<span data-ttu-id="66d48-108">사용자 정의 형식은 `|` 연산자를 오버로드할 수 있습니다([operator](../keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="66d48-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="66d48-109">예제</span><span class="sxs-lookup"><span data-stu-id="66d48-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="66d48-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66d48-110">See also</span></span>

- [<span data-ttu-id="66d48-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="66d48-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="66d48-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="66d48-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="66d48-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="66d48-113">C# operators</span></span>](index.md)