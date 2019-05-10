---
title: Inherits 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: c39272d53fea136c83a5a09444b65a594fe3b7a7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625519"
---
# <a name="inherits-statement"></a><span data-ttu-id="65240-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="65240-102">Inherits Statement</span></span>
<span data-ttu-id="65240-103">현재 클래스 또는 인터페이스가 다른 클래스나 인터페이스 집합에서 특성, 변수, 속성, 프로시저 및 이벤트를 상속 하도록 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65240-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65240-104">구문</span><span class="sxs-lookup"><span data-stu-id="65240-104">Syntax</span></span>  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="65240-105">요소</span><span class="sxs-lookup"><span data-stu-id="65240-105">Parts</span></span>  
  
|<span data-ttu-id="65240-106">용어</span><span class="sxs-lookup"><span data-stu-id="65240-106">Term</span></span>|<span data-ttu-id="65240-107">정의</span><span class="sxs-lookup"><span data-stu-id="65240-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="65240-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="65240-108">Required.</span></span> <span data-ttu-id="65240-109">이 클래스가 파생 되는 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65240-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="65240-110">또는</span><span class="sxs-lookup"><span data-stu-id="65240-110">-or-</span></span><br /><br /> <span data-ttu-id="65240-111">이 인터페이스 파생 되는 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65240-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="65240-112">여러 이름을 구분 하려면 쉼표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65240-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65240-113">설명</span><span class="sxs-lookup"><span data-stu-id="65240-113">Remarks</span></span>  
 <span data-ttu-id="65240-114">를 사용 하는 경우는 `Inherits` 문은 클래스 또는 인터페이스 정의에서 공백 및 주석이 아닌 첫 번째 줄을 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65240-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="65240-115">다음에 나와야 합니다 `Class` 또는 `Interface` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="65240-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="65240-116">사용할 수 있습니다 `Inherits` 클래스 또는 인터페이스에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="65240-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="65240-117">즉, 원본 파일, 네임 스페이스, 구조체, 모듈, 프로시저 또는 블록 상속에 대 한 선언 컨텍스트 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65240-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="65240-118">규칙</span><span class="sxs-lookup"><span data-stu-id="65240-118">Rules</span></span>  
  
- <span data-ttu-id="65240-119">**클래스를 상속 합니다.**</span><span class="sxs-lookup"><span data-stu-id="65240-119">**Class Inheritance.**</span></span> <span data-ttu-id="65240-120">클래스를 사용 하는 경우는 `Inherits` 문을 하나의 기본 클래스만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65240-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="65240-121">클래스는 그 안에 중첩 된 클래스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65240-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="65240-122">**인터페이스 상속 합니다.**</span><span class="sxs-lookup"><span data-stu-id="65240-122">**Interface Inheritance.**</span></span> <span data-ttu-id="65240-123">인터페이스를 사용 하는 경우는 `Inherits` 문에서 하나 이상의 기본 인터페이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65240-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="65240-124">동일한 이름 가진 멤버를 정의 하는 경우에 두 개의 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65240-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="65240-125">이렇게 하면 구현 코드를 구현 하는 멤버를 지정 하려면 이름 한정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65240-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="65240-126">인터페이스는 더 제한적인 액세스 수준 가진 다른 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65240-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="65240-127">예를 들어, 한 `Public` 인터페이스에서 상속할 수 없습니다는 `Friend` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="65240-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="65240-128">인터페이스 내에 중첩 된 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65240-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="65240-129">.NET Framework의 클래스 상속의 예로 <xref:System.ArgumentException> 클래스에서 상속 하는 <xref:System.SystemException> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="65240-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="65240-130">이를 제공 <xref:System.ArgumentException> 미리 정의 된 속성과 시스템 예외와 같은 필요한 절차는 <xref:System.Exception.Message%2A> 속성 및 <xref:System.Exception.ToString%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="65240-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="65240-131">.NET Framework의 상속은 인터페이스의 예로 <xref:System.Collections.ICollection> 인터페이스에서 상속 하는 <xref:System.Collections.IEnumerable> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="65240-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="65240-132">이 인해 <xref:System.Collections.ICollection> 컬렉션을 이동 하는 데 필요한 열거자의 정의 상속 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="65240-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65240-133">예제</span><span class="sxs-lookup"><span data-stu-id="65240-133">Example</span></span>  
 <span data-ttu-id="65240-134">다음 예제에서는 합니다 `Inherits` 라는 클래스를 표시 하는 문을 `thisClass` 라는 기본 클래스의 모든 멤버를 상속할 수 `anotherClass`입니다.</span><span class="sxs-lookup"><span data-stu-id="65240-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="65240-135">예제</span><span class="sxs-lookup"><span data-stu-id="65240-135">Example</span></span>  
 <span data-ttu-id="65240-136">다음 예제에서는 여러 인터페이스의 상속을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65240-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="65240-137">라는 인터페이스 `thisInterface` 이제에서 모든 정의 포함 합니다 <xref:System.IComparable>를 <xref:System.IDisposable>, 및 <xref:System.IFormattable> 상속된 된 멤버 각각에 대 한 제공 두 개체의 형식 고유의 비교를 해제 하는 인터페이스에 할당 된 리소스 개체의 값을 표현 하 고는 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="65240-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="65240-138">구현 하는 클래스 `thisInterface` 모든 기본 인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65240-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65240-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="65240-139">See also</span></span>

- [<span data-ttu-id="65240-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="65240-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="65240-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="65240-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="65240-142">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="65240-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="65240-143">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="65240-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="65240-144">인터페이스</span><span class="sxs-lookup"><span data-stu-id="65240-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
