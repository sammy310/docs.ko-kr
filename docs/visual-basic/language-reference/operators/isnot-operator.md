---
title: IsNot 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336071"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="bb8d8-102">IsNot 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb8d8-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="bb8d8-103">두 개체 참조 변수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb8d8-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb8d8-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="bb8d8-105">요소</span><span class="sxs-lookup"><span data-stu-id="bb8d8-105">Parts</span></span>
 <span data-ttu-id="bb8d8-106">`result` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-106">`result` Required.</span></span> <span data-ttu-id="bb8d8-107">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-107">A `Boolean` value.</span></span>

 <span data-ttu-id="bb8d8-108">`object1` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-108">`object1` Required.</span></span> <span data-ttu-id="bb8d8-109">모든 `Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="bb8d8-110">`object2` 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-110">`object2` Required.</span></span> <span data-ttu-id="bb8d8-111">모든 `Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb8d8-112">주의</span><span class="sxs-lookup"><span data-stu-id="bb8d8-112">Remarks</span></span>
 <span data-ttu-id="bb8d8-113">`IsNot` 연산자는 두 개체 참조가 서로 다른 개체를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="bb8d8-114">그러나 값 비교를 수행 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="bb8d8-115">`object1`와 `object2` 모두 정확히 동일한 개체 인스턴스를 참조 하는 경우 `result` `False`됩니다. 그렇지 않으면 `result` `True`됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="bb8d8-116">`IsNot`은 `Is` 연산자와 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="bb8d8-117">`IsNot`의 장점은 읽기가 어려울 수 있는 `Not` 및 `Is`를 사용 하 여 구문이 좋지 않게 방지할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="bb8d8-118">`Is` 및 `IsNot` 연산자를 사용 하 여 초기 바인딩과 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="bb8d8-119">예제</span><span class="sxs-lookup"><span data-stu-id="bb8d8-119">Example</span></span>
 <span data-ttu-id="bb8d8-120">다음 코드 예제에서는 `Is` 연산자와 `IsNot` 연산자를 모두 사용 하 여 동일한 비교를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb8d8-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="bb8d8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb8d8-121">See also</span></span>

- [<span data-ttu-id="bb8d8-122">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="bb8d8-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="bb8d8-123">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="bb8d8-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="bb8d8-124">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="bb8d8-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="bb8d8-125">방법: 두 개체가 동일한지 테스트</span><span class="sxs-lookup"><span data-stu-id="bb8d8-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
