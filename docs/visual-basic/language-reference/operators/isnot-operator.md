---
title: IsNot 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966930"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="7d16e-102">IsNot 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d16e-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="7d16e-103">두 개체 참조 변수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d16e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d16e-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="7d16e-105">요소</span><span class="sxs-lookup"><span data-stu-id="7d16e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7d16e-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7d16e-106">Required.</span></span> <span data-ttu-id="7d16e-107">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="7d16e-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7d16e-108">Required.</span></span> <span data-ttu-id="7d16e-109">`Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="7d16e-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7d16e-110">Required.</span></span> <span data-ttu-id="7d16e-111">`Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d16e-112">설명</span><span class="sxs-lookup"><span data-stu-id="7d16e-112">Remarks</span></span>  
 <span data-ttu-id="7d16e-113">연산자 `IsNot` 는 두 개체 참조가 서로 다른 개체를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="7d16e-114">그러나 값 비교를 수행 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="7d16e-115">`False` `result` 와 `object1` `object2` 가정확히동일한개체인스턴스를참조`True`하면이 고, 그렇지 않으면입니다. `result`</span><span class="sxs-lookup"><span data-stu-id="7d16e-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="7d16e-116">`IsNot``Is` 연산자와 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="7d16e-117">의 `IsNot` 장점은 읽기가 어려울 수 있는 및로 인 `Not` 한 `Is`구문을 방지할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="7d16e-118">`Is` 및`IsNot` 연산자를 사용 하 여 초기 바인딩된 개체와 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d16e-119">연산자를 사용 하 여 `TypeOf` 연산자에서 반환 된 식을 비교할 수 없습니다. `IsNot`</span><span class="sxs-lookup"><span data-stu-id="7d16e-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="7d16e-120">대신 `Not` 및`Is` 연산자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d16e-121">예제</span><span class="sxs-lookup"><span data-stu-id="7d16e-121">Example</span></span>  
 <span data-ttu-id="7d16e-122">다음 코드 예제에서는 `Is` 연산자 `IsNot` 와 연산자를 모두 사용 하 여 동일한 비교를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="7d16e-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d16e-123">See also</span></span>

- [<span data-ttu-id="7d16e-124">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="7d16e-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="7d16e-125">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="7d16e-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="7d16e-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="7d16e-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7d16e-127">방법: 두 개체가 같은지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d16e-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
