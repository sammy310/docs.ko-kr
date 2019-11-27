---
title: 'How to: Define a Conversion Operator'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344895"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="df6e9-102">방법: 변환 연산자 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df6e9-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="df6e9-103">클래스 또는 구조체를 정의한 경우 클래스 또는 구조체의 형식과 다른 데이터 형식 (예: `Integer`, `Double`또는 `String`) 사이에 형식 변환 연산자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6e9-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="df6e9-104">형식 변환을 클래스 또는 구조체 내에서 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 프로시저로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6e9-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="df6e9-105">모든 변환 프로시저는 `Public Shared`해야 하며 각각은 [확대](../../../../visual-basic/language-reference/modifiers/widening.md) / [축소](../../../../visual-basic/language-reference/modifiers/narrowing.md)를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6e9-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="df6e9-106">클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6e9-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df6e9-107">예제</span><span class="sxs-lookup"><span data-stu-id="df6e9-107">Example</span></span>  
 <span data-ttu-id="df6e9-108">다음 예에서는 `digit` 구조체와 `Byte`간에 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6e9-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="df6e9-109">다음 코드를 사용 하 여 `digit` 구조를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6e9-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="df6e9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df6e9-110">See also</span></span>

- [<span data-ttu-id="df6e9-111">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="df6e9-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="df6e9-112">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="df6e9-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="df6e9-113">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="df6e9-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="df6e9-114">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="df6e9-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="df6e9-115">Operator 문</span><span class="sxs-lookup"><span data-stu-id="df6e9-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="df6e9-116">Structure 문</span><span class="sxs-lookup"><span data-stu-id="df6e9-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="df6e9-117">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="df6e9-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="df6e9-118">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="df6e9-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="df6e9-119">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="df6e9-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
