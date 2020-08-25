---
title: IsNot 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811043"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="2967a-102">IsNot 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2967a-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="2967a-103">두 개체 참조 변수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="2967a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2967a-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="2967a-105">부분</span><span class="sxs-lookup"><span data-stu-id="2967a-105">Parts</span></span>

- `result`

  <span data-ttu-id="2967a-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2967a-106">Required.</span></span> <span data-ttu-id="2967a-107">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-107">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="2967a-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2967a-108">Required.</span></span> <span data-ttu-id="2967a-109">`Object`변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-109">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="2967a-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2967a-110">Required.</span></span> <span data-ttu-id="2967a-111">`Object`변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="2967a-112">설명</span><span class="sxs-lookup"><span data-stu-id="2967a-112">Remarks</span></span>

<span data-ttu-id="2967a-113">`IsNot`연산자는 두 개체 참조가 서로 다른 개체를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="2967a-114">그러나 값 비교를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-114">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="2967a-115">`object1`와 `object2` 가 정확히 동일한 개체 인스턴스를 참조 하면이 고, 그렇지 않으면입니다 `result` `False` `result` `True` .</span><span class="sxs-lookup"><span data-stu-id="2967a-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="2967a-116">`IsNot` 연산자와 반대입니다 `Is` .</span><span class="sxs-lookup"><span data-stu-id="2967a-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="2967a-117">의 장점은 `IsNot` `Not` 읽기가 어려울 수 있는 및로 인 한 구문을 방지할 수 있다는 것입니다 `Is` .</span><span class="sxs-lookup"><span data-stu-id="2967a-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="2967a-118">및 연산자를 사용 `Is` `IsNot` 하 여 초기 바인딩된 개체와 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="2967a-119">예제</span><span class="sxs-lookup"><span data-stu-id="2967a-119">Example</span></span>

<span data-ttu-id="2967a-120">다음 코드 예제에서는 연산자와 연산자를 모두 사용 하 여 `Is` `IsNot` 동일한 비교를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="2967a-121">IsNot 연산자에 TypeOf 연산자 사용</span><span class="sxs-lookup"><span data-stu-id="2967a-121">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="2967a-122">Visual Basic 14부터 연산자를 `TypeOf` 연산자와 함께 사용 하 여 `IsNot` 개체가 데이터 형식과 호환 *되지* 않는지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2967a-122">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="2967a-123">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="2967a-123">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="2967a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2967a-124">See also</span></span>

- [<span data-ttu-id="2967a-125">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="2967a-125">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="2967a-126">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="2967a-126">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="2967a-127">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="2967a-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="2967a-128">방법: 두 개체가 동일한지 테스트</span><span class="sxs-lookup"><span data-stu-id="2967a-128">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
