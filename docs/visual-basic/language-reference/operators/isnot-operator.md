---
title: IsNot 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: e07a775eec003a3e488f6909181aed3f742b4b91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833518"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="93f9f-102">IsNot 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93f9f-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="93f9f-103">두 개체 참조 변수를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="93f9f-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="93f9f-105">요소</span><span class="sxs-lookup"><span data-stu-id="93f9f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="93f9f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="93f9f-106">Required.</span></span> <span data-ttu-id="93f9f-107">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="93f9f-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="93f9f-108">Required.</span></span> <span data-ttu-id="93f9f-109">모든 `Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="93f9f-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="93f9f-110">Required.</span></span> <span data-ttu-id="93f9f-111">모든 `Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93f9f-112">설명</span><span class="sxs-lookup"><span data-stu-id="93f9f-112">Remarks</span></span>  
 <span data-ttu-id="93f9f-113">`IsNot` 연산자 두 개체 참조가 다른 개체를 참조 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="93f9f-114">그러나 값 비교를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="93f9f-115">경우 `object1` 하 고 `object2` 모두 정확히 같은 개체 인스턴스를 참조 `result` 됩니다 `False`가지고 있지 않은 경우 `result` 는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="93f9f-116">`IsNot` 반대 되는 `Is` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="93f9f-117">이점은 `IsNot` 구문에 불편 하지 않아도 됩니다 `Not` 및 `Is`를 읽기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="93f9f-118">사용할 수는 `Is` 고 `IsNot` 초기 바인딩 및 런타임에 바인딩된 개체를 테스트 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93f9f-119">합니다 `IsNot` 식에서 반환 된 비교 연산자를 사용할 수 없습니다는 `TypeOf` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="93f9f-120">대신 사용 해야 합니다 `Not` 고 `Is` 연산자.</span><span class="sxs-lookup"><span data-stu-id="93f9f-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93f9f-121">예제</span><span class="sxs-lookup"><span data-stu-id="93f9f-121">Example</span></span>  
 <span data-ttu-id="93f9f-122">다음 코드 예제에서는 둘 다를 `Is` 연산자 및 `IsNot` 연산자 동일한 비교를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="93f9f-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="93f9f-123">See also</span></span>

- [<span data-ttu-id="93f9f-124">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="93f9f-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="93f9f-125">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="93f9f-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="93f9f-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="93f9f-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="93f9f-127">방법: 두 개체가 같은지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
