---
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
ms.openlocfilehash: 4cae7e59083890e82d754bdaa58942c2224357b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336051"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="e25e1-102">&amp; 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e25e1-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="e25e1-103">두 식의 문자열 연결을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e25e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="e25e1-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="e25e1-105">요소</span><span class="sxs-lookup"><span data-stu-id="e25e1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e25e1-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-106">Required.</span></span> <span data-ttu-id="e25e1-107">모든 `String` 또는 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="e25e1-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-108">Required.</span></span> <span data-ttu-id="e25e1-109">`String`로 확대 되는 데이터 형식의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="e25e1-110">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-110">Required.</span></span> <span data-ttu-id="e25e1-111">`String`로 확대 되는 데이터 형식의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e25e1-112">주의</span><span class="sxs-lookup"><span data-stu-id="e25e1-112">Remarks</span></span>  
 <span data-ttu-id="e25e1-113">`expression1` 또는 `expression2`의 데이터 형식이 `String` 되지 않지만 `String`로 확대 되는 경우 `String`로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="e25e1-114">데이터 형식 중 하나가 `String`확장 되지 않는 경우 컴파일러에서 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="e25e1-115">`result` 데이터 형식이 `String`입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="e25e1-116">하나 또는 두 식이 모두 [Nothing](../../../visual-basic/language-reference/nothing.md) 으로 평가 되거나 값이 <xref:System.DBNull.Value?displayProperty=nameWithType>경우 값이 "" 인 문자열로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e25e1-117">`&` 연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e25e1-118">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e25e1-119">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e25e1-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e25e1-120">앰퍼샌드 (&) 문자를 사용 하 여 변수를 `Long`형식으로 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="e25e1-121">자세한 내용은 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e25e1-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25e1-122">예제</span><span class="sxs-lookup"><span data-stu-id="e25e1-122">Example</span></span>  
 <span data-ttu-id="e25e1-123">이 예에서는 `&` 연산자를 사용 하 여 문자열 연결을 강제 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="e25e1-124">결과는 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e25e1-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e25e1-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e25e1-125">See also</span></span>

- [<span data-ttu-id="e25e1-126">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="e25e1-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="e25e1-127">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="e25e1-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="e25e1-128">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="e25e1-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e25e1-129">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="e25e1-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e25e1-130">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="e25e1-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
