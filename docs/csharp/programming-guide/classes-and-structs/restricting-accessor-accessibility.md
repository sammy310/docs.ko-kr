---
title: 접근자 액세스 가능성 제한 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: a332fef814f0c81914eb7b8c308de68f719fbaac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714687"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="4db79-102">접근자 액세스 가능성 제한(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4db79-102">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="4db79-103">속성 또는 인덱서의 [get](../../language-reference/keywords/get.md) 및 [set](../../language-reference/keywords/set.md) 부분을 *접근자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-103">The [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="4db79-104">기본적으로 이러한 접근자는 속하는 속성 또는 인덱서와 동일한 표시 유형 또는 액세스 수준을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-104">By default these accessors have the same visibility or access level of the property or indexer to which they belong.</span></span> <span data-ttu-id="4db79-105">자세한 내용은 [접근성 수준](../../language-reference/keywords/accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4db79-105">For more information, see [accessibility levels](../../language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="4db79-106">그러나 이러한 접근자 중 하나에 대한 액세스를 제한하는 것이 유용한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-106">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="4db79-107">이렇게 하려면 일반적으로 `set` 접근자의 접근성을 제한하는 동시에 `get` 접근자를 공개적으로 액세스할 수 있도록 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-107">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="4db79-108">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 <span data-ttu-id="4db79-109">이 예제에서는 `Name` 속성이 `get` 및 `set` 접근자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-109">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="4db79-110">`get` 접근자는 속성 자체의 접근성 수준(이 경우 `public`)을 받는 반면, `set` 접근자는 접근자 자체에 [protected](../../language-reference/keywords/protected.md) 액세스 한정자를 적용하여 명시적으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-110">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="4db79-111">접근자의 액세스 한정자에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4db79-111">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="4db79-112">속성 또는 인덱서의 접근자 한정자 사용에는 다음과 같은 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-112">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
- <span data-ttu-id="4db79-113">인터페이스 또는 명시적 [interface](../../language-reference/keywords/interface.md) 멤버 구현에는 접근자 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-113">You cannot use accessor modifiers on an interface or an explicit [interface](../../language-reference/keywords/interface.md) member implementation.</span></span>  
  
- <span data-ttu-id="4db79-114">속성 또는 인덱서에 `set` 및 `get` 접근자가 모두 포함된 경우에만 접근자 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-114">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="4db79-115">이 경우 두 접근자 중 하나에서만 한정자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-115">In this case, the modifier is permitted on only one of the two accessors.</span></span>  
  
- <span data-ttu-id="4db79-116">속성 또는 인덱서에 [override](../../language-reference/keywords/override.md) 한정자가 있는 경우 접근자 한정자가 재정의된 접근자의 한정자와 일치해야 합니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="4db79-116">If the property or indexer has an [override](../../language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
- <span data-ttu-id="4db79-117">접근자의 접근성 수준은 속성 또는 인덱서 자체의 접근성 수준보다 더 제한적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-117">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="4db79-118">재정의 접근자의 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="4db79-118">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="4db79-119">속성 또는 인덱서를 재정의하는 경우 재정의 코드에서 재정의된 접근자에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-119">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="4db79-120">또한 속성/인덱서 및 접근자의 접근성이 재정의된 속성/인덱서 및 해당 접근자와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-120">Also, the accessibility of both the property/indexer and its accessors must match the corresponding overridden property/indexer and its accessors.</span></span> <span data-ttu-id="4db79-121">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-121">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="4db79-122">인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="4db79-122">Implementing Interfaces</span></span>  
 <span data-ttu-id="4db79-123">접근자를 사용하여 인터페이스를 구현하는 경우 접근자에 액세스 한정자가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-123">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="4db79-124">그러나 `get` 등의 한 접근자를 사용하여 인터페이스를 구현하는 경우 다음 예제와 같이 다른 접근자에 액세스 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-124">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="4db79-125">접근자 접근성 도메인</span><span class="sxs-lookup"><span data-stu-id="4db79-125">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="4db79-126">접근자의 액세스 한정자를 사용하는 경우 접근자의 [접근성 도메인](../../language-reference/keywords/accessibility-domain.md)은 이 한정자에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-126">If you use an access modifier on the accessor, the [accessibility domain](../../language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="4db79-127">접근자의 액세스 한정자를 사용하지 않은 경우 접근자의 접근성 도메인은 속성 또는 인덱서의 접근성 수준에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-127">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4db79-128">예제</span><span class="sxs-lookup"><span data-stu-id="4db79-128">Example</span></span>  
 <span data-ttu-id="4db79-129">다음 예제에는 세 가지 클래스 `BaseClass`, `DerivedClass`, `MainClass`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-129">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="4db79-130">`BaseClass`에는 두 클래스의 `Name` 및 `Id`인 두 가지 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-130">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="4db79-131">예제에서는 `Id`protected`DerivedClass`, `Id`private`BaseClass` 등의 제한적인 액세스 한정자를 사용할 때 [의 ](../../language-reference/keywords/protected.md) 속성을 [의 ](../../language-reference/keywords/private.md) 속성으로 숨길 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-131">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../language-reference/keywords/protected.md) or [private](../../language-reference/keywords/private.md).</span></span> <span data-ttu-id="4db79-132">따라서 이 속성에 값을 할당하면 `BaseClass` 클래스의 속성이 대신 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-132">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="4db79-133">액세스 한정자를 [public](../../language-reference/keywords/public.md)으로 바꾸면 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-133">Replacing the access modifier by [public](../../language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="4db79-134">또한 예제에서는 `private`, `protected` 속성의 `set` 접근자에 있는 `Name`, `DerivedClass` 등의 제한적인 액세스 한정자가 접근자에 대한 액세스를 차단하고 할당을 시도할 때 오류를 생성함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-134">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a><span data-ttu-id="4db79-135">설명</span><span class="sxs-lookup"><span data-stu-id="4db79-135">Comments</span></span>  
 <span data-ttu-id="4db79-136">`new private string Id` 선언을 `new public string Id`로 바꿀 경우 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db79-136">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="4db79-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4db79-137">See also</span></span>

- [<span data-ttu-id="4db79-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4db79-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4db79-139">속성</span><span class="sxs-lookup"><span data-stu-id="4db79-139">Properties</span></span>](./properties.md)
- [<span data-ttu-id="4db79-140">인덱서</span><span class="sxs-lookup"><span data-stu-id="4db79-140">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="4db79-141">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="4db79-141">Access Modifiers</span></span>](./access-modifiers.md)
