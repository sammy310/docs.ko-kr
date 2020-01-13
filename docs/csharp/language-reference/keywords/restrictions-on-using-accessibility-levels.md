---
title: 액세스 가능성 수준 사용에 대한 제한 - C# 참조
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 90c76e68ca526106f3a8be6e3db2640edbb2bc80
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715153"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="70b1a-102">액세스 가능성 수준 사용에 대한 제한(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="70b1a-102">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="70b1a-103">선언에서 형식을 지정하는 경우, 형식의 액세스 가능성 수준이 멤버 또는 다른 형식의 액세스 가능성 수준에 따라 달라지는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="70b1a-104">예를 들어 직접 기본 클래스는 적어도 파생 클래스 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="70b1a-105">다음 선언에서는 기본 클래스 `BaseClass`가 `MyClass`보다 액세스 가능성이 낮기 때문에 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="70b1a-106">다음 표에는 선언된 액세스 가능성 수준에 대한 제한이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="70b1a-107">컨텍스트</span><span class="sxs-lookup"><span data-stu-id="70b1a-107">Context</span></span>|<span data-ttu-id="70b1a-108">설명</span><span class="sxs-lookup"><span data-stu-id="70b1a-108">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="70b1a-109">클래스</span><span class="sxs-lookup"><span data-stu-id="70b1a-109">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="70b1a-110">클래스 형식의 직접 기본 클래스는 적어도 클래스 형식 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="70b1a-111">인터페이스</span><span class="sxs-lookup"><span data-stu-id="70b1a-111">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="70b1a-112">인터페이스 형식의 명시적 기본 인터페이스는 적어도 인터페이스 형식 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="70b1a-113">대리자</span><span class="sxs-lookup"><span data-stu-id="70b1a-113">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="70b1a-114">대리자 형식의 반환 형식 및 매개 변수 형식은 적어도 대리자 형식 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="70b1a-115">상수</span><span class="sxs-lookup"><span data-stu-id="70b1a-115">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="70b1a-116">상수의 형식은 적어도 상수 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="70b1a-117">필드</span><span class="sxs-lookup"><span data-stu-id="70b1a-117">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="70b1a-118">필드의 형식은 적어도 필드 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-118">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="70b1a-119">메서드</span><span class="sxs-lookup"><span data-stu-id="70b1a-119">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="70b1a-120">메서드의 반환 형식 및 매개 변수 형식은 적어도 메서드 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="70b1a-121">속성</span><span class="sxs-lookup"><span data-stu-id="70b1a-121">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="70b1a-122">속성의 형식은 적어도 속성 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-122">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="70b1a-123">이벤트</span><span class="sxs-lookup"><span data-stu-id="70b1a-123">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="70b1a-124">이벤트의 형식은 적어도 이벤트 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-124">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="70b1a-125">인덱서</span><span class="sxs-lookup"><span data-stu-id="70b1a-125">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="70b1a-126">인덱서의 형식 및 매개 변수 형식은 적어도 인덱서 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="70b1a-127">연산자</span><span class="sxs-lookup"><span data-stu-id="70b1a-127">Operators</span></span>](../operators/index.md)|<span data-ttu-id="70b1a-128">연산자의 반환 형식 및 매개 변수 형식은 적어도 연산자 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="70b1a-129">생성자</span><span class="sxs-lookup"><span data-stu-id="70b1a-129">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="70b1a-130">생성자의 매개 변수 형식은 적어도 생성자 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="70b1a-131">예제</span><span class="sxs-lookup"><span data-stu-id="70b1a-131">Example</span></span>

<span data-ttu-id="70b1a-132">다음 예제에는 다양한 종류의 잘못된 선언이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="70b1a-133">각 선언 다음의 주석은 예상된 컴파일러 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70b1a-133">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible 
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error: 
    // "The parameter B.MyPrivateMethod is not accessible due to 
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="70b1a-134">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="70b1a-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="70b1a-135">참조</span><span class="sxs-lookup"><span data-stu-id="70b1a-135">See also</span></span>

- [<span data-ttu-id="70b1a-136">C# 참조</span><span class="sxs-lookup"><span data-stu-id="70b1a-136">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="70b1a-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="70b1a-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="70b1a-138">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="70b1a-138">C# Keywords</span></span>](../../language-reference/keywords/index.md)
- [<span data-ttu-id="70b1a-139">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="70b1a-139">Access Modifiers</span></span>](../../language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="70b1a-140">접근성 도메인</span><span class="sxs-lookup"><span data-stu-id="70b1a-140">Accessibility Domain</span></span>](../../language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="70b1a-141">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="70b1a-141">Accessibility Levels</span></span>](../../language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="70b1a-142">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="70b1a-142">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="70b1a-143">public</span><span class="sxs-lookup"><span data-stu-id="70b1a-143">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="70b1a-144">private</span><span class="sxs-lookup"><span data-stu-id="70b1a-144">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="70b1a-145">protected</span><span class="sxs-lookup"><span data-stu-id="70b1a-145">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="70b1a-146">internal</span><span class="sxs-lookup"><span data-stu-id="70b1a-146">internal</span></span>](../../language-reference/keywords/internal.md)
