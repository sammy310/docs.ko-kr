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
ms.openlocfilehash: d778c0c99d6d074fe8b73aaf3660074643e7e136
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371611"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="94e8d-102">&amp; 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94e8d-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="94e8d-103">두 식의 문자열 연결을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e8d-104">구문</span><span class="sxs-lookup"><span data-stu-id="94e8d-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="94e8d-105">부분</span><span class="sxs-lookup"><span data-stu-id="94e8d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="94e8d-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="94e8d-106">Required.</span></span> <span data-ttu-id="94e8d-107">Any `String` 또는 `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="94e8d-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="94e8d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="94e8d-108">Required.</span></span> <span data-ttu-id="94e8d-109">로 확대 되는 데이터 형식을 사용 하는 모든 식 `String` 입니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="94e8d-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="94e8d-110">Required.</span></span> <span data-ttu-id="94e8d-111">로 확대 되는 데이터 형식을 사용 하는 모든 식 `String` 입니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94e8d-112">설명</span><span class="sxs-lookup"><span data-stu-id="94e8d-112">Remarks</span></span>  
 <span data-ttu-id="94e8d-113">또는의 데이터 형식이 `expression1` `expression2` 이 아닌로 확대 된 경우로 `String` `String` 변환 됩니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="94e8d-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="94e8d-114">데이터 형식 중 하나가로 확장 되지 않는 경우 `String` 컴파일러에서 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="94e8d-115">의 데이터 형식이 `result` 인 경우 `String`</span><span class="sxs-lookup"><span data-stu-id="94e8d-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="94e8d-116">하나 또는 두 식이 모두 [Nothing](../nothing.md) 으로 평가 되거나 값이 인 경우 <xref:System.DBNull.Value?displayProperty=nameWithType> 값이 "" 인 문자열로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-116">If one or both expressions evaluate to [Nothing](../nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94e8d-117">`&`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="94e8d-118">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="94e8d-119">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94e8d-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94e8d-120">앰퍼샌드 (&) 문자를 사용 하 여 변수를 형식으로 식별할 수도 있습니다 `Long` .</span><span class="sxs-lookup"><span data-stu-id="94e8d-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="94e8d-121">자세한 내용은 [형식 문자](../../programming-guide/language-features/data-types/type-characters.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="94e8d-121">For more information, see [Type Characters](../../programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e8d-122">예제</span><span class="sxs-lookup"><span data-stu-id="94e8d-122">Example</span></span>  
 <span data-ttu-id="94e8d-123">이 예에서는 연산자를 사용 `&` 하 여 문자열을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="94e8d-124">결과는 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="94e8d-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="94e8d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94e8d-125">See also</span></span>

- [<span data-ttu-id="94e8d-126">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="94e8d-126">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="94e8d-127">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="94e8d-127">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="94e8d-128">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="94e8d-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="94e8d-129">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="94e8d-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="94e8d-130">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="94e8d-130">Concatenation Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
