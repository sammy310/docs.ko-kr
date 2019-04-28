---
title: 특성
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: KrzysztofCwalina
ms.openlocfilehash: 6d4cc6615b7f7346e9c8fc2a7264025f318c8a3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785569"
---
# <a name="attributes"></a><span data-ttu-id="a7bdc-102">특성</span><span class="sxs-lookup"><span data-stu-id="a7bdc-102">Attributes</span></span>
<span data-ttu-id="a7bdc-103"><xref:System.Attribute?displayProperty=nameWithType> 사용자 지정 특성을 정의 하는 기본 클래스를 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="a7bdc-104">특성은 어셈블리, 형식, 멤버 및 매개 변수 같은 프로그래밍 요소에 추가할 수 있는 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="a7bdc-105">이러한 어셈블리의 메타 데이터에 저장 되 고 리플렉션 Api를 사용 하 여 런타임에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="a7bdc-106">예를 들어 프레임 워크 정의 <xref:System.ObsoleteAttribute>, 형식 또는 멤버는 형식 또는 멤버는 사용 되지 나타내기 위해 적용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="a7bdc-107">특성에는 특성과 관련 된 추가 데이터를 전달 하는 하나 이상의 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="a7bdc-108">예를 들어 `ObsoleteAttribute` 출시에 대 한 추가 정보를 수행할 수 형식 또는 멤버가 사용 되지 않음 및 사용 되지 않는 API를 바꾸는 새 Api 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="a7bdc-109">특성이 적용 되는 경우 특성의 일부 속성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="a7bdc-110">이러한 라고 필수 속성 또는 필수 인수를 위치 생성자 매개 변수로 표현 됩니다 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="a7bdc-111">예를 들어, 합니다 <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> 의 속성을 <xref:System.Diagnostics.ConditionalAttribute> 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="a7bdc-112">특성이 적용 되는 경우 지정 반드시 없는 속성은 선택적 속성 (또는 선택적 인수) 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="a7bdc-113">설정 가능한 속성으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-113">They are represented by settable properties.</span></span> <span data-ttu-id="a7bdc-114">컴파일러는 특성이 적용 되 면 이러한 속성을 설정 하려면 특수 한 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="a7bdc-115">예를 들어를 <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 속성은 선택적 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="a7bdc-116">**✓ DO** "특성" 접미사를 사용 하 여 사용자 지정 특성 클래스 이름</span><span class="sxs-lookup"><span data-stu-id="a7bdc-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="a7bdc-117">**✓ DO** 적용 된 <xref:System.AttributeUsageAttribute> 사용자 지정 특성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="a7bdc-118">**✓ DO** 옵션 인수에 대해 설정 가능한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="a7bdc-119">**✓ DO** 필수 인수에 대 한 가져오기 전용 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="a7bdc-120">**✓ DO** 필수 인수에 해당 하는 속성을 초기화할 생성자 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="a7bdc-121">각 매개 변수에 해당 속성으로 (하지만 사용 하 여 다른 대/소문자 구분) 이름이 같은 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="a7bdc-122">**X AVOID** 에 해당 하는 선택적 인수 속성을 초기화할 생성자 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="a7bdc-123">즉, 생성자 및 setter를 사용 하 여 설정할 수 있는 속성을 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="a7bdc-124">이 지침 수는 인수는 선택 사항 및이 필요 하며 두 가지 동일한 작업을 수행 하지 않아도 매우 명시적 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="a7bdc-125">**X AVOID** 사용자 지정 특성 생성자 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="a7bdc-126">인수는 필수 및 선택적 사용자에 게 통신 명확 하 게 생성자가 하나만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="a7bdc-127">**✓ DO** 사용자 지정 특성 클래스를 가능 하면 항상 봉인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="a7bdc-128">따라서 더 빠르게 특성에 대 한 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7bdc-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="a7bdc-129">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="a7bdc-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a7bdc-130">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="a7bdc-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bdc-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7bdc-131">See also</span></span>

- [<span data-ttu-id="a7bdc-132">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a7bdc-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a7bdc-133">사용 지침</span><span class="sxs-lookup"><span data-stu-id="a7bdc-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
