---
title: IsFalse 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 49b8493575685a220808df1522ce16835b3ce0ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917152"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="831eb-102">IsFalse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="831eb-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="831eb-103">식이 인지 여부를 확인 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="831eb-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="831eb-104">코드에서 명시적 `IsFalse` 으로 호출할 수는 없지만 Visual Basic 컴파일러는이를 사용 하 여 절에서 `AndAlso` 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="831eb-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="831eb-105">클래스 또는 구조체를 정의한 다음 해당 형식의 변수를 `AndAlso` 절에서 사용 하는 경우 해당 클래스 또는 구조체에 대해를 정의 `IsFalse` 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="831eb-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="831eb-106">컴파일러는 및 `IsTrue` 연산자 `IsFalse` 를 일치 하는 *쌍*으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="831eb-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="831eb-107">즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="831eb-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="831eb-108">연산자를 오버 로드할 수 있습니다. 즉, 해당 피연산자의 형식이 해당 클래스 또는 구조체의 형식인 경우 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="831eb-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="831eb-109">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="831eb-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="831eb-110">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="831eb-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="831eb-111">예제</span><span class="sxs-lookup"><span data-stu-id="831eb-111">Example</span></span>  
 <span data-ttu-id="831eb-112">다음 코드 예제에서는 `IsFalse` 및 `IsTrue` 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="831eb-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="831eb-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="831eb-113">See also</span></span>

- [<span data-ttu-id="831eb-114">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="831eb-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="831eb-115">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="831eb-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="831eb-116">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="831eb-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
