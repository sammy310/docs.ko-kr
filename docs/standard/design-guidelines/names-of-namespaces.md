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
ms.openlocfilehash: 0678f695e3ae7c40660031862c9073a21fd72491
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709233"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="48eda-102">네임스페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="48eda-102">Names of Namespaces</span></span>
<span data-ttu-id="48eda-103">다른 명명 지침과 마찬가지로 네임 스페이스의 이름을 지정할 때의 목표는 프레임 워크를 사용 하 여 프로그래머에 게 네임 스페이스의 콘텐츠를 즉시 알 수 있는 충분 한 명확성을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="48eda-104">다음 템플릿은 네임 스페이스 이름 지정에 대 한 일반 규칙을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="48eda-105">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="48eda-106">**✓ DO** 이름이 같은 다른 회사의 네임 스페이스를 방지 하기 위해 회사 이름이 있는 네임 스페이스 이름 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="48eda-107">**✓ DO** 네임 스페이스 이름의 두 번째 수준에서 안정적이 고 버전에 관계 없이 제품 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="48eda-108">**X DO NOT** 사용 하 여 조직 계층의 기준으로 네임 스페이스 계층의 이름에 대 한 기업의 그룹 이름은 일시적인 경우가 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="48eda-109">관련 기술 그룹에 대 한 네임 스페이스의 계층 구조를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="48eda-110">**✓ DO** 기간이 PascalCasing, 및 별도 네임 스페이스 구성 요소를 사용 하 여 (예: `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="48eda-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="48eda-111">특수 대/소문자 구분을 채택 하는 경우 일반 네임 스페이스 대/소문자를 벗어나는 경우에도 브랜드에서 정의한 대/소문자 구분을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="48eda-112">**✓ CONSIDER** 적절 한 복수형 네임 스페이스 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="48eda-113">예를 들어 `System.Collection` 대신 `System.Collections`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="48eda-114">그러나 브랜드 이름과 머리글자어는이 규칙의 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="48eda-115">예를 들어 `System.IOs` 대신 `System.IO`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="48eda-116">**X DO NOT** 해당 네임 스페이스에서 네임 스페이스 및 형식에 대 한 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="48eda-117">예를 들어 `Debug` 네임 스페이스 이름으로 사용 하지 말고 동일한 네임 스페이스에 `Debug` 라는 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="48eda-118">일부 컴파일러에서는 이러한 형식을 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="48eda-119">네임 스페이스 및 형식 이름 충돌</span><span class="sxs-lookup"><span data-stu-id="48eda-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="48eda-120">**X DO NOT** 와 같은 제네릭 형식 이름을 소개 `Element`, `Node`, `Log`, 및 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="48eda-121">이렇게 하면 일반적인 시나리오에서 형식 이름 충돌이 발생 하 게 될 확률이 매우 높습니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="48eda-122">제네릭 형식 이름 (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`)을 한정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="48eda-123">네임 스페이스의 다양 한 범주에 대해 형식 이름 충돌을 방지 하기 위한 특정 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
- <span data-ttu-id="48eda-124">**응용 프로그램 모델 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="48eda-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="48eda-125">단일 응용 프로그램 모델에 속하는 네임 스페이스는 함께 사용 되는 경우가 많지만 다른 응용 프로그램 모델의 네임 스페이스와 거의 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="48eda-126">예를 들어 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스는 <xref:System.Web.UI?displayProperty=nameWithType> 네임 스페이스와 함께 거의 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="48eda-127">다음은 잘 알려진 응용 프로그램 모델 네임 스페이스 그룹의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="48eda-128">**X DO NOT** 단일 응용 프로그램 모델 내에서는 네임 스페이스의 형식에 같은 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="48eda-129">예를 들어 <xref:System.Web.UI?displayProperty=nameWithType> 네임 스페이스에 `Page`이라는 형식이 이미 포함 되어 있으므로 `Page` 라는 형식을 <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 네임 스페이스에 추가 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="48eda-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
- <span data-ttu-id="48eda-130">**인프라 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="48eda-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="48eda-131">이 그룹에는 일반적인 응용 프로그램을 개발 하는 동안 거의 가져오지 않은 네임 스페이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="48eda-132">예를 들어 `.Design` 네임 스페이스는 프로그래밍 도구를 개발할 때 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="48eda-133">이러한 네임 스페이스의 형식과 충돌을 방지 하는 것은 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
- <span data-ttu-id="48eda-134">**핵심 네임 스페이스**</span><span class="sxs-lookup"><span data-stu-id="48eda-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="48eda-135">핵심 네임 스페이스에는 응용 프로그램 모델의 네임 스페이스와 인프라 네임 스페이스를 제외한 모든 `System` 네임 스페이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="48eda-136">핵심 네임 스페이스에는 기타, `System`, `System.IO`, `System.Xml`및 `System.Net`포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="48eda-137">**X DO NOT** 제공 핵심 네임 스페이스에서 종류와 충돌 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="48eda-138">예를 들어 `Stream` 형식 이름으로 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="48eda-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="48eda-139">매우 일반적으로 사용 되는 형식 <xref:System.IO.Stream?displayProperty=nameWithType>와 충돌 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
- <span data-ttu-id="48eda-140">**기술 네임 스페이스 그룹**</span><span class="sxs-lookup"><span data-stu-id="48eda-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="48eda-141">이 범주에는 `Microsoft.Build.Utilities` 및 `Microsoft.Build.Tasks`와 같은 처음 두 개의 네임 스페이스 노드가 `(<Company>.<Technology>*`) 인 모든 네임 스페이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="48eda-142">단일 기술에 속한 형식이 서로 충돌 하지 않는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="48eda-143">**X DO NOT** 단일 기술에서 다른 종류와 충돌 하는 형식 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="48eda-144">**X DO NOT** (없는 경우 기술 응용 프로그램 모델에 사용할 수 없습니다) 기술 네임 스페이스의 형식 및 응용 프로그램 모델 네임 스페이스는 간의 유형 이름 충돌을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="48eda-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="48eda-145">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="48eda-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="48eda-146">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="48eda-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48eda-147">참조</span><span class="sxs-lookup"><span data-stu-id="48eda-147">See also</span></span>

- [<span data-ttu-id="48eda-148">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="48eda-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="48eda-149">명명 지침</span><span class="sxs-lookup"><span data-stu-id="48eda-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
