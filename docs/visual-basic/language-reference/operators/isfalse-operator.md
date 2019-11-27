---
title: IsFalse 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349525"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="dd7af-102">IsFalse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd7af-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="dd7af-103">식이 `False`되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="dd7af-104">`IsFalse`는 코드에서 명시적으로 호출할 수 없지만 Visual Basic 컴파일러는이를 사용 하 여 `AndAlso` 절에서 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="dd7af-105">클래스 또는 구조체를 정의 하 고 `AndAlso` 절에서 해당 형식의 변수를 사용 하는 경우 해당 클래스 또는 구조체에서 `IsFalse`를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="dd7af-106">컴파일러는 `IsFalse` 및 `IsTrue` 연산자를 일치 하는 *쌍*으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="dd7af-107">즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd7af-108">`IsFalse` 연산자는 *오버 로드*될 수 있습니다. 즉, 클래스 또는 구조체의 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="dd7af-109">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="dd7af-110">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd7af-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd7af-111">예제</span><span class="sxs-lookup"><span data-stu-id="dd7af-111">Example</span></span>  
 <span data-ttu-id="dd7af-112">다음 코드 예제에서는 `IsFalse` 및 `IsTrue` 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd7af-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="dd7af-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd7af-113">See also</span></span>

- [<span data-ttu-id="dd7af-114">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="dd7af-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="dd7af-115">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="dd7af-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="dd7af-116">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="dd7af-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
