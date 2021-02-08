---
description: '다음에 대 한 자세한 정보: &amp; = 연산자 (Visual Basic)'
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
ms.openlocfilehash: ffc4de352ee29f4c7d18a257dd3699b37c668db7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774319"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="81dba-103">&amp;= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81dba-103">&amp;= Operator (Visual Basic)</span></span>

<span data-ttu-id="81dba-104">`String`변수 또는 속성에 식을 연결 하 `String` 고 결과를 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-104">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81dba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="81dba-105">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="81dba-106">부분</span><span class="sxs-lookup"><span data-stu-id="81dba-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="81dba-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-107">Required.</span></span> <span data-ttu-id="81dba-108">`String`변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-108">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="81dba-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="81dba-109">Required.</span></span> <span data-ttu-id="81dba-110">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-110">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81dba-111">설명</span><span class="sxs-lookup"><span data-stu-id="81dba-111">Remarks</span></span>  

 <span data-ttu-id="81dba-112">연산자의 좌 변에 있는 요소는 `&=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-112">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="81dba-113">변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="81dba-114">`&=`연산자는 `String` 오른쪽의 식을 `String` 왼쪽에 있는 변수나 속성에 연결 하 고 결과를 왼쪽에 있는 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-114">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="81dba-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="81dba-115">Overloading</span></span>  

 <span data-ttu-id="81dba-116">[& 연산자](concatenation-operator.md) 를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-116">The [& Operator](concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="81dba-117">연산자를 오버 로드 하면 `&` 연산자의 동작에 영향을 줍니다 `&=` .</span><span class="sxs-lookup"><span data-stu-id="81dba-117">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="81dba-118">`&=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `&` 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-118">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="81dba-119">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81dba-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81dba-120">예제</span><span class="sxs-lookup"><span data-stu-id="81dba-120">Example</span></span>  

 <span data-ttu-id="81dba-121">다음 예에서는 연산자를 사용 하 여 `&=` 두 변수를 연결 하 `String` 고 결과를 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dba-121">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="81dba-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81dba-122">See also</span></span>

- [<span data-ttu-id="81dba-123">& 연산자</span><span class="sxs-lookup"><span data-stu-id="81dba-123">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="81dba-124">+ = 연산자</span><span class="sxs-lookup"><span data-stu-id="81dba-124">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="81dba-125">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="81dba-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="81dba-126">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="81dba-126">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="81dba-127">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="81dba-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="81dba-128">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="81dba-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="81dba-129">문</span><span class="sxs-lookup"><span data-stu-id="81dba-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
