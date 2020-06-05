---
title: '방법: 두 개체가 동일한지 테스트'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: b215225dbc2d8c0d2bdfe2206e5d4a4f1faa6d0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403423"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="678ef-102">방법: 두 개체가 동일한지 테스트(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="678ef-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="678ef-103">개체를 참조 하는 두 개의 변수가 있는 경우 `Is` or `IsNot` 연산자 또는 둘 다를 사용 하 여 동일한 인스턴스를 참조 하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="678ef-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="678ef-104">두 개체가 동일한 지 여부를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="678ef-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="678ef-105">두 변수를 피연산자로 사용 하는 [Is 연산자](../../../language-reference/operators/is-operator.md) 또는 [IsNot 연산자](../../../language-reference/operators/isnot-operator.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="678ef-105">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="678ef-106">두 개체가 같은 인스턴스를 참조 하는지 여부에 따라 특정 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="678ef-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="678ef-107">앞의 예제에서는 `c` 폼의 활성 컨트롤과 컨트롤을 비교 합니다 `f` .</span><span class="sxs-lookup"><span data-stu-id="678ef-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="678ef-108">활성 컨트롤이 없거나, 해당 컨트롤이 있지만와 동일한 컨트롤 인스턴스가 아닌 경우 `c` `If` 문이 실패 하 고 추가 처리 없이 프로시저가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="678ef-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="678ef-109">`Is`사용자가 또는를 사용 하는지에 `IsNot` 관계 없이 사용자가 개인적으로 편리 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="678ef-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="678ef-110">지정 된 식에서 다른 항목 보다 읽기가 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="678ef-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678ef-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="678ef-111">See also</span></span>

- [<span data-ttu-id="678ef-112">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="678ef-112">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
