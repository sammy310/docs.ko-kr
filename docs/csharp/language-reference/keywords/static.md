---
title: static 한정자 - C# 참조
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 771bcfdac4c4bf27c15da4bc374d804405317a78
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102062"
---
# <a name="static-c-reference"></a><span data-ttu-id="a2ad2-102">static(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a2ad2-102">static (C# Reference)</span></span>

<span data-ttu-id="a2ad2-103">이 페이지에서는 `static` 한정자 키워드를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-103">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="a2ad2-104">`static` 키워드는 [`using static`](using-static.md) 지시문의 일부이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-104">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="a2ad2-105">`static` 한정자를 사용하여 특정 개체가 아니라 형식 자체에 속하는 정적 멤버를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-105">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="a2ad2-106">`static` 한정자를 사용하여 `static` 클래스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-106">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="a2ad2-107">클래스, 인터페이스 및 구조체에서 필드, 메서드, 속성, 연산자, 이벤트 및 생성자에 `static` 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-107">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="a2ad2-108">`static` 한정자는 인덱서 또는 종료자와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-108">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="a2ad2-109">자세한 내용은 [static 클래스 및 static 클래스 멤버](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-109">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example---static-class"></a><span data-ttu-id="a2ad2-110">예제 - 정적 클래스</span><span class="sxs-lookup"><span data-stu-id="a2ad2-110">Example - static class</span></span>

<span data-ttu-id="a2ad2-111">다음 클래스는 `static`으로 선언되며 `static` 메서드만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-111">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="a2ad2-112">상수 또는 형식 선언은 암시적으로 `static` 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-112">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="a2ad2-113">`static` 구성원은 인스턴스를 통해 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-113">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="a2ad2-114">대신, 형식 이름을 통해 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-114">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="a2ad2-115">예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-115">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="a2ad2-116">`static` 구성원 `x`를 참조하려면 동일한 범위에서 구성원에 액세스할 수 없는 경우 정규화된 이름인 `MyBaseC.MyStruct.x`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-116">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="a2ad2-117">클래스 인스턴스에는 클래스의 모든 인스턴스 필드에 대한 별도 복사본이 포함되지만 각 `static` 필드의 복사본은 한 개만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-117">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="a2ad2-118">[`this`](this.md)를 사용하여 `static` 메서드 또는 속성 접근자를 참조할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-118">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="a2ad2-119">`static` 키워드가 클래스에 적용된 경우 클래스의 모든 구성원은 `static`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-119">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="a2ad2-120">클래스, 인터페이스 및 `static` 클래스에 `static` 생성자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-120">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="a2ad2-121">프로그램이 시작되어 클래스가 인스턴스화되기 전에 `static` 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-121">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="a2ad2-122">`static` 키워드는 C++보다 사용이 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-122">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="a2ad2-123">C++ 키워드와 비교하려면 [스토리지 클래스(C++)](/cpp/cpp/storage-classes-cpp#static)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-123">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="a2ad2-124">`static` 구성원을 보여 주려면 회사 직원을 나타내는 클래스를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-124">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="a2ad2-125">클래스에 직원 수를 구하는 메서드와 직원 수를 저장하는 필드가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-125">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="a2ad2-126">메서드와 필드는 둘 다 직원 인스턴스에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-126">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="a2ad2-127">대신 직원의 클래스에 전체적으로 속합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-127">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="a2ad2-128">클래스의 `static` 구성원으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-128">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="a2ad2-129">예제 - 정적 필드 및 메서드</span><span class="sxs-lookup"><span data-stu-id="a2ad2-129">Example - static field and method</span></span>

<span data-ttu-id="a2ad2-130">이 예제에서는 새 직원의 이름 및 ID를 읽고, 직원 카운터를 1만큼 늘린 다음 새 직원에 대한 정보와 새 직원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-130">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="a2ad2-131">이 프로그램은 키보드에서 현재 직원 수를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-131">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="a2ad2-132">예제 - 정적 초기화</span><span class="sxs-lookup"><span data-stu-id="a2ad2-132">Example - static initialization</span></span>

<span data-ttu-id="a2ad2-133">이 예제에서는 아직 선언되지 않은 다른 `static` 필드를 사용하여 `static` 필드를 초기화할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-133">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="a2ad2-134">`static` 필드에 값을 명시적으로 할당할 때까지 결과는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2ad2-134">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="a2ad2-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a2ad2-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a2ad2-136">참조</span><span class="sxs-lookup"><span data-stu-id="a2ad2-136">See also</span></span>

- [<span data-ttu-id="a2ad2-137">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a2ad2-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2ad2-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a2ad2-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2ad2-139">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="a2ad2-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a2ad2-140">한정자</span><span class="sxs-lookup"><span data-stu-id="a2ad2-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a2ad2-141">using 정적 지시문</span><span class="sxs-lookup"><span data-stu-id="a2ad2-141">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="a2ad2-142">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="a2ad2-142">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
