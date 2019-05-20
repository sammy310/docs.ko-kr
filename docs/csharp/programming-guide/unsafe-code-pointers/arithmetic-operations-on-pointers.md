---
title: 포인터에 대한 산술 연산 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: b08f9dbf8137e483bd38a4f396732191598532cf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635231"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="501d4-102">포인터에 대한 산술 연산(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="501d4-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="501d4-103">이 항목에서는 산술 연산자 `+` 및 `-`를 사용하여 포인터를 조작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="501d4-104">void 포인터에 대해 산술 연산을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="501d4-105">포인터에 숫자 값 더하기 및 포인터에서 숫자 값 빼기</span><span class="sxs-lookup"><span data-stu-id="501d4-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="501d4-106">[int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식의 `n` 값을 포인터에 더할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="501d4-107">`p`가 `pointer-type*` 형식의 포인터인 경우 결과 `p+n`은 `p`의 주소에 `n * sizeof(pointer-type)`를 더하여 생성된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="501d4-108">마찬가지로 `p-n`은 `p` 주소에서 `n * sizeof(pointer-type)`를 뺀 결과로 생성된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="501d4-109">포인터 빼기</span><span class="sxs-lookup"><span data-stu-id="501d4-109">Subtracting pointers</span></span>  
 <span data-ttu-id="501d4-110">같은 형식의 포인터를 뺄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="501d4-111">결과는 항상 `long` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-111">The result is always of the type `long`.</span></span> <span data-ttu-id="501d4-112">예를 들어 `p1` 및 `p2`가 `pointer-type*` 형식의 포인터인 경우 `p1-p2` 식의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="501d4-113">산술 연산이 포인터의 도메인을 오버플로하는 경우 예외가 생성되지 않고 결과는 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="501d4-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="501d4-114">예제</span><span class="sxs-lookup"><span data-stu-id="501d4-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="501d4-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="501d4-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="501d4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="501d4-116">See also</span></span>

- [<span data-ttu-id="501d4-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="501d4-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="501d4-118">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="501d4-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="501d4-119">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="501d4-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="501d4-120">포인터 조작</span><span class="sxs-lookup"><span data-stu-id="501d4-120">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [<span data-ttu-id="501d4-121">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="501d4-121">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="501d4-122">유형</span><span class="sxs-lookup"><span data-stu-id="501d4-122">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="501d4-123">unsafe</span><span class="sxs-lookup"><span data-stu-id="501d4-123">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="501d4-124">fixed 문</span><span class="sxs-lookup"><span data-stu-id="501d4-124">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="501d4-125">stackalloc</span><span class="sxs-lookup"><span data-stu-id="501d4-125">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
