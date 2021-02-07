---
description: '자세한 정보: IsFalse 연산자 (Visual Basic)'
title: IsFalse 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 190399dd29ba2d643bd26dfe4f6191211c9a3740
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665707"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="e643c-103">IsFalse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e643c-103">IsFalse Operator (Visual Basic)</span></span>

<span data-ttu-id="e643c-104">식이 인지 여부를 확인 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e643c-104">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="e643c-105">`IsFalse`코드에서 명시적으로 호출할 수는 없지만 Visual Basic 컴파일러는이를 사용 하 여 절에서 코드를 생성할 수 있습니다 `AndAlso` .</span><span class="sxs-lookup"><span data-stu-id="e643c-105">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="e643c-106">클래스 또는 구조체를 정의한 다음 해당 형식의 변수를 절에서 사용 하는 경우 `AndAlso` `IsFalse` 해당 클래스 또는 구조체에 대해를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e643c-106">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="e643c-107">컴파일러는 `IsFalse` 및 연산자를 `IsTrue` 일치 하는 *쌍* 으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="e643c-107">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="e643c-108">즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e643c-108">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e643c-109">`IsFalse`연산자를 *오버 로드할* 수 있습니다. 즉, 해당 피연산자의 형식이 해당 클래스 또는 구조체의 형식인 경우 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e643c-109">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="e643c-110">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e643c-110">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e643c-111">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e643c-111">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e643c-112">예제</span><span class="sxs-lookup"><span data-stu-id="e643c-112">Example</span></span>  

 <span data-ttu-id="e643c-113">다음 코드 예제에서는 및 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다 `IsFalse` `IsTrue` .</span><span class="sxs-lookup"><span data-stu-id="e643c-113">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="e643c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e643c-114">See also</span></span>

- [<span data-ttu-id="e643c-115">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="e643c-115">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="e643c-116">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e643c-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="e643c-117">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="e643c-117">AndAlso Operator</span></span>](andalso-operator.md)
