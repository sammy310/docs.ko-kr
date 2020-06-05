---
title: '&amp;= 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: db42f7be7225b866eacf5b73066754e91cd1a0f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371988"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="f0ff6-102">&amp;= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ff6-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="f0ff6-103">`String`변수 또는 속성에 식을 연결 하 `String` 고 결과를 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ff6-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0ff6-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f0ff6-105">부분</span><span class="sxs-lookup"><span data-stu-id="f0ff6-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="f0ff6-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-106">Required.</span></span> <span data-ttu-id="f0ff6-107">`String`변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="f0ff6-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-108">Required.</span></span> <span data-ttu-id="f0ff6-109">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0ff6-110">설명</span><span class="sxs-lookup"><span data-stu-id="f0ff6-110">Remarks</span></span>  
 <span data-ttu-id="f0ff6-111">연산자의 좌 변에 있는 요소는 `&=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="f0ff6-112">변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="f0ff6-113">`&=`연산자는 `String` 오른쪽의 식을 `String` 왼쪽에 있는 변수나 속성에 연결 하 고 결과를 왼쪽에 있는 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f0ff6-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="f0ff6-114">Overloading</span></span>  
 <span data-ttu-id="f0ff6-115">[& 연산자](concatenation-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-115">The [& Operator](concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f0ff6-116">연산자를 오버 로드 하면 `&` 연산자의 동작에 영향을 줍니다 `&=` .</span><span class="sxs-lookup"><span data-stu-id="f0ff6-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="f0ff6-117">`&=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `&` 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f0ff6-118">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-118">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ff6-119">예제</span><span class="sxs-lookup"><span data-stu-id="f0ff6-119">Example</span></span>  
 <span data-ttu-id="f0ff6-120">다음 예에서는 연산자를 사용 하 여 `&=` 두 변수를 연결 하 `String` 고 결과를 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff6-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f0ff6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0ff6-121">See also</span></span>

- [<span data-ttu-id="f0ff6-122">& 연산자</span><span class="sxs-lookup"><span data-stu-id="f0ff6-122">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="f0ff6-123">+ = 연산자</span><span class="sxs-lookup"><span data-stu-id="f0ff6-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="f0ff6-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="f0ff6-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="f0ff6-125">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="f0ff6-125">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="f0ff6-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f0ff6-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="f0ff6-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="f0ff6-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="f0ff6-128">문</span><span class="sxs-lookup"><span data-stu-id="f0ff6-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
