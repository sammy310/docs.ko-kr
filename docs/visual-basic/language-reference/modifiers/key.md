---
description: '자세한 정보: 키 (Visual Basic)'
title: 키
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 5ec918da661144053824ca2a734cdec11873b0e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640799"
---
# <a name="key-visual-basic"></a><span data-ttu-id="c3b00-103">Key(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3b00-103">Key (Visual Basic)</span></span>

<span data-ttu-id="c3b00-104">키워드를 사용 하 여 `Key` 익명 형식의 속성에 대 한 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-104">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="c3b00-105">키 속성으로 지정 된 속성만 익명 형식 인스턴스 간의 같음 테스트 또는 해시 코드 값 계산과 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-105">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="c3b00-106">키 속성의 값은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-106">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="c3b00-107">초기화 목록에서 키워드 앞에 키워드를 배치 하 여 익명 형식의 속성을 키 속성으로 지정 `Key` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-107">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="c3b00-108">다음 예제에서 `Airline` 및 `FlightNo` 는 키 속성 이지만 `Gate` 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-108">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="c3b00-109">새 무명 형식이 만들어지면에서 직접 상속 됩니다 <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="c3b00-109">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="c3b00-110">컴파일러는 세 개의 상속 된 멤버 <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> 및를 재정의 <xref:System.Object.ToString%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-110">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="c3b00-111">및에 대해 생성 된 재정의 코드 <xref:System.Object.Equals%2A> 는 <xref:System.Object.GetHashCode%2A> 키 속성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-111">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="c3b00-112">형식에 키 속성이 없는 경우 <xref:System.Object.GetHashCode%2A> 및 <xref:System.Object.Equals%2A> 는 재정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-112">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="c3b00-113">같음</span><span class="sxs-lookup"><span data-stu-id="c3b00-113">Equality</span></span>  

 <span data-ttu-id="c3b00-114">두 익명 형식 인스턴스는 동일한 형식의 인스턴스인 경우와 해당 키 속성의 값이 동일한 경우에 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-114">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="c3b00-115">다음 예제에서 `flight2` 는 `flight1` 동일한 익명 형식의 인스턴스이며 해당 키 속성에 대해 일치 하는 값을 가지 므로 이전 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-115">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="c3b00-116">그러나 `flight3` `flight1` 키 속성의 값이 서로 다르기 때문에와 같지 않습니다 `FlightNo` .</span><span class="sxs-lookup"><span data-stu-id="c3b00-116">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="c3b00-117">인스턴스 `flight4` 는 `flight1` 키 속성으로 다른 속성을 지정 하기 때문에와 동일한 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-117">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="c3b00-118">두 인스턴스가 키가 아닌 속성 (이름, 형식, 순서 및 값)만 사용 하 여 선언 된 경우 두 인스턴스는 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-118">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="c3b00-119">키 속성이 없는 인스턴스는 자체와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-119">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="c3b00-120">두 익명 형식 인스턴스가 동일한 익명 형식의 인스턴스인 조건에 대 한 자세한 내용은 [무명 형식](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c3b00-120">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="c3b00-121">해시 코드 계산</span><span class="sxs-lookup"><span data-stu-id="c3b00-121">Hash Code Calculation</span></span>  

 <span data-ttu-id="c3b00-122">와 마찬가지로 <xref:System.Object.Equals%2A> 익명 형식에 대해에 정의 된 해시 함수는 <xref:System.Object.GetHashCode%2A> 형식의 키 속성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-122">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="c3b00-123">다음 예에서는 키 속성과 해시 코드 값 간의 상호 작용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-123">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="c3b00-124">키가 아닌 속성에 일치 하는 값이 없는 경우에도 모든 키 속성에 대해 동일한 값을 가진 무명 형식의 인스턴스는 동일한 해시 코드 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-124">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="c3b00-125">다음 문은 `True`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-125">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="c3b00-126">하나 이상의 키 속성에 대 한 값이 서로 다른 익명 형식의 인스턴스는 해시 코드 값이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-126">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="c3b00-127">다음 문은 `False`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-127">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="c3b00-128">서로 다른 속성을 키 속성으로 지정 하는 익명 형식의 인스턴스는 동일한 형식의 인스턴스가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-128">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="c3b00-129">모든 속성의 이름과 값이 동일한 경우에도 해시 코드 값은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-129">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="c3b00-130">다음 문은 `False`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-130">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="c3b00-131">Read-Only 값</span><span class="sxs-lookup"><span data-stu-id="c3b00-131">Read-Only Values</span></span>  

 <span data-ttu-id="c3b00-132">키 속성의 값은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-132">The values of key properties cannot be changed.</span></span> <span data-ttu-id="c3b00-133">예를 들어 `flight1` 앞의 예제에서 `Airline` 및 필드는 `FlightNo` 읽기 전용 이지만 `Gate` 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3b00-133">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="c3b00-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3b00-134">See also</span></span>

- [<span data-ttu-id="c3b00-135">익명 형식 정의</span><span class="sxs-lookup"><span data-stu-id="c3b00-135">Anonymous Type Definition</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="c3b00-136">방법: 익명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="c3b00-136">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="c3b00-137">익명 형식</span><span class="sxs-lookup"><span data-stu-id="c3b00-137">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
