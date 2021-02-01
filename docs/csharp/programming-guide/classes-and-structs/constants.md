---
title: 상수 - C# 프로그래밍 가이드
description: C#의 상수는 컴파일 시간 리터럴 값이며 프로그램이 컴파일된 후에는 변경되지 않습니다. C# 기본 제공 형식만 상수가 될 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 4783aff8e9424c90e46cb52692a3e645e995d914
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899076"
---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="93785-104">상수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="93785-104">Constants (C# Programming Guide)</span></span>

<span data-ttu-id="93785-105">상수는 컴파일 시간에 알려진 변경할 수 없는 값입니다. 프로그램 수명 동안 변경하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="93785-105">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="93785-106">상수는 [const](../../language-reference/keywords/const.md) 한정자로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="93785-106">Constants are declared with the [const](../../language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="93785-107">C# [기본 제공 형식](../../language-reference/builtin-types/built-in-types.md)(<xref:System.Object?displayProperty=nameWithType> 제외)만 `const`로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-107">Only the C# [built-in types](../../language-reference/builtin-types/built-in-types.md) (excluding <xref:System.Object?displayProperty=nameWithType>) may be declared as `const`.</span></span> <span data-ttu-id="93785-108">클래스, 구조체 및 배열을 비롯한 사용자 정의 형식은 `const`가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-108">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="93785-109">[readonly](../../language-reference/keywords/readonly.md) 한정자를 사용하여 런타임에 한 번 초기화되고(예: 생성자에서) 이후 변경할 수 없는 클래스, 구조체 또는 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="93785-109">Use the [readonly](../../language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="93785-110">C#에서는 `const` 메서드, 속성 또는 이벤트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-110">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="93785-111">열거형 형식을 사용하여 정수 계열 기본 제공 형식(예: `int`, `uint`, `long` 등)에 대한 명명된 상수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-111">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="93785-112">자세한 내용은 [enum](../../language-reference/builtin-types/enum.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93785-112">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="93785-113">상수는 선언될 때 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93785-113">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="93785-114">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="93785-114">For example:</span></span>  
  
 [!code-csharp[Calendar#1](snippets/constants/Calendar.cs#1)]
  
 <span data-ttu-id="93785-115">이 예제에서 `Months` 상수는 항상 12이고 클래스 자체에 의해서도 변경될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-115">In this example, the constant `Months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="93785-116">실제로 컴파일러는 C# 소스 코드에서 상수 식별자를 발견할 경우(예: `Months`) 리터럴 값을 직접 컴파일러에서 생성하는 IL(중간 언어) 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="93785-116">In fact, when the compiler encounters a constant identifier in C# source code (for example, `Months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="93785-117">런타임에 상수와 연결된 변수 주소가 없으므로 `const` 필드는 참조를 통해 전달될 수 없고 식에 l-value로 표시될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-117">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93785-118">DLL과 같이 다른 코드에 정의된 상수 값을 참조할 경우 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="93785-118">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="93785-119">DLL의 새 버전에서 상수의 새 값을 정의할 경우 프로그램은 새 버전에 대해 다시 컴파일될 때까지 이전 리터럴 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="93785-119">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="93785-120">다음과 같이 같은 형식의 여러 상수를 동시에 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-120">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 [!code-csharp[Calendar#2](snippets/constants/Calendar.cs#2)]
  
 <span data-ttu-id="93785-121">상수를 초기화하는 데 사용되는 식은 순환 참조를 만들지 않을 경우 다른 상수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-121">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="93785-122">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="93785-122">For example:</span></span>  
  
 [!code-csharp[Calendar#3](snippets/constants/Calendar.cs#3)]
  
 <span data-ttu-id="93785-123">상수는 [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) 또는 [private protected](../../language-reference/keywords/private-protected.md)로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-123">Constants can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="93785-124">이러한 액세스 한정자는 클래스의 사용자가 상수에 액세스하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="93785-124">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="93785-125">자세한 내용은 [액세스 한정자](./access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93785-125">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="93785-126">형식의 모든 인스턴스에 대한 상수 값이 같으므로 상수가 [static](../../language-reference/keywords/static.md) 필드인 것처럼 상수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="93785-126">Constants are accessed as if they were [static](../../language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="93785-127">상수를 선언하는 데 `static` 키워드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93785-127">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="93785-128">상수를 정의하는 클래스에 포함되지 않은 식은 상수에 액세스할 때 클래스 이름, 마침표 및 상수 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93785-128">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="93785-129">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="93785-129">For example:</span></span>  
  
 [!code-csharp[Calendar#4](snippets/constants/Calendar.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="93785-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="93785-130">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93785-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93785-131">See also</span></span>

- [<span data-ttu-id="93785-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="93785-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="93785-133">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="93785-133">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="93785-134">속성</span><span class="sxs-lookup"><span data-stu-id="93785-134">Properties</span></span>](./properties.md)
- [<span data-ttu-id="93785-135">형식</span><span class="sxs-lookup"><span data-stu-id="93785-135">Types</span></span>](../types/index.md)
- [<span data-ttu-id="93785-136">readonly</span><span class="sxs-lookup"><span data-stu-id="93785-136">readonly</span></span>](../../language-reference/keywords/readonly.md)
- [<span data-ttu-id="93785-137">C# 파트 1의 불변성: 불변성의 종류</span><span class="sxs-lookup"><span data-stu-id="93785-137">Immutability in C# Part One: Kinds of Immutability</span></span>](/archive/blogs/ericlippert/immutability-in-c-part-one-kinds-of-immutability)
