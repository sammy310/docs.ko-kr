---
title: Key(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: e13a773f0b585a5c8803a77c7aaad441d90dfe75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053953"
---
# <a name="key-visual-basic"></a><span data-ttu-id="68ee2-102">Key(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68ee2-102">Key (Visual Basic)</span></span>
<span data-ttu-id="68ee2-103">`Key` 키워드를 사용 하면 익명 형식의 속성에 대 한 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="68ee2-104">키 속성 익명 형식 인스턴스 또는 해시 코드 값입니다. 계산이 간에 같음 테스트에 참여 하는 대로 속성만 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="68ee2-105">키 속성의 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="68ee2-106">키워드를 배치 하 여 키 속성으로 익명 형식의 속성을 지정 `Key` 초기화 목록에 선언 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="68ee2-107">다음 예에서 `Airline` 하 고 `FlightNo` 키 속성은 있지만 `Gate` 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="68ee2-108">직접 상속 하는 새로운 무명 형식 만들어지면 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="68ee2-109">컴파일러는 세 명의 상속 된 멤버를 재정의: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="68ee2-110">생성 된 재정의 코드는 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 키 속성에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="68ee2-111">형식에 키 속성이 없는 경우 <xref:System.Object.GetHashCode%2A> 고 <xref:System.Object.Equals%2A> 은 무시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="68ee2-112">같음</span><span class="sxs-lookup"><span data-stu-id="68ee2-112">Equality</span></span>  
 <span data-ttu-id="68ee2-113">동일한 형식의 인스턴스인 경우 및 해당 키 속성의 값이 같으면 두 익명 형식 인스턴스 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="68ee2-114">다음 예에서 `flight2` 값과 같음 `flight1` 이전 예제에서 인스턴스의 동일한 익명 이기 때문에 형식이 있으며 일치 하는 키 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="68ee2-115">그러나 `flight3` 같지 `flight1` 키 속성에 대해 다른 값이 있어 `FlightNo`합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="68ee2-116">인스턴스 `flight4` 와 동일한 형식이 아닌 `flight1` 키 속성으로 다른 속성을 지정 하므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="68ee2-117">두 인스턴스 키가 아닌 속성만 동일한 이름, 형식, 순서 및 값을 사용 하 여 선언 된 경우 두 인스턴스가 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="68ee2-118">키 속성 없이 인스턴스 자체에 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="68ee2-119">두 개의 익명 형식 인스턴스는 동일한 익명 형식의 인스턴스는 조건에 대 한 자세한 내용은 참조 하세요. [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="68ee2-120">해시 코드 계산</span><span class="sxs-lookup"><span data-stu-id="68ee2-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="68ee2-121">와 같은 <xref:System.Object.Equals%2A>, 해시 함수에 정의 된 <xref:System.Object.GetHashCode%2A> 무명 형식을 형식의 키 속성을 기반에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="68ee2-122">다음 예제에서는 키 속성 및 해시 간의 상호 작용 코드 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="68ee2-123">모든 키 속성에 대해 동일한 값이 있는 무명 형식의 인스턴스 키가 아닌 속성 값을 일치 하는 있지 않은 경우에 동일한 해시 코드 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="68ee2-124">다음 문은 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="68ee2-125">하나 이상의 키 속성에 대해 다른 값이 있는 무명 형식의 인스턴스는 서로 다른 해시 코드 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="68ee2-126">다음 문은 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="68ee2-127">키 속성으로 다른 속성을 지정 하는 무명 형식의 인스턴스는 동일한 형식의 인스턴스 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="68ee2-128">경우에 모든 속성의 값과 이름이 같은 다른 해시 코드 값 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="68ee2-129">다음 문은 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="68ee2-130">읽기 전용 값</span><span class="sxs-lookup"><span data-stu-id="68ee2-130">Read-Only Values</span></span>  
 <span data-ttu-id="68ee2-131">키 속성의 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="68ee2-132">예를 들어 `flight1` 앞의 예제에는 `Airline` 및 `FlightNo` 필드는 읽기 전용 있지만 `Gate` 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68ee2-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="68ee2-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="68ee2-133">See also</span></span>

- [<span data-ttu-id="68ee2-134">익명 형식 정의</span><span class="sxs-lookup"><span data-stu-id="68ee2-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="68ee2-135">방법: 무명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="68ee2-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="68ee2-136">익명 형식</span><span class="sxs-lookup"><span data-stu-id="68ee2-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
