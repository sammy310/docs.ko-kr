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
ms.openlocfilehash: 3cc0ae5f04358fbe6b2aabc50498f39ca7225164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370806"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="70bf3-102">Is 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70bf3-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="70bf3-103">두 개체 참조 변수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bf3-104">구문</span><span class="sxs-lookup"><span data-stu-id="70bf3-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="70bf3-105">부분</span><span class="sxs-lookup"><span data-stu-id="70bf3-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="70bf3-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70bf3-106">Required.</span></span> <span data-ttu-id="70bf3-107">모든 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="70bf3-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70bf3-108">Required.</span></span> <span data-ttu-id="70bf3-109">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="70bf3-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70bf3-110">Required.</span></span> <span data-ttu-id="70bf3-111">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70bf3-112">설명</span><span class="sxs-lookup"><span data-stu-id="70bf3-112">Remarks</span></span>  
 <span data-ttu-id="70bf3-113">`Is`연산자는 두 개체 참조가 동일한 개체를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="70bf3-114">그러나 값 비교를 수행 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="70bf3-115">`object1`와 `object2` 가 정확히 동일한 개체 인스턴스를 참조 하면이 고, 그렇지 않으면입니다 `result` `True` `result` `False` .</span><span class="sxs-lookup"><span data-stu-id="70bf3-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="70bf3-116">`Is`는 키워드와 함께 사용 `TypeOf` 하 여 `TypeOf` `Is` 개체 변수가 데이터 형식과 호환 되는지 여부를 테스트 하는 ... 식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70bf3-117">`Is`키워드는 Select ...에도 사용 됩니다. [ Case 문](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="70bf3-117">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70bf3-118">예제</span><span class="sxs-lookup"><span data-stu-id="70bf3-118">Example</span></span>  
 <span data-ttu-id="70bf3-119">다음 예제에서는 연산자를 사용 하 여 `Is` 개체 참조 쌍을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="70bf3-120">`Boolean`두 개체가 동일한 지 여부를 나타내는 값에 결과가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="70bf3-121">앞의 예제에서 보여 주는 것 처럼 연산자를 사용 `Is` 하 여 초기 바인딩과 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70bf3-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bf3-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70bf3-122">See also</span></span>

- [<span data-ttu-id="70bf3-123">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="70bf3-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="70bf3-124">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="70bf3-124">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="70bf3-125">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70bf3-125">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="70bf3-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="70bf3-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="70bf3-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="70bf3-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="70bf3-128">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="70bf3-128">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
