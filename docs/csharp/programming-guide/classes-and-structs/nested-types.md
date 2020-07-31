---
title: 중첩 형식 - C# 프로그래밍 가이드
description: 클래스, 구조체 또는 인터페이스 내에서 정의된 형식을 C#에서 중첩 형식이라고 합니다.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 9e1c6c1e8b22b5447d43915ab02984aa13146301
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864945"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="57b4d-103">중첩 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="57b4d-103">Nested Types (C# Programming Guide)</span></span>

<span data-ttu-id="57b4d-104">[클래스](../../language-reference/keywords/class.md), [구조체](../../language-reference/builtin-types/struct.md) 또는 [인터페이스](../../language-reference/keywords/interface.md) 내에서 선언된 형식을 중첩 형식이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-104">A type defined within a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) is called a nested type.</span></span> <span data-ttu-id="57b4d-105">예</span><span class="sxs-lookup"><span data-stu-id="57b4d-105">For example</span></span>

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

<span data-ttu-id="57b4d-106">외부 형식이 클래스, 인터페이스 또는 구조체 중 무엇인지에 관계없이, 중첩 형식은 기본적으로 [private](../../language-reference/keywords/private.md)으로 설정됩니다. 즉, 포함하는 형식에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-106">Regardless of whether the outer type is a class, interface, or struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="57b4d-107">앞의 예제에서 `Nested` 클래스는 외부 형식에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span>

<span data-ttu-id="57b4d-108">다음과 같이 [액세스 한정자](../../language-reference/keywords/access-modifiers.md)를 지정하여 중첩 형식의 접근성을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="57b4d-109">**클래스**의 중첩 형식은 [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) 또는 [private protected](../../language-reference/keywords/private-protected.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-109">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span>

   <span data-ttu-id="57b4d-110">그러나 [sealed 클래스](../../language-reference/keywords/sealed.md) 내에서 `protected`, `protected internal` 또는 `private protected` 중첩 클래스를 정의하면 컴파일러 경고 [CS0628](../../misc/cs0628.md), “sealed 클래스에 새 protected 멤버가 선언되었습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-110">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="57b4d-111">**구조체**의 중첩 형식은 [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) 또는 [private](../../language-reference/keywords/private.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-111">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>

<span data-ttu-id="57b4d-112">다음 예제에서는 `Nested` 클래스를 public으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-112">The following example makes the `Nested` class public:</span></span>

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

<span data-ttu-id="57b4d-113">중첩 형식(내부 형식)은 이 형식을 포함하고 있는 형식(외부 형식)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-113">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="57b4d-114">포함하는 형식에 액세스하려면 중첩 형식의 생성자에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-114">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="57b4d-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="57b4d-115">For example:</span></span>

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

<span data-ttu-id="57b4d-116">중첩 형식은 이 형식을 포함하는 형식에 액세스할 수 있는 모든 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-116">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="57b4d-117">또한 상속 및 보호된 멤버를 포함하여 외부 형식의 개인 및 보호된 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-117">It can access private and protected members of the containing type, including any inherited protected members.</span></span>

<span data-ttu-id="57b4d-118">위 선언에서 `Nested` 클래스의 전체 이름은 `Container.Nested`입니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-118">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="57b4d-119">이 이름은 다음과 같이 중첩된 클래스의 새 인스턴스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57b4d-119">This is the name used to create a new instance of the nested class, as follows:</span></span>

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a><span data-ttu-id="57b4d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57b4d-120">See also</span></span>

- [<span data-ttu-id="57b4d-121">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="57b4d-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="57b4d-122">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="57b4d-122">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="57b4d-123">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="57b4d-123">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="57b4d-124">생성자</span><span class="sxs-lookup"><span data-stu-id="57b4d-124">Constructors</span></span>](./constructors.md)
