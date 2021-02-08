---
description: '다음에 대 한 자세한 정보: Inherits 문'
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: fba574ec207b384c1e7219341526a4a89c8a619c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768924"
---
# <a name="inherits-statement"></a><span data-ttu-id="f5ee5-103">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="f5ee5-103">Inherits Statement</span></span>

<span data-ttu-id="f5ee5-104">현재 클래스 또는 인터페이스가 다른 클래스나 인터페이스 집합에서 특성, 변수, 속성, 프로시저 및 이벤트를 상속 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-104">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ee5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5ee5-105">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="f5ee5-106">부분</span><span class="sxs-lookup"><span data-stu-id="f5ee5-106">Parts</span></span>  
  
|<span data-ttu-id="f5ee5-107">용어</span><span class="sxs-lookup"><span data-stu-id="f5ee5-107">Term</span></span>|<span data-ttu-id="f5ee5-108">정의</span><span class="sxs-lookup"><span data-stu-id="f5ee5-108">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="f5ee5-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-109">Required.</span></span> <span data-ttu-id="f5ee5-110">이 클래스가 파생 되는 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-110">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="f5ee5-111">또는</span><span class="sxs-lookup"><span data-stu-id="f5ee5-111">-or-</span></span><br /><br /> <span data-ttu-id="f5ee5-112">이 인터페이스가 파생 되는 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-112">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="f5ee5-113">여러 이름을 구분 하려면 쉼표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-113">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5ee5-114">설명</span><span class="sxs-lookup"><span data-stu-id="f5ee5-114">Remarks</span></span>  

 <span data-ttu-id="f5ee5-115">사용 되는 경우 `Inherits` 문은 클래스 또는 인터페이스 정의에서 공백이 아닌 첫 번째 줄 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-115">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="f5ee5-116">또는 문 바로 뒤에 `Class` 와 야 합니다 `Interface` .</span><span class="sxs-lookup"><span data-stu-id="f5ee5-116">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="f5ee5-117">`Inherits`는 클래스 또는 인터페이스 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-117">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="f5ee5-118">즉, 상속의 선언 컨텍스트는 소스 파일, 네임 스페이스, 구조체, 모듈, 프로시저 또는 블록이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-118">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f5ee5-119">규칙</span><span class="sxs-lookup"><span data-stu-id="f5ee5-119">Rules</span></span>  
  
- <span data-ttu-id="f5ee5-120">**클래스 상속.**</span><span class="sxs-lookup"><span data-stu-id="f5ee5-120">**Class Inheritance.**</span></span> <span data-ttu-id="f5ee5-121">클래스가 문을 사용 하는 경우 `Inherits` 기본 클래스를 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-121">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="f5ee5-122">클래스는 그 안에 중첩 된 클래스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-122">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="f5ee5-123">**인터페이스 상속.**</span><span class="sxs-lookup"><span data-stu-id="f5ee5-123">**Interface Inheritance.**</span></span> <span data-ttu-id="f5ee5-124">인터페이스에서 문을 사용 하는 경우 `Inherits` 기본 인터페이스를 하나 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-124">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="f5ee5-125">두 인터페이스가 동일한 이름의 멤버를 정의 하는 경우에도 두 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-125">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="f5ee5-126">이렇게 하려면 구현 하는 코드에서 구현 중인 멤버를 지정 하는 데 이름 한정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-126">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="f5ee5-127">인터페이스는 더 제한적인 액세스 수준으로 다른 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-127">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="f5ee5-128">예를 들어 인터페이스는 `Public` 인터페이스에서 상속할 수 없습니다 `Friend` .</span><span class="sxs-lookup"><span data-stu-id="f5ee5-128">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="f5ee5-129">인터페이스는 그 안에 중첩 된 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-129">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="f5ee5-130">.NET Framework의 클래스 상속 예는 클래스 <xref:System.ArgumentException> 에서 상속 되는 클래스입니다 <xref:System.SystemException> .</span><span class="sxs-lookup"><span data-stu-id="f5ee5-130">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="f5ee5-131">이는 <xref:System.ArgumentException> 속성 및 메서드와 같은 시스템 예외에 필요한 모든 미리 정의 된 속성 및 프로시저에 제공 <xref:System.Exception.Message%2A> <xref:System.Exception.ToString%2A> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-131">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="f5ee5-132">.NET Framework의 인터페이스 상속 예제는 인터페이스 <xref:System.Collections.ICollection> 에서 상속 되는 인터페이스입니다 <xref:System.Collections.IEnumerable> .</span><span class="sxs-lookup"><span data-stu-id="f5ee5-132">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="f5ee5-133">그러면에서 <xref:System.Collections.ICollection> 컬렉션을 트래버스하는 데 필요한 열거자의 정의가 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-133">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5ee5-134">예제</span><span class="sxs-lookup"><span data-stu-id="f5ee5-134">Example</span></span>  

 <span data-ttu-id="f5ee5-135">다음 예제에서는 문을 사용 하 여 라는 `Inherits` 클래스가 `thisClass` 라는 기본 클래스의 모든 멤버를 상속 하는 방법을 보여 줍니다 `anotherClass` .</span><span class="sxs-lookup"><span data-stu-id="f5ee5-135">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="f5ee5-136">예제</span><span class="sxs-lookup"><span data-stu-id="f5ee5-136">Example</span></span>  

 <span data-ttu-id="f5ee5-137">다음 예제에서는 여러 인터페이스의 상속을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-137">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="f5ee5-138">이제 이라는 인터페이스에는 `thisInterface` , 및 인터페이스의 모든 정의가 포함 되어 있습니다 <xref:System.IComparable> <xref:System.IDisposable> <xref:System.IFormattable> . 상속 된 멤버는 두 개체의 형식 관련 비교를 위해 각각 제공 하 고 할당 된 리소스를 해제 하 고 개체의 값을로 표현 합니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="f5ee5-138">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="f5ee5-139">을 구현 하는 클래스는 `thisInterface` 모든 기본 인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ee5-139">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ee5-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5ee5-140">See also</span></span>

- [<span data-ttu-id="f5ee5-141">MustInherit</span><span class="sxs-lookup"><span data-stu-id="f5ee5-141">MustInherit</span></span>](../modifiers/mustinherit.md)
- [<span data-ttu-id="f5ee5-142">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="f5ee5-142">NotInheritable</span></span>](../modifiers/notinheritable.md)
- [<span data-ttu-id="f5ee5-143">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="f5ee5-143">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="f5ee5-144">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="f5ee5-144">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="f5ee5-145">인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5ee5-145">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
