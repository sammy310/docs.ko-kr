---
description: '자세한 정보: &amp; 연산자 (Visual Basic)'
title: '&amp; 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: ba7c94805e805c841d05241fef557ca972a19ae9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774098"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="229b9-103">&amp; 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="229b9-103">&amp; Operator (Visual Basic)</span></span>

<span data-ttu-id="229b9-104">두 식의 문자열 연결을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-104">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229b9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="229b9-105">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="229b9-106">부분</span><span class="sxs-lookup"><span data-stu-id="229b9-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="229b9-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-107">Required.</span></span> <span data-ttu-id="229b9-108">Any `String` 또는 `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="229b9-108">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="229b9-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-109">Required.</span></span> <span data-ttu-id="229b9-110">로 확대 되는 데이터 형식을 사용 하는 모든 식 `String` 입니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-110">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="229b9-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-111">Required.</span></span> <span data-ttu-id="229b9-112">로 확대 되는 데이터 형식을 사용 하는 모든 식 `String` 입니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-112">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="229b9-113">설명</span><span class="sxs-lookup"><span data-stu-id="229b9-113">Remarks</span></span>  

 <span data-ttu-id="229b9-114">또는의 데이터 형식이 `expression1` `expression2` 이 아닌로 확대 된 경우로 `String` `String` 변환 됩니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="229b9-114">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="229b9-115">데이터 형식 중 하나가로 확장 되지 않는 경우 `String` 컴파일러에서 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-115">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="229b9-116">의 데이터 형식이 `result` 인 경우 `String`</span><span class="sxs-lookup"><span data-stu-id="229b9-116">The data type of `result` is `String`.</span></span> <span data-ttu-id="229b9-117">하나 또는 두 식이 모두 [Nothing](../nothing.md) 으로 평가 되거나 값이 인 경우 <xref:System.DBNull.Value?displayProperty=nameWithType> 값이 "" 인 문자열로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-117">If one or both expressions evaluate to [Nothing](../nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="229b9-118">`&`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-118">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="229b9-119">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="229b9-120">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="229b9-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="229b9-121">앰퍼샌드 (&) 문자를 사용 하 여 변수를 형식으로 식별할 수도 있습니다 `Long` .</span><span class="sxs-lookup"><span data-stu-id="229b9-121">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="229b9-122">자세한 내용은 [형식 문자](../../programming-guide/language-features/data-types/type-characters.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="229b9-122">For more information, see [Type Characters](../../programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="229b9-123">예제</span><span class="sxs-lookup"><span data-stu-id="229b9-123">Example</span></span>  

 <span data-ttu-id="229b9-124">이 예에서는 연산자를 사용 `&` 하 여 문자열을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-124">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="229b9-125">결과는 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="229b9-125">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="229b9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="229b9-126">See also</span></span>

- [<span data-ttu-id="229b9-127">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="229b9-127">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="229b9-128">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="229b9-128">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="229b9-129">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="229b9-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="229b9-130">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="229b9-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="229b9-131">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="229b9-131">Concatenation Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
