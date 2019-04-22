---
title: '방법: 두 개체가 동일한 (Visual Basic) 인지 여부를 테스트합니다'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: dbb268175d197e7b931af45a98f3a273c593e5a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819128"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="00956-102">방법: 두 개체가 동일한 (Visual Basic) 인지 여부를 테스트합니다</span><span class="sxs-lookup"><span data-stu-id="00956-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="00956-103">두 변수 개체를 참조 하는 경우 사용할 수 있습니다 합니다 `Is` 또는 `IsNot` 연산자 또는 둘 다에서 동일한 인스턴스를 참조 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="00956-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="00956-104">두 개체가 같은지 여부를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="00956-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="00956-105">사용 된 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 또는 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 피연산자로 두 변수를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="00956-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="00956-106">두 개체가 같은 인스턴스를 참조 하는 여부에 따라 특정 작업을 수행 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="00956-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="00956-107">앞의 예제에서는 컨트롤 비교 `c` 폼에 있는 활성 컨트롤에 대해 `f`합니다.</span><span class="sxs-lookup"><span data-stu-id="00956-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="00956-108">활성 컨트롤이 없는 경우 없는 경우 하나 하지 않은 동일한 컨트롤 인스턴스로 `c`, 그런 다음 `If` 추가적인 처리 없이 문은 실패 하 고 프로시저에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="00956-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="00956-109">사용할지 `Is` 또는 `IsNot` 할 개인 편의 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00956-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="00956-110">하나는 지정된 된 식에서 다른 보다 읽기 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00956-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00956-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="00956-111">See also</span></span>

- [<span data-ttu-id="00956-112">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00956-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
