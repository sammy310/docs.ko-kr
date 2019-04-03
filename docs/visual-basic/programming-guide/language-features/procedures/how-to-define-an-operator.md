---
title: '방법: 연산자 (Visual Basic)를 정의 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 3a09657ee7a79b7f590adba0e4fb0c04a8e89043
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843645"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="31982-102">방법: 연산자 (Visual Basic)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="31982-103">클래스 또는 구조체를 정의한 경우에 표준 연산자의 동작을 정의할 수 있습니다 (같은 `*`, `<>`, 또는 `And`) 클래스 또는 구조체 형식의 하나 또는 두 피연산자 모두가 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="31982-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="31982-104">클래스 또는 구조체에서 연산자 프로시저도 표준 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="31982-105">모든 연산자 프로시저 여야 `Public` `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="31982-106">클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="31982-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31982-107">예제</span><span class="sxs-lookup"><span data-stu-id="31982-107">Example</span></span>  
 <span data-ttu-id="31982-108">다음 예제에서는 정의 된 `+` 구조에 대 한 연산자 호출 `height`합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="31982-109">구조는 feet 및 인치 단위로 측정 된 높이 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="31982-110">하나의 *인치* 2.54 센티미터 이며 하나 *foot* 12 인치입니다.</span><span class="sxs-lookup"><span data-stu-id="31982-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="31982-111">생성자는 정규화 된 값 (인치 < 12.0)을 위해 다음을 수행 합니다. *모듈로* 산술 12입니다.</span><span class="sxs-lookup"><span data-stu-id="31982-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="31982-112">`+` 연산자 생성자를 사용 하 여 정규화 된 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="31982-113">구조를 테스트할 수 있습니다 `height` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  
  
  
## <a name="see-also"></a><span data-ttu-id="31982-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="31982-114">See also</span></span>

- [<span data-ttu-id="31982-115">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="31982-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="31982-116">방법: 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="31982-117">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="31982-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="31982-118">방법: 연산자를 정의 하는 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31982-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="31982-119">Operator 문</span><span class="sxs-lookup"><span data-stu-id="31982-119">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="31982-120">Structure 문</span><span class="sxs-lookup"><span data-stu-id="31982-120">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="31982-121">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="31982-121">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="31982-122">Mod 연산자</span><span class="sxs-lookup"><span data-stu-id="31982-122">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
