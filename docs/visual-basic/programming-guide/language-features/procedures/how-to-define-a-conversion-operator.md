---
description: '자세한 정보: 방법: 변환 연산자 정의 (Visual Basic)'
title: '방법: 변환 연산자 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: c090e183e809974163625c4bfcf33536b1082b66
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481989"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="77b41-103">방법: 변환 연산자 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77b41-103">How to: Define a Conversion Operator (Visual Basic)</span></span>

<span data-ttu-id="77b41-104">클래스 또는 구조체를 정의한 경우 클래스 또는 구조체의 형식과 다른 데이터 형식 (예: `Integer` , 또는) 사이에 형식 변환 연산자를 정의할 수 있습니다 `Double` `String` .</span><span class="sxs-lookup"><span data-stu-id="77b41-104">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="77b41-105">형식 변환을 클래스 또는 구조체 내에서 [CType 함수](../../../language-reference/functions/ctype-function.md) 프로시저로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b41-105">Define the type conversion as a [CType Function](../../../language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="77b41-106">모든 변환 프로시저는 여야 `Public Shared` 하 고 각각은 [확대](../../../language-reference/modifiers/widening.md) / [축소](../../../language-reference/modifiers/narrowing.md)를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b41-106">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../language-reference/modifiers/widening.md) or [Narrowing](../../../language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="77b41-107">클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="77b41-107">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77b41-108">예</span><span class="sxs-lookup"><span data-stu-id="77b41-108">Example</span></span>  

 <span data-ttu-id="77b41-109">다음 예제에서는 및 라는 구조체 간에 변환 연산자를 정의 합니다 `digit` `Byte` .</span><span class="sxs-lookup"><span data-stu-id="77b41-109">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="77b41-110">다음 코드를 사용 하 여 구조체를 테스트할 수 있습니다 `digit` .</span><span class="sxs-lookup"><span data-stu-id="77b41-110">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="77b41-111">추가 정보</span><span class="sxs-lookup"><span data-stu-id="77b41-111">See also</span></span>

- [<span data-ttu-id="77b41-112">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="77b41-112">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="77b41-113">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="77b41-113">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="77b41-114">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="77b41-114">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="77b41-115">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="77b41-115">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="77b41-116">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="77b41-116">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="77b41-117">Structure 문</span><span class="sxs-lookup"><span data-stu-id="77b41-117">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="77b41-118">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="77b41-118">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="77b41-119">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="77b41-119">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="77b41-120">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="77b41-120">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
