---
description: internal - C# 참조
title: internal - C# 참조
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: 14722d66a65eb5f96118acf017dc877e657b2dd9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134577"
---
# <a name="internal-c-reference"></a><span data-ttu-id="d1ff8-103">internal(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d1ff8-103">internal (C# Reference)</span></span>
<span data-ttu-id="d1ff8-104">`internal` 키워드는 형식 및 형식 멤버에 대한 [액세스 한정자](./access-modifiers.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-104">The `internal` keyword is an [access modifier](./access-modifiers.md) for types and type members.</span></span>
  
 > <span data-ttu-id="d1ff8-105">이 페이지에서는 `internal` 액세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-105">This page covers `internal` access.</span></span> <span data-ttu-id="d1ff8-106">`internal` 키워드는 [`protected internal`](./protected-internal.md) 액세스 한정자의 일부이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-106">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="d1ff8-107">내부 형식 또는 멤버는 다음 예제와 같이 동일한 어셈블리의 파일 내에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-107">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```csharp  
public class BaseClass
{  
    // Only accessible within the same assembly.
    internal static int x = 0;
}  
```  

 <span data-ttu-id="d1ff8-108">`internal` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](./accessibility-levels.md) 및 [액세스 한정자](../../programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-108">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](./accessibility-levels.md) and [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="d1ff8-109">어셈블리에 대한 자세한 내용은 [.NET 어셈블리](../../../standard/assembly/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-109">For more information about assemblies, see [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
 <span data-ttu-id="d1ff8-110">내부 액세스는 구성 요소 그룹이 나머지 애플리케이션 코드에 노출되지 않고 비공개 방식으로 상호 작용할 수 있도록 하기 때문에 일반적으로 구성 요소 기반 개발에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-110">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="d1ff8-111">예를 들어 그래픽 사용자 인터페이스를 빌드하기 위한 프레임워크는 내부 액세스로 멤버를 사용하여 상호 작용하는 `Control` 및 `Form` 클래스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-111">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="d1ff8-112">이러한 멤버는 internal이므로 프레임워크를 사용하는 코드에 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-112">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="d1ff8-113">정의 시 사용된 어셈블리 외부에서 내부 액세스로 형식 또는 멤버를 참조하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-113">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1ff8-114">예제</span><span class="sxs-lookup"><span data-stu-id="d1ff8-114">Example</span></span>  
 <span data-ttu-id="d1ff8-115">이 예제에는 `Assembly1.cs` 및 `Assembly1_a.cs`의 두 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-115">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="d1ff8-116">첫 번째 파일에는 내부 기본 클래스인 `BaseClass`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-116">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="d1ff8-117">두 번째 파일에서 `BaseClass`를 인스턴스화하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-117">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="d1ff8-118">예제</span><span class="sxs-lookup"><span data-stu-id="d1ff8-118">Example</span></span>  
 <span data-ttu-id="d1ff8-119">이 예제에서는 예제 1에서 사용한 것과 동일한 파일을 사용하고 `BaseClass`의 액세스 가능성 수준을 `public`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-119">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="d1ff8-120">또한 `intM` 멤버의 액세스 가능성 수준을 `internal`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-120">Also change the accessibility level of the member `intM` to `internal`.</span></span> <span data-ttu-id="d1ff8-121">이 경우 클래스를 인스턴스화할 수 있지만 내부 멤버에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-121">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="d1ff8-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d1ff8-122">C# Language Specification</span></span>  

<span data-ttu-id="d1ff8-123">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [선언된 내게 필요한 옵션](~/_csharplang/spec/basic-concepts.md#declared-accessibility)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-123">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="d1ff8-124">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1ff8-124">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1ff8-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1ff8-125">See also</span></span>

- [<span data-ttu-id="d1ff8-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d1ff8-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d1ff8-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d1ff8-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d1ff8-128">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d1ff8-128">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d1ff8-129">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="d1ff8-129">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="d1ff8-130">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="d1ff8-130">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="d1ff8-131">한정자</span><span class="sxs-lookup"><span data-stu-id="d1ff8-131">Modifiers</span></span>](index.md)
- [<span data-ttu-id="d1ff8-132">public</span><span class="sxs-lookup"><span data-stu-id="d1ff8-132">public</span></span>](./public.md)
- [<span data-ttu-id="d1ff8-133">private</span><span class="sxs-lookup"><span data-stu-id="d1ff8-133">private</span></span>](./private.md)
- [<span data-ttu-id="d1ff8-134">protected</span><span class="sxs-lookup"><span data-stu-id="d1ff8-134">protected</span></span>](./protected.md)
