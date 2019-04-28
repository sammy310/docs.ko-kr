---
title: 네임스페이스의 이름
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: KrzysztofCwalina
ms.openlocfilehash: 0099c5c8a863023099b377e139461606de3e1e1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940987"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="48e86-102">네임스페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="48e86-102">Names of Namespaces</span></span>
<span data-ttu-id="48e86-103">으로 다른 명명 지침을 사용 하 여 목표 네임 스페이스의 이름을 지정할 때 만드는 것 충분 한 명확성 프레임 워크를 사용 하 여 즉시 무엇이 있는지 아는 네임 스페이스의 내용을 짧을 수 프로그래머입니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="48e86-104">다음 템플릿 네임 스페이스 이름에 대 한 일반 규칙을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="48e86-105">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="48e86-106">**✓ DO** 이름이 같은 다른 회사의 네임 스페이스를 방지 하기 위해 회사 이름이 있는 네임 스페이스 이름 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="48e86-107">**✓ DO** 네임 스페이스 이름의 두 번째 수준에서 안정적이 고 버전에 관계 없이 제품 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="48e86-108">**X DO NOT** 사용 하 여 조직 계층의 기준으로 네임 스페이스 계층의 이름에 대 한 기업의 그룹 이름은 일시적인 경우가 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="48e86-109">그룹 관련된 기술에 대 한 네임 스페이스의 계층 구조를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="48e86-110">**✓ DO** 기간이 PascalCasing, 및 별도 네임 스페이스 구성 요소를 사용 하 여 (예: `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="48e86-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="48e86-111">브랜드에서 않던 대/소문자를 사용 하는 경우 규칙 대/소문자 기본 네임 스페이스에서에서 파생 하는 경우에 사용자 브랜드에 정의 된 대/소문자를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="48e86-112">**✓ CONSIDER** 적절 한 복수형 네임 스페이스 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="48e86-113">예를 들어 `System.Collection` 대신 `System.Collections`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="48e86-114">하지만 브랜드 이름 및 머리글자어가이 규칙에 대 한 예외를 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="48e86-115">예를 들어 `System.IOs` 대신 `System.IO`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="48e86-116">**X DO NOT** 해당 네임 스페이스에서 네임 스페이스 및 형식에 대 한 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="48e86-117">예를 들어, 사용 하지 마십시오 `Debug` 네임 스페이스와 이름을 지정 하 고 다음 라는 클래스도 제공 `Debug` 동일한 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="48e86-118">여러 컴파일러에서는 해당 형식을 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="48e86-119">네임 스페이스 및 형식 이름 충돌</span><span class="sxs-lookup"><span data-stu-id="48e86-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="48e86-120">**X DO NOT** 와 같은 제네릭 형식 이름을 소개 `Element`, `Node`, `Log`, 및 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="48e86-121">이렇게 이름을 입력으로 이어질 시나리오의 일반적인 충돌 가능성이 매우 높은 경우</span><span class="sxs-lookup"><span data-stu-id="48e86-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="48e86-122">제네릭 형식 이름을 정규화 해야 있습니다 (`FormElement`, `XmlNode`를 `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="48e86-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="48e86-123">네임 스페이스의 다른 범주에 대 한 형식 이름 충돌을 방지 하는 것에 대 한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
- <span data-ttu-id="48e86-124">**응용 프로그램 모델 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="48e86-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="48e86-125">단일 응용 프로그램 모델에 속한 네임 스페이스는 종종 매우 함께 사용 하지만 다른 응용 프로그램 모델의 네임 스페이스를 사용 하 여 사용할 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="48e86-126">예를 들어 합니다 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스와 함께 사용 되는 거의 <xref:System.Web.UI?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="48e86-127">다음은 잘 알려진 응용 프로그램 모델 네임 스페이스 그룹 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="48e86-128">**X DO NOT** 단일 응용 프로그램 모델 내에서는 네임 스페이스의 형식에 같은 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="48e86-129">예를 들어 이라는 형식을 추가 하지 마십시오 `Page` 에 <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 네임 스페이스 때문에 <xref:System.Web.UI?displayProperty=nameWithType> 네임 스페이스에는 이미 명명 된 형식이 포함 되어 `Page`입니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
- <span data-ttu-id="48e86-130">**인프라 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="48e86-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="48e86-131">이 그룹에 일반적인 응용 프로그램을 개발 하는 동안 거의 가져온 네임 스페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="48e86-132">예를 들어 `.Design` 네임 스페이스는 프로그래밍 개발 도구 때 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="48e86-133">이러한 네임 스페이스의 형식을 사용 하 여 충돌을 방지 합니다. 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
- <span data-ttu-id="48e86-134">**핵심 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="48e86-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="48e86-135">모든 핵심 네임 스페이스 포함 `System` 네임 스페이스를 응용 프로그램 모델 및 인프라 네임 스페이스를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="48e86-136">특히, 핵심 네임 스페이스를 포함 `System`, `System.IO`를 `System.Xml`, 및 `System.Net`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="48e86-137">**X DO NOT** 제공 핵심 네임 스페이스에서 종류와 충돌 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="48e86-138">예를 들어, 사용 하지 마십시오 `Stream` 형식 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="48e86-139">충돌 <xref:System.IO.Stream?displayProperty=nameWithType>, 매우 일반적으로 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
- <span data-ttu-id="48e86-140">**기술 네임 스페이스 그룹**</span><span class="sxs-lookup"><span data-stu-id="48e86-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="48e86-141">이 범주에 동일한 처음 두 개의 네임 스페이스 노드를 사용 하 여 모든 네임 스페이스를 포함 `(<Company>.<Technology>*`), 같은 `Microsoft.Build.Utilities` 및 `Microsoft.Build.Tasks`합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="48e86-142">것이 단일 기술을에 속하는 형식에 서로 충돌 하지 않는지 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="48e86-143">**X DO NOT** 단일 기술에서 다른 종류와 충돌 하는 형식 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="48e86-144">**X DO NOT** (없는 경우 기술 응용 프로그램 모델에 사용할 수 없습니다) 기술 네임 스페이스의 형식 및 응용 프로그램 모델 네임 스페이스는 간의 유형 이름 충돌을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e86-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="48e86-145">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="48e86-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="48e86-146">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="48e86-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e86-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="48e86-147">See also</span></span>

- [<span data-ttu-id="48e86-148">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="48e86-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="48e86-149">명명 지침</span><span class="sxs-lookup"><span data-stu-id="48e86-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
