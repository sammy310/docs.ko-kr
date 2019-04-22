---
title: '방법: 변환 연산자 (Visual Basic)를 정의 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: cf7bfdd09c7f3429f9c730a7aec34b24af3f2e9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829228"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="3a873-102">방법: 변환 연산자 (Visual Basic)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a873-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="3a873-103">클래스 또는 구조체를 정의한 경우 해당 클래스 또는 구조체 형식 및 다른 데이터 형식 간의 형식 변환 연산자를 정의할 수 있습니다 (같은 `Integer`, `Double`, 또는 `String`).</span><span class="sxs-lookup"><span data-stu-id="3a873-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="3a873-104">형식 변환으로 정의 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) 클래스 또는 구조체 내에서 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="3a873-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="3a873-105">모든 변환 프로시저 여야 `Public Shared`를 각각 지정 해야 합니다 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) 또는 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a873-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="3a873-106">클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a873-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a873-107">예제</span><span class="sxs-lookup"><span data-stu-id="3a873-107">Example</span></span>  
 <span data-ttu-id="3a873-108">다음 예제에서는 라는 구조 간의 변환 연산자를 정의 `digit` 및 `Byte`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a873-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="3a873-109">구조를 테스트할 수 있습니다 `digit` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a873-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="3a873-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a873-110">See also</span></span>

- [<span data-ttu-id="3a873-111">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="3a873-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="3a873-112">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="3a873-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="3a873-113">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="3a873-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="3a873-114">방법: 연산자를 정의 하는 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a873-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="3a873-115">Operator 문</span><span class="sxs-lookup"><span data-stu-id="3a873-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3a873-116">Structure 문</span><span class="sxs-lookup"><span data-stu-id="3a873-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="3a873-117">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="3a873-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="3a873-118">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="3a873-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="3a873-119">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="3a873-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
