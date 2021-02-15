---
description: '자세히 알아보기: 방법: 두 개체가 동일한 지 확인 (Visual Basic)'
title: '방법: 두 개체가 동일한지 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 91f431b5a7e4cf51135c060ca0aebf1b3b968b25
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481898"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="3442c-103">방법: 두 개체가 동일한지 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3442c-103">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>

<span data-ttu-id="3442c-104">Visual Basic 두 변수가 동일한 경우 (즉, 두 변수가 메모리에서 동일한 클래스 인스턴스를 가리키는 경우) 두 변수 참조가 동일한 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-104">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="3442c-105">예를 들어 Windows Forms 응용 프로그램에서는 현재 인스턴스 ( `Me` )가와 같은 특정 인스턴스와 동일한 지 여부를 확인 하기 위해 비교를 수행할 수 있습니다 `Form2` .</span><span class="sxs-lookup"><span data-stu-id="3442c-105">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="3442c-106">Visual Basic는 포인터를 비교 하는 두 개의 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-106">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="3442c-107">[Is 연산자](../../../language-reference/operators/is-operator.md) 는 `True` 개체가 동일 하면를 반환 하 고, [IsNot 연산자](../../../language-reference/operators/isnot-operator.md) 는 그렇지 않으면를 반환 합니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="3442c-107">The [Is Operator](../../../language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="3442c-108">두 개체가 동일한 지 확인</span><span class="sxs-lookup"><span data-stu-id="3442c-108">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="3442c-109">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="3442c-109">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="3442c-110">`Boolean`두 개체를 테스트 하는 식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-110">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="3442c-111">테스트 식에서 `Is` 피연산자로 두 개의 개체를 사용 하 여 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-111">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="3442c-112">`Is``True`개체가 동일한 클래스 인스턴스를 가리키면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-112">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="3442c-113">두 개체가 동일 하지 않은 경우 확인</span><span class="sxs-lookup"><span data-stu-id="3442c-113">Determining if Two Objects Are Not Identical</span></span>  

 <span data-ttu-id="3442c-114">두 개체가 동일 하지 않을 경우 작업을 수행 하려는 경우와 예를 들어 및를 결합 하는 것이 어려울 수 있습니다 `Not` `Is` `If Not obj1 Is obj2` .</span><span class="sxs-lookup"><span data-stu-id="3442c-114">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="3442c-115">이 경우 연산자를 사용할 수 있습니다 `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="3442c-115">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="3442c-116">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="3442c-116">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="3442c-117">`Boolean`두 개체를 테스트 하는 식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-117">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="3442c-118">테스트 식에서 `IsNot` 피연산자로 두 개의 개체를 사용 하 여 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-118">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="3442c-119">`IsNot``True`개체가 동일한 클래스 인스턴스를 가리키지 않으면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-119">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3442c-120">예</span><span class="sxs-lookup"><span data-stu-id="3442c-120">Example</span></span>  

 <span data-ttu-id="3442c-121">다음 예제에서는 변수 쌍을 테스트 `Object` 하 여 동일한 클래스 인스턴스를 가리켜야 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-121">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="3442c-122">위의 예제는 다음과 같은 출력을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3442c-122">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="3442c-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3442c-123">See also</span></span>

- [<span data-ttu-id="3442c-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="3442c-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="3442c-125">개체 변수</span><span class="sxs-lookup"><span data-stu-id="3442c-125">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="3442c-126">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="3442c-126">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="3442c-127">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="3442c-127">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="3442c-128">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="3442c-128">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="3442c-129">방법: 두 개체가 관련이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3442c-129">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="3442c-130">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="3442c-130">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
