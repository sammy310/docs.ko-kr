---
title: IsFalse 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 9f25c406038486224c2c4708c86ef86889c44c15
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818490"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="e2943-102">IsFalse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2943-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="e2943-103">식이 인지 결정 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="e2943-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="e2943-104">호출할 수 없습니다 `IsFalse` 명시적으로 코드 에서만 Visual Basic 컴파일러는 데 사용할 수에서 코드를 생성할 `AndAlso` 절.</span><span class="sxs-lookup"><span data-stu-id="e2943-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="e2943-105">클래스 또는 구조체 정의 다음에 있는 해당 유형의 변수를 사용 하는 경우는 `AndAlso` 정의 해야 절 `IsFalse` 해당 클래스 또는 구조체에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2943-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="e2943-106">컴파일러에서 고려 하는 `IsFalse` 및 `IsTrue` 연산자는 *일치 하는 쌍*합니다.</span><span class="sxs-lookup"><span data-stu-id="e2943-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="e2943-107">이 그 중 하나를 정의 하는 경우 정의 해야 합니다도 다른 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2943-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2943-108">합니다 `IsFalse` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="e2943-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="e2943-109">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2943-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e2943-110">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2943-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2943-111">예제</span><span class="sxs-lookup"><span data-stu-id="e2943-111">Example</span></span>  
 <span data-ttu-id="e2943-112">다음 코드 예제에 대 한 정의 포함 하는 구조체의 윤곽선을 정의 합니다 `IsFalse` 고 `IsTrue` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e2943-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="e2943-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e2943-113">See also</span></span>

- [<span data-ttu-id="e2943-114">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="e2943-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="e2943-115">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e2943-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="e2943-116">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="e2943-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
