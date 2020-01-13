---
title: 중첩 형식 - C# 프로그래밍 가이드
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 982eeceb2088dd6e1e57fe796b38e46c0f2d4de8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705498"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="04984-102">중첩 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="04984-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="04984-103">[클래스](../../language-reference/keywords/class.md) 또는 [구조체](../../language-reference/keywords/struct.md) 내에서 선언된 형식을 중첩 형식이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="04984-103">A type defined within a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="04984-104">예:</span><span class="sxs-lookup"><span data-stu-id="04984-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
<span data-ttu-id="04984-105">외부 형식이 클래스 또는 구조체인지와 관계없이 중첩 형식은 기본적으로 [private](../../language-reference/keywords/private.md)로 설정됩니다. 포함하는 형식에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="04984-106">앞의 예제에서 `Nested` 클래스는 외부 형식에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="04984-107">다음과 같이 [액세스 한정자](../../language-reference/keywords/access-modifiers.md)를 지정하여 중첩 형식의 접근성을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="04984-108">**클래스**의 중첩 형식은 [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) 또는 [private protected](../../language-reference/keywords/private-protected.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-108">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="04984-109">그러나 [sealed 클래스](../../language-reference/keywords/sealed.md) 내에서 `protected`, `protected internal` 또는 `private protected` 중첩 클래스를 정의하면 컴파일러 경고 [CS0628](../../misc/cs0628.md), “sealed 클래스에 새 protected 멤버가 선언되었습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="04984-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="04984-110">**구조체**의 중첩 형식은 [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) 또는 [private](../../language-reference/keywords/private.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-110">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="04984-111">다음 예제에서는 `Nested` 클래스를 public으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04984-111">The following example makes the `Nested` class public:</span></span>
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 <span data-ttu-id="04984-112">중첩 형식(내부 형식)은 이 형식을 포함하고 있는 형식(외부 형식)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="04984-113">포함하는 형식에 액세스하려면 중첩 형식의 생성자에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="04984-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="04984-114">예:</span><span class="sxs-lookup"><span data-stu-id="04984-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 <span data-ttu-id="04984-115">중첩 형식은 이 형식을 포함하는 형식에 액세스할 수 있는 모든 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="04984-116">또한 상속 및 보호된 멤버를 포함하여 외부 형식의 개인 및 보호된 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04984-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="04984-117">위 선언에서 `Nested` 클래스의 전체 이름은 `Container.Nested`입니다.</span><span class="sxs-lookup"><span data-stu-id="04984-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="04984-118">이 이름은 다음과 같이 중첩된 클래스의 새 인스턴스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04984-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a><span data-ttu-id="04984-119">참조</span><span class="sxs-lookup"><span data-stu-id="04984-119">See also</span></span>

- [<span data-ttu-id="04984-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="04984-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="04984-121">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="04984-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="04984-122">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="04984-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="04984-123">생성자</span><span class="sxs-lookup"><span data-stu-id="04984-123">Constructors</span></span>](./constructors.md)
