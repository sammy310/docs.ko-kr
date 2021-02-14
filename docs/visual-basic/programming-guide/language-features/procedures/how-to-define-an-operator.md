---
description: '자세한 정보: 방법: 연산자 정의 (Visual Basic)'
title: '방법: 연산자 정의'
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
ms.openlocfilehash: ead96a302426c6f5b1667bb030aab56afe3284c8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462713"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="59431-103">방법: 연산자 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59431-103">How to: Define an Operator (Visual Basic)</span></span>

<span data-ttu-id="59431-104">클래스 또는 구조체를 정의한 경우 `*` `<>` `And` 피연산자 중 하나 또는 둘 모두가 클래스 또는 구조체의 형식인 경우 표준 연산자 (예:, 또는)의 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59431-104">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="59431-105">클래스 또는 구조체 내에서 연산자 프로시저로 표준 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59431-105">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="59431-106">모든 연산자 프로시저는 여야 합니다 `Public` `Shared` .</span><span class="sxs-lookup"><span data-stu-id="59431-106">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="59431-107">클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="59431-107">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59431-108">예</span><span class="sxs-lookup"><span data-stu-id="59431-108">Example</span></span>  

 <span data-ttu-id="59431-109">다음 예에서는 `+` 라는 구조체의 연산자를 정의 합니다 `height` .</span><span class="sxs-lookup"><span data-stu-id="59431-109">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="59431-110">구조체는 피트와 인치로 측정 된 높이를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59431-110">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="59431-111">1 *인치* 는 2.54 센티미터이 고 1 *피트* 는 12 인치입니다.</span><span class="sxs-lookup"><span data-stu-id="59431-111">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="59431-112">정규화 된 값 (인치 < 12.0)을 보장 하기 위해 생성자는 *모듈로* 12 산술 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="59431-112">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="59431-113">연산자는 생성자를 사용 하 여 `+` 정규화 된 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="59431-113">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="59431-114">다음 코드를 사용 하 여 구조체를 테스트할 수 있습니다 `height` .</span><span class="sxs-lookup"><span data-stu-id="59431-114">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="59431-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="59431-115">See also</span></span>

- [<span data-ttu-id="59431-116">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="59431-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="59431-117">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="59431-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="59431-118">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="59431-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="59431-119">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="59431-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="59431-120">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="59431-120">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="59431-121">Structure 문</span><span class="sxs-lookup"><span data-stu-id="59431-121">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="59431-122">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="59431-122">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="59431-123">Mod 연산자</span><span class="sxs-lookup"><span data-stu-id="59431-123">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)
