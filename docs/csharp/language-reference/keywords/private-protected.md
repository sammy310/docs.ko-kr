---
title: private protected - C# 참조
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: a73d61712075cf24d2b94c505104df1fade629e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713211"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="d821b-102">private protected (C# Reference)</span><span class="sxs-lookup"><span data-stu-id="d821b-102">private protected (C# Reference)</span></span>

<span data-ttu-id="d821b-103">`private protected` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="d821b-104">private protected 멤버는 포함하는 클래스에서 파생된 형식으로 액세스할 수 있지만 포함하는 어셈블리 내에서만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="d821b-105">`private protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d821b-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d821b-106">`private protected` 액세스 한정자는 C# 7.2 버전에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="d821b-107">예제</span><span class="sxs-lookup"><span data-stu-id="d821b-107">Example</span></span>

<span data-ttu-id="d821b-108">기본 클래스의 private protected 멤버는 변수의 정적 형식이 파생 클래스 형식인 경우에만 포함 어셈블리의 파생된 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="d821b-109">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="d821b-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;  

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="d821b-110">이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="d821b-111">첫 번째 파일은 공용 기본 클래스인 `BaseClass`를 포함하고 여기에서 파생된 형식인 `DerivedClass1`을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="d821b-112">`BaseClass`는 `myValue`이 두 가지 방법으로 액세스를 시도하는 private protected 멤버인 `DerivedClass1`를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="d821b-113">`myValue`의 인스턴스를 통한 `BaseClass` 액세스의 첫 번째 시도는 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="d821b-114">그러나 `DerivedClass1`에서 상속된 멤버로 사용하려는 시도는 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="d821b-115">두 번째 파일에서 `myValue`의 상속된 멤버로 `DerivedClass2`에 액세스하는 시도는 Assembly1에서 파생된 형식으로만 액세스할 수 있으므로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="d821b-116">구조체를 상속할 수 없기 때문에 구조체 멤버는 `private protected`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d821b-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="d821b-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d821b-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="d821b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d821b-118">See also</span></span>

- [<span data-ttu-id="d821b-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d821b-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d821b-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d821b-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d821b-121">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d821b-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d821b-122">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="d821b-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="d821b-123">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="d821b-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="d821b-124">한정자</span><span class="sxs-lookup"><span data-stu-id="d821b-124">Modifiers</span></span>](index.md)
- [<span data-ttu-id="d821b-125">public</span><span class="sxs-lookup"><span data-stu-id="d821b-125">public</span></span>](public.md)
- [<span data-ttu-id="d821b-126">private</span><span class="sxs-lookup"><span data-stu-id="d821b-126">private</span></span>](private.md)
- [<span data-ttu-id="d821b-127">internal</span><span class="sxs-lookup"><span data-stu-id="d821b-127">internal</span></span>](internal.md)
- <span data-ttu-id="d821b-128">[internal virtual 키워드에 대한 보안 문제](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d821b-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
