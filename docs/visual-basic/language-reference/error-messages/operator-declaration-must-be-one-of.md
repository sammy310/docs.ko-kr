---
title: 연산자 선언은 +,-, *,-,-, ^, &amp; , Like, Mod, And, or, Xor, Not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse 중 하나 여야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 3fb2cf392611e5ca83818e3bf173513be031085d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409337"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="bfe72-102">연산자 선언은 +,-, \*, \, /, ^, &amp; Like, Mod, And, or, Xor, Not, \<\<, >> 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe72-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="bfe72-103">오버 로드할 수 있는 연산자만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe72-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="bfe72-104">다음 표에서는 선언할 수 있는 연산자를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe72-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="bfe72-105">Type</span><span class="sxs-lookup"><span data-stu-id="bfe72-105">Type</span></span>|<span data-ttu-id="bfe72-106">연산자</span><span class="sxs-lookup"><span data-stu-id="bfe72-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="bfe72-107">단항 연산자</span><span class="sxs-lookup"><span data-stu-id="bfe72-107">Unary</span></span>|<span data-ttu-id="bfe72-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="bfe72-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="bfe72-109">이진</span><span class="sxs-lookup"><span data-stu-id="bfe72-109">Binary</span></span>|<span data-ttu-id="bfe72-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="bfe72-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="bfe72-111">변환(단항)</span><span class="sxs-lookup"><span data-stu-id="bfe72-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="bfe72-112">`=`이진 목록의 연산자는 대입 연산자가 아닌 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe72-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="bfe72-113">**오류 ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="bfe72-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bfe72-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bfe72-114">To correct this error</span></span>  
  
1. <span data-ttu-id="bfe72-115">오버로드할 수 있는 연산자 집합에서 연산자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe72-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="bfe72-116">직접 오버로드할 수 없는 연산자 오버로드 기능이 필요할 경우 적절한 매개 변수를 사용하고 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bfe72-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe72-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfe72-117">See also</span></span>

- [<span data-ttu-id="bfe72-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="bfe72-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="bfe72-119">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="bfe72-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="bfe72-120">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="bfe72-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="bfe72-121">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="bfe72-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="bfe72-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="bfe72-122">Function Statement</span></span>](../statements/function-statement.md)
