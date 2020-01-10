---
title: 특성
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: ff38cfdc228fd1eae1ace734ed2688c62c66499a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709558"
---
# <a name="attributes"></a><span data-ttu-id="51477-102">특성</span><span class="sxs-lookup"><span data-stu-id="51477-102">Attributes</span></span>
<span data-ttu-id="51477-103"><xref:System.Attribute?displayProperty=nameWithType>는 사용자 지정 특성을 정의 하는 데 사용 되는 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="51477-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="51477-104">특성은 어셈블리, 형식, 멤버 및 매개 변수와 같은 프로그래밍 요소에 추가할 수 있는 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="51477-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="51477-105">어셈블리의 메타 데이터에 저장 되 고 리플렉션 Api를 사용 하 여 런타임에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51477-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="51477-106">예를 들어 프레임 워크는 형식 또는 멤버가 더 이상 사용 되지 않음을 나타내기 위해 형식 또는 멤버에 적용 될 수 있는 <xref:System.ObsoleteAttribute>를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="51477-107">특성에는 특성과 관련 된 추가 데이터를 포함 하는 하나 이상의 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51477-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="51477-108">예를 들어, 형식 또는 멤버가 더 이상 사용 되지 않는 릴리스에 대 한 추가 정보 및 사용 되지 않는 API를 교체 하는 새 Api에 대 한 설명을 `ObsoleteAttribute` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51477-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="51477-109">특성이 적용 될 때 특성의 일부 속성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="51477-110">이러한 속성은 위치 생성자 매개 변수로 표시 되기 때문에 필수 속성 또는 필수 인수 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="51477-111">예를 들어 <xref:System.Diagnostics.ConditionalAttribute>의 <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> 속성은 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="51477-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="51477-112">특성이 적용 될 때 반드시 지정 해야 하는 것은 아니지만 속성을 선택적 속성 (또는 선택적 인수) 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="51477-113">이러한 속성은 설정 가능한 속성으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51477-113">They are represented by settable properties.</span></span> <span data-ttu-id="51477-114">컴파일러는 특성이 적용 될 때 이러한 속성을 설정 하는 특수 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="51477-115">예를 들어 <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 속성은 선택적 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51477-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="51477-116">**✓ DO** "특성" 접미사를 사용 하 여 사용자 지정 특성 클래스 이름</span><span class="sxs-lookup"><span data-stu-id="51477-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="51477-117">**✓ DO** 적용 된 <xref:System.AttributeUsageAttribute> 사용자 지정 특성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51477-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="51477-118">**✓ DO** 옵션 인수에 대해 설정 가능한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="51477-119">**✓ DO** 필수 인수에 대 한 가져오기 전용 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="51477-120">**✓ DO** 필수 인수에 해당 하는 속성을 초기화할 생성자 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="51477-121">각 매개 변수는 해당 속성으로 동일한 이름 (다른 대/소문자 구분)을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="51477-122">**X AVOID** 에 해당 하는 선택적 인수 속성을 초기화할 생성자 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="51477-123">즉, 생성자와 setter를 모두 사용 하 여 설정할 수 있는 속성은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51477-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="51477-124">이 지침을 사용 하면 선택적 인수를 매우 명확 하 게 사용할 수 있으며, 두 가지 방법으로 동일한 작업을 수행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51477-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="51477-125">**X AVOID** 사용자 지정 특성 생성자 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="51477-126">생성자가 하나뿐인 경우 필요한 인수와 선택적 인수를 사용자에 게 명확 하 게 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="51477-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="51477-127">**✓ DO** 사용자 지정 특성 클래스를 가능 하면 항상 봉인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51477-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="51477-128">이렇게 하면 특성의 조회 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="51477-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="51477-129">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="51477-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="51477-130">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="51477-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51477-131">참조</span><span class="sxs-lookup"><span data-stu-id="51477-131">See also</span></span>

- [<span data-ttu-id="51477-132">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="51477-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="51477-133">사용 지침</span><span class="sxs-lookup"><span data-stu-id="51477-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
