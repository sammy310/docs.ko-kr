---
title: 접근자 액세스 가능성 제한 - C# 프로그래밍 가이드
description: C#에서 속성의 get 및 set 접근자는 자신이 속한 속성과 기본적으로 가시성 또는 액세스 수준이 같습니다. 액세스를 제한할 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: 18fd1d58dc6125b5180118b2e0d3edc885a4b971
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863970"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="06d2e-104">접근자 액세스 가능성 제한(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="06d2e-104">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="06d2e-105">속성 또는 인덱서의 [get](../../language-reference/keywords/get.md) 및 [set](../../language-reference/keywords/set.md) 부분을 *접근자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-105">The [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="06d2e-106">기본적으로 이러한 접근자는 속하는 속성 또는 인덱서와 동일한 표시 유형 또는 액세스 수준을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-106">By default these accessors have the same visibility or access level of the property or indexer to which they belong.</span></span> <span data-ttu-id="06d2e-107">자세한 내용은 [접근성 수준](../../language-reference/keywords/accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06d2e-107">For more information, see [accessibility levels](../../language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="06d2e-108">그러나 이러한 접근자 중 하나에 대한 액세스를 제한하는 것이 유용한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-108">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="06d2e-109">이렇게 하려면 일반적으로 `set` 접근자의 접근성을 제한하는 동시에 `get` 접근자를 공개적으로 액세스할 수 있도록 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-109">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="06d2e-110">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="06d2e-110">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 <span data-ttu-id="06d2e-111">이 예제에서는 `Name` 속성이 `get` 및 `set` 접근자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-111">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="06d2e-112">`get` 접근자는 속성 자체의 접근성 수준(이 경우 `public`)을 받는 반면, `set` 접근자는 접근자 자체에 [protected](../../language-reference/keywords/protected.md) 액세스 한정자를 적용하여 명시적으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-112">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="06d2e-113">접근자의 액세스 한정자에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="06d2e-113">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="06d2e-114">속성 또는 인덱서의 접근자 한정자 사용에는 다음과 같은 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-114">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
- <span data-ttu-id="06d2e-115">인터페이스 또는 명시적 [interface](../../language-reference/keywords/interface.md) 멤버 구현에는 접근자 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-115">You cannot use accessor modifiers on an interface or an explicit [interface](../../language-reference/keywords/interface.md) member implementation.</span></span>  
  
- <span data-ttu-id="06d2e-116">속성 또는 인덱서에 `set` 및 `get` 접근자가 모두 포함된 경우에만 접근자 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-116">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="06d2e-117">이 경우 두 접근자 중 하나에서만 한정자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-117">In this case, the modifier is permitted on only one of the two accessors.</span></span>  
  
- <span data-ttu-id="06d2e-118">속성 또는 인덱서에 [override](../../language-reference/keywords/override.md) 한정자가 있는 경우 접근자 한정자가 재정의된 접근자의 한정자와 일치해야 합니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="06d2e-118">If the property or indexer has an [override](../../language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
- <span data-ttu-id="06d2e-119">접근자의 접근성 수준은 속성 또는 인덱서 자체의 접근성 수준보다 더 제한적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-119">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="06d2e-120">재정의 접근자의 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="06d2e-120">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="06d2e-121">속성 또는 인덱서를 재정의하는 경우 재정의 코드에서 재정의된 접근자에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-121">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="06d2e-122">또한 속성/인덱서 및 접근자의 접근성이 재정의된 속성/인덱서 및 해당 접근자와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-122">Also, the accessibility of both the property/indexer and its accessors must match the corresponding overridden property/indexer and its accessors.</span></span> <span data-ttu-id="06d2e-123">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="06d2e-123">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="06d2e-124">인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="06d2e-124">Implementing Interfaces</span></span>  
 <span data-ttu-id="06d2e-125">접근자를 사용하여 인터페이스를 구현하는 경우 접근자에 액세스 한정자가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-125">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="06d2e-126">그러나 `get` 등의 한 접근자를 사용하여 인터페이스를 구현하는 경우 다음 예제와 같이 다른 접근자에 액세스 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-126">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="06d2e-127">접근자 접근성 도메인</span><span class="sxs-lookup"><span data-stu-id="06d2e-127">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="06d2e-128">접근자의 액세스 한정자를 사용하는 경우 접근자의 [접근성 도메인](../../language-reference/keywords/accessibility-domain.md)은 이 한정자에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-128">If you use an access modifier on the accessor, the [accessibility domain](../../language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="06d2e-129">접근자의 액세스 한정자를 사용하지 않은 경우 접근자의 접근성 도메인은 속성 또는 인덱서의 접근성 수준에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-129">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06d2e-130">예제</span><span class="sxs-lookup"><span data-stu-id="06d2e-130">Example</span></span>  
 <span data-ttu-id="06d2e-131">다음 예제에는 세 가지 클래스 `BaseClass`, `DerivedClass`, `MainClass`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-131">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="06d2e-132">`BaseClass`에는 두 클래스의 `Name` 및 `Id`인 두 가지 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-132">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="06d2e-133">예제에서는 [protected](../../language-reference/keywords/protected.md), [private](../../language-reference/keywords/private.md) 등의 제한적인 액세스 한정자를 사용할 때 `DerivedClass`의 `Id` 속성을 `BaseClass`의 `Id` 속성으로 숨길 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-133">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../language-reference/keywords/protected.md) or [private](../../language-reference/keywords/private.md).</span></span> <span data-ttu-id="06d2e-134">따라서 이 속성에 값을 할당하면 `BaseClass` 클래스의 속성이 대신 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-134">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="06d2e-135">액세스 한정자를 [public](../../language-reference/keywords/public.md)으로 바꾸면 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-135">Replacing the access modifier by [public](../../language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="06d2e-136">또한 예제에서는 `DerivedClass`, `Name` 속성의 `set` 접근자에 있는 `private`, `protected` 등의 제한적인 액세스 한정자가 접근자에 대한 액세스를 차단하고 할당을 시도할 때 오류를 생성함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-136">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a><span data-ttu-id="06d2e-137">주석</span><span class="sxs-lookup"><span data-stu-id="06d2e-137">Comments</span></span>  
 <span data-ttu-id="06d2e-138">`new private string Id` 선언을 `new public string Id`로 바꿀 경우 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="06d2e-138">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="06d2e-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06d2e-139">See also</span></span>

- [<span data-ttu-id="06d2e-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="06d2e-140">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="06d2e-141">속성</span><span class="sxs-lookup"><span data-stu-id="06d2e-141">Properties</span></span>](./properties.md)
- [<span data-ttu-id="06d2e-142">인덱서</span><span class="sxs-lookup"><span data-stu-id="06d2e-142">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="06d2e-143">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="06d2e-143">Access Modifiers</span></span>](./access-modifiers.md)
