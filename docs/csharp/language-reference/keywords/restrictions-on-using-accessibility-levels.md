---
description: 액세스 가능성 수준 사용에 대한 제한 - C# 참조
title: 액세스 가능성 수준 사용에 대한 제한 - C# 참조
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 542e463e41c70f2e8aed5c20dc1294e296a88518
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137002"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="455a0-103">액세스 가능성 수준 사용에 대한 제한(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="455a0-103">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="455a0-104">선언에서 형식을 지정하는 경우, 형식의 액세스 가능성 수준이 멤버 또는 다른 형식의 액세스 가능성 수준에 따라 달라지는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-104">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="455a0-105">예를 들어 직접 기본 클래스는 적어도 파생 클래스 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-105">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="455a0-106">다음 선언에서는 기본 클래스 `BaseClass`가 `MyClass`보다 액세스 가능성이 낮기 때문에 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-106">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="455a0-107">다음 표에는 선언된 액세스 가능성 수준에 대한 제한이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-107">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="455a0-108">Context</span><span class="sxs-lookup"><span data-stu-id="455a0-108">Context</span></span>|<span data-ttu-id="455a0-109">설명</span><span class="sxs-lookup"><span data-stu-id="455a0-109">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="455a0-110">클래스</span><span class="sxs-lookup"><span data-stu-id="455a0-110">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="455a0-111">클래스 형식의 직접 기본 클래스는 적어도 클래스 형식 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-111">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="455a0-112">인터페이스</span><span class="sxs-lookup"><span data-stu-id="455a0-112">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="455a0-113">인터페이스 형식의 명시적 기본 인터페이스는 적어도 인터페이스 형식 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-113">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="455a0-114">대리자</span><span class="sxs-lookup"><span data-stu-id="455a0-114">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="455a0-115">대리자 형식의 반환 형식 및 매개 변수 형식은 적어도 대리자 형식 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-115">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="455a0-116">상수</span><span class="sxs-lookup"><span data-stu-id="455a0-116">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="455a0-117">상수의 형식은 적어도 상수 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-117">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="455a0-118">필드</span><span class="sxs-lookup"><span data-stu-id="455a0-118">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="455a0-119">필드의 형식은 적어도 필드 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-119">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="455a0-120">메서드</span><span class="sxs-lookup"><span data-stu-id="455a0-120">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="455a0-121">메서드의 반환 형식 및 매개 변수 형식은 적어도 메서드 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-121">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="455a0-122">속성</span><span class="sxs-lookup"><span data-stu-id="455a0-122">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="455a0-123">속성의 형식은 적어도 속성 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-123">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="455a0-124">이벤트</span><span class="sxs-lookup"><span data-stu-id="455a0-124">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="455a0-125">이벤트의 형식은 적어도 이벤트 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-125">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="455a0-126">인덱서</span><span class="sxs-lookup"><span data-stu-id="455a0-126">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="455a0-127">인덱서의 형식 및 매개 변수 형식은 적어도 인덱서 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-127">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="455a0-128">연산자</span><span class="sxs-lookup"><span data-stu-id="455a0-128">Operators</span></span>](../operators/index.md)|<span data-ttu-id="455a0-129">연산자의 반환 형식 및 매개 변수 형식은 적어도 연산자 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-129">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="455a0-130">생성자</span><span class="sxs-lookup"><span data-stu-id="455a0-130">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="455a0-131">생성자의 매개 변수 형식은 적어도 생성자 자체 수준만큼 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-131">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="455a0-132">예제</span><span class="sxs-lookup"><span data-stu-id="455a0-132">Example</span></span>

<span data-ttu-id="455a0-133">다음 예제에는 다양한 종류의 잘못된 선언이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-133">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="455a0-134">각 선언 다음의 주석은 예상된 컴파일러 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="455a0-134">The comment following each declaration indicates the expected compiler error.</span></span>

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

## <a name="c-language-specification"></a><span data-ttu-id="455a0-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="455a0-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="455a0-136">참조</span><span class="sxs-lookup"><span data-stu-id="455a0-136">See also</span></span>

- [<span data-ttu-id="455a0-137">C# 참조</span><span class="sxs-lookup"><span data-stu-id="455a0-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="455a0-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="455a0-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="455a0-139">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="455a0-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="455a0-140">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="455a0-140">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="455a0-141">내게 필요한 옵션 도메인</span><span class="sxs-lookup"><span data-stu-id="455a0-141">Accessibility Domain</span></span>](accessibility-domain.md)
- [<span data-ttu-id="455a0-142">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="455a0-142">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="455a0-143">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="455a0-143">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="455a0-144">public</span><span class="sxs-lookup"><span data-stu-id="455a0-144">public</span></span>](public.md)
- [<span data-ttu-id="455a0-145">private</span><span class="sxs-lookup"><span data-stu-id="455a0-145">private</span></span>](private.md)
- [<span data-ttu-id="455a0-146">protected</span><span class="sxs-lookup"><span data-stu-id="455a0-146">protected</span></span>](protected.md)
- [<span data-ttu-id="455a0-147">internal</span><span class="sxs-lookup"><span data-stu-id="455a0-147">internal</span></span>](internal.md)
