---
title: Is 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917212"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="214be-102">Is 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="214be-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="214be-103">두 개체 참조 변수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="214be-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214be-104">구문</span><span class="sxs-lookup"><span data-stu-id="214be-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="214be-105">요소</span><span class="sxs-lookup"><span data-stu-id="214be-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="214be-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="214be-106">Required.</span></span> <span data-ttu-id="214be-107">모든 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="214be-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="214be-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="214be-108">Required.</span></span> <span data-ttu-id="214be-109">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="214be-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="214be-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="214be-110">Required.</span></span> <span data-ttu-id="214be-111">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="214be-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="214be-112">설명</span><span class="sxs-lookup"><span data-stu-id="214be-112">Remarks</span></span>  
 <span data-ttu-id="214be-113">연산자 `Is` 는 두 개체 참조가 동일한 개체를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="214be-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="214be-114">그러나 값 비교를 수행 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="214be-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="214be-115">`True` `result` 와 `object1` `object2` 가정확히동일한개체인스턴스를참조`False`하면이 고, 그렇지 않으면입니다. `result`</span><span class="sxs-lookup"><span data-stu-id="214be-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="214be-116">`Is``TypeOf` 키워드와 함께 사용 하 `TypeOf`여 ... `Is` 식-개체 변수가 데이터 형식과 호환 되는지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="214be-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="214be-117">`Is` 키워드는 [Select ...에도 사용 됩니다. Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="214be-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="214be-118">예제</span><span class="sxs-lookup"><span data-stu-id="214be-118">Example</span></span>  
 <span data-ttu-id="214be-119">다음 예제에서는 `Is` 연산자를 사용 하 여 개체 참조 쌍을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="214be-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="214be-120">두 개체가 동일한 지 여부를 `Boolean` 나타내는 값에 결과가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="214be-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="214be-121">앞의 예제에서 보여 주는 것 처럼 `Is` 연산자를 사용 하 여 초기 바인딩과 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="214be-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214be-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="214be-122">See also</span></span>

- [<span data-ttu-id="214be-123">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="214be-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="214be-124">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="214be-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="214be-125">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="214be-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="214be-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="214be-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="214be-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="214be-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="214be-128">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="214be-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
