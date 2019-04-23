---
title: '연산자 선언 중 하나 여야 합니다: +,-, *,-,-, ^, &amp;, Mod, 처럼를 Or, Xor, 그렇지 않은 <<>>, <> =, <, < =, >, > =, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 4283547109ec312cc4fe07a054bbb8db3bff660f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299191"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="1649e-102">연산자 선언 중 하나 여야 합니다: +,-, \*,\,/, ^, &amp;, Mod, 처럼를 Or, Xor, 되지 \< \<, >>...</span><span class="sxs-lookup"><span data-stu-id="1649e-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="1649e-103">오버 로드 된 연산자만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1649e-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="1649e-104">다음 표에서 연산자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1649e-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="1649e-105">형식</span><span class="sxs-lookup"><span data-stu-id="1649e-105">Type</span></span>|<span data-ttu-id="1649e-106">연산자</span><span class="sxs-lookup"><span data-stu-id="1649e-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="1649e-107">단항</span><span class="sxs-lookup"><span data-stu-id="1649e-107">Unary</span></span>|<span data-ttu-id="1649e-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="1649e-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="1649e-109">이항</span><span class="sxs-lookup"><span data-stu-id="1649e-109">Binary</span></span>|<span data-ttu-id="1649e-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="1649e-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="1649e-111">변환(단항)</span><span class="sxs-lookup"><span data-stu-id="1649e-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="1649e-112">`=` 이진 목록의 연산자는 비교 연산자, 대입 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1649e-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="1649e-113">**오류 ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="1649e-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1649e-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1649e-114">To correct this error</span></span>  
  
1. <span data-ttu-id="1649e-115">오버로드할 수 있는 연산자 집합에서 연산자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1649e-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="1649e-116">직접 오버로드할 수 없는 연산자 오버로드 기능이 필요할 경우 적절한 매개 변수를 사용하고 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1649e-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1649e-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="1649e-117">See also</span></span>

- [<span data-ttu-id="1649e-118">Operator 문</span><span class="sxs-lookup"><span data-stu-id="1649e-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="1649e-119">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="1649e-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="1649e-120">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="1649e-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="1649e-121">방법: 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1649e-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="1649e-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="1649e-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
