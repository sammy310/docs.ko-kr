---
title: Is 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 52fbb39ab0a36c8b947b78f464fad26be05ce204
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349541"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="3b53b-102">Is 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b53b-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="3b53b-103">두 개체 참조 변수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b53b-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b53b-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="3b53b-105">요소</span><span class="sxs-lookup"><span data-stu-id="3b53b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="3b53b-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-106">Required.</span></span> <span data-ttu-id="3b53b-107">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="3b53b-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-108">Required.</span></span> <span data-ttu-id="3b53b-109">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="3b53b-110">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-110">Required.</span></span> <span data-ttu-id="3b53b-111">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b53b-112">주의</span><span class="sxs-lookup"><span data-stu-id="3b53b-112">Remarks</span></span>  
 <span data-ttu-id="3b53b-113">`Is` 연산자는 두 개체 참조가 동일한 개체를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="3b53b-114">그러나 값 비교를 수행 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="3b53b-115">`object1`와 `object2` 모두 정확히 동일한 개체 인스턴스를 참조 하는 경우 `result` `True`됩니다. 그렇지 않으면 `result` `False`됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="3b53b-116">`Is`는 `TypeOf` 키워드와 함께 사용 하 여 개체 변수가 데이터 형식과 호환 되는지 여부를 테스트 하는 `TypeOf`...`Is` 식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b53b-117">`Is` 키워드는 [Select ... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3b53b-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b53b-118">예제</span><span class="sxs-lookup"><span data-stu-id="3b53b-118">Example</span></span>  
 <span data-ttu-id="3b53b-119">다음 예제에서는 `Is` 연산자를 사용 하 여 개체 참조 쌍을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="3b53b-120">두 개체가 동일한 지 여부를 나타내는 `Boolean` 값에 결과가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="3b53b-121">앞의 예제에서 보여 주는 것 처럼 `Is` 연산자를 사용 하 여 초기 바인딩과 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b53b-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b53b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b53b-122">See also</span></span>

- [<span data-ttu-id="3b53b-123">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="3b53b-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="3b53b-124">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="3b53b-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="3b53b-125">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="3b53b-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="3b53b-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="3b53b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="3b53b-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="3b53b-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="3b53b-128">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="3b53b-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
