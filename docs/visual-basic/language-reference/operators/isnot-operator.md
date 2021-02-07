---
description: '자세한 정보: IsNot 연산자 (Visual Basic)'
title: IsNot 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ac3e127676dfa57d14e07838152022de62fc336b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665668"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="22ece-103">IsNot 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22ece-103">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="22ece-104">두 개체 참조 변수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-104">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="22ece-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="22ece-105">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="22ece-106">부분</span><span class="sxs-lookup"><span data-stu-id="22ece-106">Parts</span></span>

- `result`

  <span data-ttu-id="22ece-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-107">Required.</span></span> <span data-ttu-id="22ece-108">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-108">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="22ece-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-109">Required.</span></span> <span data-ttu-id="22ece-110">`Object`변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-110">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="22ece-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-111">Required.</span></span> <span data-ttu-id="22ece-112">`Object`변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-112">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="22ece-113">설명</span><span class="sxs-lookup"><span data-stu-id="22ece-113">Remarks</span></span>

<span data-ttu-id="22ece-114">`IsNot`연산자는 두 개체 참조가 서로 다른 개체를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-114">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="22ece-115">그러나 값 비교를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-115">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="22ece-116">`object1`와 `object2` 가 정확히 동일한 개체 인스턴스를 참조 하면이 고, 그렇지 않으면입니다 `result` `False` `result` `True` .</span><span class="sxs-lookup"><span data-stu-id="22ece-116">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="22ece-117">`IsNot` 연산자와 반대입니다 `Is` .</span><span class="sxs-lookup"><span data-stu-id="22ece-117">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="22ece-118">의 장점은 `IsNot` `Not` 읽기가 어려울 수 있는 및로 인 한 구문을 방지할 수 있다는 것입니다 `Is` .</span><span class="sxs-lookup"><span data-stu-id="22ece-118">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="22ece-119">및 연산자를 사용 `Is` `IsNot` 하 여 초기 바인딩된 개체와 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-119">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="22ece-120">예제</span><span class="sxs-lookup"><span data-stu-id="22ece-120">Example</span></span>

<span data-ttu-id="22ece-121">다음 코드 예제에서는 연산자와 연산자를 모두 사용 하 여 `Is` `IsNot` 동일한 비교를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-121">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="22ece-122">IsNot 연산자에 TypeOf 연산자 사용</span><span class="sxs-lookup"><span data-stu-id="22ece-122">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="22ece-123">Visual Basic 14부터 연산자를 `TypeOf` 연산자와 함께 사용 하 여 `IsNot` 개체가 데이터 형식과 호환 *되지* 않는지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-123">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="22ece-124">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22ece-124">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="22ece-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22ece-125">See also</span></span>

- [<span data-ttu-id="22ece-126">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="22ece-126">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="22ece-127">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="22ece-127">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="22ece-128">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="22ece-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="22ece-129">방법: 두 개체가 동일한지 테스트</span><span class="sxs-lookup"><span data-stu-id="22ece-129">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
