---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 6e6e9cc9210232059210862f2bda691c57b372d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353235"
---
# <a name="inherits-statement"></a><span data-ttu-id="9babe-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="9babe-102">Inherits Statement</span></span>
<span data-ttu-id="9babe-103">현재 클래스 또는 인터페이스가 다른 클래스나 인터페이스 집합에서 특성, 변수, 속성, 프로시저 및 이벤트를 상속 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9babe-104">구문</span><span class="sxs-lookup"><span data-stu-id="9babe-104">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="9babe-105">요소</span><span class="sxs-lookup"><span data-stu-id="9babe-105">Parts</span></span>  
  
|<span data-ttu-id="9babe-106">용어</span><span class="sxs-lookup"><span data-stu-id="9babe-106">Term</span></span>|<span data-ttu-id="9babe-107">정의</span><span class="sxs-lookup"><span data-stu-id="9babe-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="9babe-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-108">Required.</span></span> <span data-ttu-id="9babe-109">이 클래스가 파생 되는 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="9babe-110">-또는-</span><span class="sxs-lookup"><span data-stu-id="9babe-110">-or-</span></span><br /><br /> <span data-ttu-id="9babe-111">이 인터페이스가 파생 되는 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="9babe-112">여러 이름을 구분 하려면 쉼표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9babe-113">주의</span><span class="sxs-lookup"><span data-stu-id="9babe-113">Remarks</span></span>  
 <span data-ttu-id="9babe-114">사용 되는 경우 `Inherits` 문은 클래스 또는 인터페이스 정의에서 공백이 아닌 첫 번째 줄 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="9babe-115">`Class` 또는 `Interface` 문 바로 뒤에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="9babe-116">`Inherits`는 클래스 또는 인터페이스 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="9babe-117">즉, 상속의 선언 컨텍스트는 소스 파일, 네임 스페이스, 구조체, 모듈, 프로시저 또는 블록이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9babe-118">규칙</span><span class="sxs-lookup"><span data-stu-id="9babe-118">Rules</span></span>  
  
- <span data-ttu-id="9babe-119">**클래스 상속.**</span><span class="sxs-lookup"><span data-stu-id="9babe-119">**Class Inheritance.**</span></span> <span data-ttu-id="9babe-120">클래스가 `Inherits` 문을 사용 하는 경우 하나의 기본 클래스만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="9babe-121">클래스는 그 안에 중첩 된 클래스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="9babe-122">**인터페이스 상속.**</span><span class="sxs-lookup"><span data-stu-id="9babe-122">**Interface Inheritance.**</span></span> <span data-ttu-id="9babe-123">인터페이스에서 `Inherits` 문을 사용 하는 경우 하나 이상의 기본 인터페이스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="9babe-124">두 인터페이스가 동일한 이름의 멤버를 정의 하는 경우에도 두 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="9babe-125">이렇게 하려면 구현 하는 코드에서 구현 중인 멤버를 지정 하는 데 이름 한정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="9babe-126">인터페이스는 더 제한적인 액세스 수준으로 다른 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="9babe-127">예를 들어 `Public` 인터페이스는 `Friend` 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="9babe-128">인터페이스는 그 안에 중첩 된 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="9babe-129">.NET Framework의 클래스 상속 예제는 <xref:System.SystemException> 클래스에서 상속 되는 <xref:System.ArgumentException> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="9babe-130">이를 통해 <xref:System.Exception.Message%2A> 속성 및 <xref:System.Exception.ToString%2A> 메서드와 같이 시스템 예외에 필요한 미리 정의 된 모든 속성 및 프로시저를 <xref:System.ArgumentException> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="9babe-131">.NET Framework의 인터페이스 상속 예는 <xref:System.Collections.IEnumerable> 인터페이스에서 상속 하는 <xref:System.Collections.ICollection> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="9babe-132">이로 인해 <xref:System.Collections.ICollection>는 컬렉션을 트래버스하는 데 필요한 열거자의 정의를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9babe-133">예제</span><span class="sxs-lookup"><span data-stu-id="9babe-133">Example</span></span>  
 <span data-ttu-id="9babe-134">다음 예제에서는 `Inherits` 문을 사용 하 `thisClass` 클래스 `anotherClass`기본 클래스의 모든 멤버를 상속할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="9babe-135">예제</span><span class="sxs-lookup"><span data-stu-id="9babe-135">Example</span></span>  
 <span data-ttu-id="9babe-136">다음 예제에서는 여러 인터페이스의 상속을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="9babe-137">이제 `thisInterface` 이라는 인터페이스에는 상속 된 멤버가 두 개체의 유형별 비교를 위해 각각 제공 하는 <xref:System.IComparable>, <xref:System.IDisposable>및 <xref:System.IFormattable> 인터페이스의 모든 정의와 할당 된 리소스를 해제 하 고 개체의 값을 `String`로 표현 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="9babe-138">`thisInterface`를 구현 하는 클래스는 모든 기본 인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babe-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9babe-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9babe-139">See also</span></span>

- [<span data-ttu-id="9babe-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="9babe-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="9babe-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="9babe-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="9babe-142">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="9babe-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="9babe-143">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="9babe-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="9babe-144">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9babe-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
