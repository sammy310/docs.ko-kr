---
title: 포인터 비교 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 5185bd5e1686858452efcc7c89e2c1977e094386
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969208"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="a0642-102">포인터 비교(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a0642-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="a0642-103">다음 연산자를 적용하여 임의 형식의 포인터를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0642-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="a0642-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="a0642-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="a0642-105">비교 연산자는 부호 없는 정수처럼 두 피연산자의 주소를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="a0642-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0642-106">예제</span><span class="sxs-lookup"><span data-stu-id="a0642-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a><span data-ttu-id="a0642-107">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="a0642-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="a0642-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0642-108">See also</span></span>

- [<span data-ttu-id="a0642-109">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a0642-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a0642-110">포인터 식</span><span class="sxs-lookup"><span data-stu-id="a0642-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="a0642-111">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="a0642-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="a0642-112">포인터 조작</span><span class="sxs-lookup"><span data-stu-id="a0642-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="a0642-113">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="a0642-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="a0642-114">유형</span><span class="sxs-lookup"><span data-stu-id="a0642-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="a0642-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="a0642-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="a0642-116">fixed 문</span><span class="sxs-lookup"><span data-stu-id="a0642-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="a0642-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="a0642-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
