---
description: protected internal - C# 참조
title: protected internal - C# 참조
ms.date: 11/15/2017
f1_keywords:
- protectedinternal_CSharpKeyword
author: sputier
ms.openlocfilehash: a7537fba93c0d7145f04c6236d15c11b70f8bf98
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139439"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="700c7-103">protected internal(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="700c7-103">protected internal (C# Reference)</span></span>

<span data-ttu-id="700c7-104">`protected internal` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-104">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="700c7-105">protected internal 멤버는 포함하는 클래스에서 파생된 형식이나 현재 어셈블리에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-105">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="700c7-106">`protected internal` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="700c7-106">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="700c7-107">예제</span><span class="sxs-lookup"><span data-stu-id="700c7-107">Example</span></span>

<span data-ttu-id="700c7-108">기본 클래스의 protected internal 멤버는 포함하는 어셈블리 내의 모든 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-108">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="700c7-109">또한 액세스가 파생된 클래스 형식의 변수를 통해 발생하는 경우에만 다른 어셈블리에 있는 파생 클래스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-109">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="700c7-110">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="700c7-110">For example, consider the following code segment:</span></span>

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

<span data-ttu-id="700c7-111">이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="700c7-112">첫 번째 파일은 공용 기본 클래스인 `BaseClass`와 다른 클래스인 `TestAccess`을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-112">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="700c7-113">`BaseClass`는 `TestAccess` 형식으로 액세스되는 protected internal 멤버인 `myValue`를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-113">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="700c7-114">두 번째 파일에서 `BaseClass`의 인스턴스를 통한 `myValue` 액세스의 시도는 오류를 생성하지만 파생된 클래스 `DerivedClass`의 인스턴스를 통한 이 멤버로의 액세스는 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-114">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="700c7-115">구조체를 상속할 수 없기 때문에 구조체 멤버는 `protected internal`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="700c7-115">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="700c7-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="700c7-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="700c7-117">참조</span><span class="sxs-lookup"><span data-stu-id="700c7-117">See also</span></span>

- [<span data-ttu-id="700c7-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="700c7-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="700c7-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="700c7-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="700c7-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="700c7-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="700c7-121">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="700c7-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="700c7-122">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="700c7-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="700c7-123">한정자</span><span class="sxs-lookup"><span data-stu-id="700c7-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="700c7-124">public</span><span class="sxs-lookup"><span data-stu-id="700c7-124">public</span></span>](public.md)
- [<span data-ttu-id="700c7-125">private</span><span class="sxs-lookup"><span data-stu-id="700c7-125">private</span></span>](private.md)
- [<span data-ttu-id="700c7-126">internal</span><span class="sxs-lookup"><span data-stu-id="700c7-126">internal</span></span>](internal.md)
- <span data-ttu-id="700c7-127">[internal virtual 키워드에 대한 보안 문제](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="700c7-127">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
