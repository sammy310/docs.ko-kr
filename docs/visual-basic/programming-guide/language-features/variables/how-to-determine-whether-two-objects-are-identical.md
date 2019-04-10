---
title: '방법: 두 개체가 동일한 (Visual Basic) 여부를 확인합니다'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: aae053ae0473ed6ced0f28da3d5e5afc0be629df
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295041"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="d957e-102">방법: 두 개체가 동일한 (Visual Basic) 여부를 확인합니다</span><span class="sxs-lookup"><span data-stu-id="d957e-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="d957e-103">Visual basic의 경우 두 변수가 메모리에서 동일한 클래스 인스턴스를 가리키는 두 개의 변수 참조의 포인터가 동일한 경우, 즉, 동일한 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="d957e-104">예를 들어, Windows Forms 응용 프로그램에서는 하려는 비교를 확인 하는지 여부를 현재 인스턴스 (`Me`) 동일 특정 인스턴스를 같은 `Form2`합니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="d957e-105">Visual Basic에서는 포인터를 비교할 두 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="d957e-106">[Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 반환 `True` 개체가 동일 하면 하며 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 반환 `True` 하지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="d957e-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="d957e-107">두 개체가 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="d957e-108">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="d957e-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="d957e-109">설정 된 `Boolean` 두 개체를 테스트할 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="d957e-110">테스트 식에서 사용 된 `Is` 피연산자로 두 개체를 사용 하 여 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     `Is` <span data-ttu-id="d957e-111">반환 `True` 개체 동일한 클래스 인스턴스를 가리키는 경우.</span><span class="sxs-lookup"><span data-stu-id="d957e-111">returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="d957e-112">두 개체가 동일 하지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="d957e-113">두 개체가 같지 및 결합 하기에 비효율적인 수 하는 경우 작업을 수행 하려는 경우에 따라 `Not` 하 고 `Is`예를 들어 `If Not obj1 Is obj2`합니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="d957e-114">이런 경우에서 사용할 수는 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="d957e-115">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="d957e-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="d957e-116">설정 된 `Boolean` 두 개체를 테스트할 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="d957e-117">테스트 식에서 사용 된 `IsNot` 피연산자로 두 개체를 사용 하 여 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     `IsNot` <span data-ttu-id="d957e-118">반환 `True` 경우 개체는 동일한 클래스 인스턴스를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-118">returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d957e-119">예제</span><span class="sxs-lookup"><span data-stu-id="d957e-119">Example</span></span>  
 <span data-ttu-id="d957e-120">다음 예에서는 쌍을 테스트 `Object` 변수를 같은 클래스 인스턴스를 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="d957e-121">앞의 예제에는 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d957e-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="d957e-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="d957e-122">See also</span></span>

- [<span data-ttu-id="d957e-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="d957e-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d957e-124">개체 변수</span><span class="sxs-lookup"><span data-stu-id="d957e-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="d957e-125">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="d957e-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="d957e-126">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="d957e-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="d957e-127">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="d957e-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="d957e-128">방법: 두 개체가 관련이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d957e-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="d957e-129">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="d957e-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
