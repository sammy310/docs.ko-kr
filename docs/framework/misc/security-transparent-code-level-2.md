---
title: 보안 투명 코드, 수준 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62c25b14fa7b3867bbdbcb2f1e08cc16ce349e72
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156080"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="07c99-102">보안 투명 코드, 수준 2</span><span class="sxs-lookup"><span data-stu-id="07c99-102">Security-Transparent Code, Level 2</span></span>
<a name="top"></a>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="07c99-103">수준 2 투명도는 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 새로 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-103">Level 2 transparency was introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="07c99-104">이 모델의 세 가지 개념은 투명 코드, 보안 안전에 중요 코드 및 보안에 중요 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>  
  
-   <span data-ttu-id="07c99-105">완전 신뢰로 실행되는 코드를 포함하는 투명 코드는 다른 투명 코드나 보안 안전에 중요 코드만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="07c99-106">도메인의 부분 신뢰 권한 집합(있는 경우)에서 허용하는 작업만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="07c99-107">투명 코드는 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-107">Transparent code cannot do the following:</span></span>  
  
    -   <span data-ttu-id="07c99-108"><xref:System.Security.CodeAccessPermission.Assert%2A> 또는 권한 상승을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>  
  
    -   <span data-ttu-id="07c99-109">안전하지 않거나 확인할 수 없는 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-109">Contain unsafe or unverifiable code.</span></span>  
  
    -   <span data-ttu-id="07c99-110">중요한 코드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-110">Directly call critical code.</span></span>  
  
    -   <span data-ttu-id="07c99-111"><xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성이 포함된 코드나 네이티브 코드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>  
  
    -   <span data-ttu-id="07c99-112"><xref:System.Security.Permissions.SecurityAction.LinkDemand>로 보호된 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>  
  
    -   <span data-ttu-id="07c99-113">중요한 형식에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-113">Inherit from critical types.</span></span>  
  
     <span data-ttu-id="07c99-114">또한 투명 메서드는 중요한 가상 메서드를 재정의하거나 중요한 인터페이스 메서드를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>  
  
-   <span data-ttu-id="07c99-115">안전에 중요 코드는 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="07c99-116">이 코드는 완전 신뢰 코드의 제한된 노출 영역을 노출하고, 정확성 및 보안 확인은 안전에 중요 코드에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>  
  
-   <span data-ttu-id="07c99-117">보안에 중요 코드는 모든 코드를 호출할 수 있고 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>  
  
 <span data-ttu-id="07c99-118">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-118">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="07c99-119">사용 예제 및 동작</span><span class="sxs-lookup"><span data-stu-id="07c99-119">Usage Examples and Behaviors</span></span>](#examples)  
  
-   [<span data-ttu-id="07c99-120">재정의 패턴</span><span class="sxs-lookup"><span data-stu-id="07c99-120">Override Patterns</span></span>](#override)  
  
-   [<span data-ttu-id="07c99-121">상속 규칙</span><span class="sxs-lookup"><span data-stu-id="07c99-121">Inheritance Rules</span></span>](#inheritance)  
  
-   [<span data-ttu-id="07c99-122">추가 정보 및 규칙</span><span class="sxs-lookup"><span data-stu-id="07c99-122">Additional Information and Rules</span></span>](#additional)  
  
<a name="examples"></a>   
## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="07c99-123">사용 예제 및 동작</span><span class="sxs-lookup"><span data-stu-id="07c99-123">Usage Examples and Behaviors</span></span>  
 <span data-ttu-id="07c99-124">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 규칙(수준 2 투명도)을 지정하려면 어셈블리에 대한 다음 주석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-124">To specify [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules (level 2 transparency), use the following annotation for an assembly:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level2)]  
```  
  
 <span data-ttu-id="07c99-125">.NET Framework 2.0 규칙(수준 1 투명도)으로 잠그려면 다음 주석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-125">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 <span data-ttu-id="07c99-126">어셈블리를 주석으로 처리하지 않으면 기본적으로 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-126">If you do not annotate an assembly, the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules are used by default.</span></span> <span data-ttu-id="07c99-127">그러나 권장 되는 가장 좋은 방법은 사용 하는 것은 <xref:System.Security.SecurityRulesAttribute> 기본값에 따라 대신 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-127">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>  
  
### <a name="assembly-wide-annotation"></a><span data-ttu-id="07c99-128">어셈블리 수준 주석</span><span class="sxs-lookup"><span data-stu-id="07c99-128">Assembly-wide Annotation</span></span>  
 <span data-ttu-id="07c99-129">어셈블리 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-129">The following rules apply to the use of attributes at the assembly level:</span></span>  
  
-   <span data-ttu-id="07c99-130">특성이 없습니다. 모든 특성을 지정 하지 않으면 런타임 보안에 중요 보안에 중요 한 상속 규칙을 위반 하는 위치를 제외한 모든 코드는 해석 (재정의 하거나를 투명 하 게 구현 하는 경우에 예를 들어, 가상 또는 인터페이스 메서드).</span><span class="sxs-lookup"><span data-stu-id="07c99-130">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="07c99-131">이 경우 메서드는 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-131">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="07c99-132">특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-132">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>  
  
-   `SecurityTransparent`<span data-ttu-id="07c99-133">: 모든 코드는 투명 합니다. 전체 어셈블리 권한이 필요 하거나 안전 하지 않은 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-133">: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>  
  
-   `SecurityCritical`<span data-ttu-id="07c99-134">: 이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-134">: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="07c99-135">이 시나리오는 특성을 지정하지 않는 것과 비슷하지만, 공용 언어 런타임이 투명도 규칙을 자동으로 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-135">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="07c99-136">예를 들어 가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 기본적으로 해당 메서드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-136">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="07c99-137">메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석으로 처리해야 합니다. 그러지 않으면 로드 시 <xref:System.TypeLoadException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-137">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="07c99-138">이 규칙은 기본 클래스와 파생 클래스가 둘 다 같은 어셈블리에 있을 경우에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-138">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>  
  
-   `AllowPartiallyTrustedCallers` <span data-ttu-id="07c99-139">(수준 2만): 모든 코드가 기본적으로 투명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-139">(level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="07c99-140">그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-140">However, individual types and members can have other attributes.</span></span>  
  
 <span data-ttu-id="07c99-141">다음 표에서 수준 1 수준 2에 대 한 어셈블리 수준 동작을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-141">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>  
  
|<span data-ttu-id="07c99-142">Assembly 특성</span><span class="sxs-lookup"><span data-stu-id="07c99-142">Assembly attribute</span></span>|<span data-ttu-id="07c99-143">수준 2</span><span class="sxs-lookup"><span data-stu-id="07c99-143">Level 2</span></span>|<span data-ttu-id="07c99-144">수준 1</span><span class="sxs-lookup"><span data-stu-id="07c99-144">Level 1</span></span>|  
|------------------------|-------------|-------------|  
|<span data-ttu-id="07c99-145">부분적으로 신뢰할 수 있는 어셈블리에 대한 특성 없음</span><span class="sxs-lookup"><span data-stu-id="07c99-145">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="07c99-146">형식 및 멤버는 기본적으로 투명하지만 보안에 중요하거나 보안 안전에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-146">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="07c99-147">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-147">All types and members are transparent.</span></span>|  
|<span data-ttu-id="07c99-148">특성 없음</span><span class="sxs-lookup"><span data-stu-id="07c99-148">No attribute</span></span>|<span data-ttu-id="07c99-149">특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-149">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="07c99-150">보안에 중요하게 되어 상속 규칙을 위반하는 경우를 제외하고 모든 형식 및 멤버가 보안에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-150">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="07c99-151">완전히 신뢰할 수 있는 어셈블리(전역 어셈블리 캐시에 포함 또는 `AppDomain`에서 완전 신뢰로 식별됨)에서 모든 형식은 투명하고 모든 멤버는 보안 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-151">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|  
|`SecurityTransparent`|<span data-ttu-id="07c99-152">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-152">All types and members are transparent.</span></span>|<span data-ttu-id="07c99-153">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-153">All types and members are transparent.</span></span>|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="07c99-154">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="07c99-154">Not applicable.</span></span>|<span data-ttu-id="07c99-155">모든 형식 및 멤버가 보안에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-155">All types and members are security-critical.</span></span>|  
|`SecurityCritical`|<span data-ttu-id="07c99-156">이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-156">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="07c99-157">가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 해당 메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석을 달아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-157">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="07c99-158">모든 코드가 기본적으로 투명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-158">All code defaults to transparent.</span></span> <span data-ttu-id="07c99-159">그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-159">However, individual types and members can have other attributes.</span></span>|  
  
### <a name="type-and-member-annotation"></a><span data-ttu-id="07c99-160">형식 및 멤버 주석</span><span class="sxs-lookup"><span data-stu-id="07c99-160">Type and Member Annotation</span></span>  
 <span data-ttu-id="07c99-161">형식에 적용되는 보안 특성은 형식에 의해 도입되는 멤버에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-161">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="07c99-162">그러나 기본 클래스 또는 인터페이스 구현의 가상 또는 추상 재정의에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-162">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="07c99-163">형식 및 멤버 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-163">The following rules apply to the use of attributes at the type and member level:</span></span>  
  
-   `SecurityCritical`<span data-ttu-id="07c99-164">: 형식 또는 멤버는 중요 및 완전 신뢰 코드 에서만 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-164">: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="07c99-165">보안에 중요 형식에 도입된 메서드는 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-165">Methods that are introduced in a security-critical type are critical.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="07c99-166">기본 클래스 또는 인터페이스에 도입되고 보안에 중요 클래스에서 재정의되거나 구현되는 가상 및 추상 메서드는 기본적으로 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-166">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="07c99-167">이들 메서드는 `SecuritySafeCritical` 또는 `SecurityCritical`로 식별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-167">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>  
  
-   `SecuritySafeCritical`<span data-ttu-id="07c99-168">: 형식 또는 멤버가 안전에 중요 한 경우</span><span class="sxs-lookup"><span data-stu-id="07c99-168">: The type or member is safe-critical.</span></span> <span data-ttu-id="07c99-169">그러나 형식 또는 멤버는 투명(부분적으로 신뢰할 수 있는) 코드에서 호출할 수 있고 다른 중요한 코드와 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-169">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="07c99-170">코드는 보안을 위해 감사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-170">The code must be audited for security.</span></span>  
  
 [<span data-ttu-id="07c99-171">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="07c99-171">Back to top</span></span>](#top)  
  
<a name="override"></a>   
## <a name="override-patterns"></a><span data-ttu-id="07c99-172">재정의 패턴</span><span class="sxs-lookup"><span data-stu-id="07c99-172">Override Patterns</span></span>  
 <span data-ttu-id="07c99-173">다음 표에서는 수준 2 투명도에 허용되는 메서드 재정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-173">The following table shows the method overrides allowed for level 2 transparency.</span></span>  
  
|<span data-ttu-id="07c99-174">기본 가상/인터페이스 멤버</span><span class="sxs-lookup"><span data-stu-id="07c99-174">Base virtual/interface member</span></span>|<span data-ttu-id="07c99-175">재정의/인터페이스</span><span class="sxs-lookup"><span data-stu-id="07c99-175">Override/interface</span></span>|  
|------------------------------------|-------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 [<span data-ttu-id="07c99-176">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="07c99-176">Back to top</span></span>](#top)  
  
<a name="inheritance"></a>   
## <a name="inheritance-rules"></a><span data-ttu-id="07c99-177">상속 규칙</span><span class="sxs-lookup"><span data-stu-id="07c99-177">Inheritance Rules</span></span>  
 <span data-ttu-id="07c99-178">이 섹션에서는 액세스 권한과 기능에 따라 다음 순서가 `Transparent`, `Critical` 및 `SafeCritical` 코드에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-178">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>  
  
 `Transparent` < `SafeCritical` < `Critical`  
  
-   <span data-ttu-id="07c99-179">형식에 대 한 규칙: 왼쪽에서 오른쪽으로 이동, 액세스 더 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-179">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="07c99-180">파생 형식은 기본 형식 이상으로 제한적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-180">Derived types must be at least as restrictive as the base type.</span></span>  
  
-   <span data-ttu-id="07c99-181">메서드에 대 한 규칙: 파생된 메서드는 기본 메서드에서 내게 필요한 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-181">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="07c99-182">기본 동작의 경우 주석으로 처리되지 않은 모든 파생 메서드는 `Transparent`입니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-182">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="07c99-183">재정의된 메서드가 `SecurityCritical`로 명시적으로 주석을 달지 않으면 중요한 형식의 파생 항목으로 인해 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-183">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>  
  
 <span data-ttu-id="07c99-184">다음 표에서는 허용되는 형식 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-184">The following table shows the allowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="07c99-185">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="07c99-185">Base class</span></span>|<span data-ttu-id="07c99-186">파생 클래스는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-186">Derived class can be</span></span>|  
|----------------|--------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`SafeCritical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="07c99-187">다음 표에서는 허용되지 않는 형식 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-187">The following table shows the disallowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="07c99-188">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="07c99-188">Base class</span></span>|<span data-ttu-id="07c99-189">파생 클래스는 다음과 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-189">Derived class cannot be</span></span>|  
|----------------|-----------------------------|  
|`SafeCritical`|`Transparent`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
 <span data-ttu-id="07c99-190">다음 표에서는 허용되는 메서드 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-190">The following table shows the allowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="07c99-191">기본 메서드</span><span class="sxs-lookup"><span data-stu-id="07c99-191">Base method</span></span>|<span data-ttu-id="07c99-192">파생 메서드는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-192">Derived method can be</span></span>|  
|-----------------|---------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="07c99-193">다음 표에서는 허용되지 않는 메서드 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-193">The following table shows the disallowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="07c99-194">기본 메서드</span><span class="sxs-lookup"><span data-stu-id="07c99-194">Base method</span></span>|<span data-ttu-id="07c99-195">파생 메서드는 다음과 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-195">Derived method cannot be</span></span>|  
|-----------------|------------------------------|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
> [!NOTE]
>  <span data-ttu-id="07c99-196">이들 상속 규칙은 수준 2 형식 및 멤버에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-196">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="07c99-197">수준 1 어셈블리의 형식은 수준 2 보안에 중요 형식 및 멤버에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-197">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="07c99-198">따라서 수준 2 형식 및 멤버에는 수준 1 상속자에 대한 별도의 상속 요청이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-198">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>  
  
 [<span data-ttu-id="07c99-199">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="07c99-199">Back to top</span></span>](#top)  
  
<a name="additional"></a>   
## <a name="additional-information-and-rules"></a><span data-ttu-id="07c99-200">추가 정보 및 규칙</span><span class="sxs-lookup"><span data-stu-id="07c99-200">Additional Information and Rules</span></span>  
  
### <a name="linkdemand-support"></a><span data-ttu-id="07c99-201">LinkDemand 지원</span><span class="sxs-lookup"><span data-stu-id="07c99-201">LinkDemand Support</span></span>  
 <span data-ttu-id="07c99-202">수준 2 투명도 모델은 <xref:System.Security.Permissions.SecurityAction.LinkDemand>를 <xref:System.Security.SecurityCriticalAttribute> 특성으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-202">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="07c99-203">레거시(수준 1) 코드에서 <xref:System.Security.Permissions.SecurityAction.LinkDemand>는 자동으로 <xref:System.Security.Permissions.SecurityAction.Demand>로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-203">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>  
  
### <a name="reflection"></a><span data-ttu-id="07c99-204">반사</span><span class="sxs-lookup"><span data-stu-id="07c99-204">Reflection</span></span>  
 <span data-ttu-id="07c99-205">중요한 메서드를 호출하거나 중요한 필드를 읽으면 private 메서드나 필드를 호출한 것처럼 완전 신뢰에 대한 요청이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-205">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="07c99-206">따라서 완전 신뢰 코드는 중요한 메서드를 호출할 수 있지만 부분 신뢰 코드는 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-206">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>  
  
 <span data-ttu-id="07c99-207">형식, 메서드 또는 필드가 `SecurityCritical`, `SecuritySafeCritical` 또는 `SecurityTransparent`인지 확인하려고 <xref:System.Reflection> 네임스페이스에 <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> 및 <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A> 속성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-207">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="07c99-208">이들 속성을 사용하여 특성이 있는지 확인하는 것이 아니라 리플렉션을 통해 투명도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-208">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="07c99-209">투명도 규칙은 복잡하고 특성이 있는지 확인하는 것으로는 충분하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-209">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07c99-210">A `SafeCritical` 메서드가 반환 `true` 둘 다에 대해 <xref:System.Type.IsSecurityCritical%2A> 및 <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>이므로 `SafeCritical` (중요 한 코드와 동일한 기능을 포함 하지만 투명 코드에서 호출할 수 있습니다)에 실제로 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-210">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>  
  
 <span data-ttu-id="07c99-211">동적 메서드는 연결된 모듈의 투명도를 상속합니다. 형식의 투명도를 상속하지 않습니다(형식에 연결된 경우).</span><span class="sxs-lookup"><span data-stu-id="07c99-211">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>  
  
### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="07c99-212">완전 신뢰에서 확인 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="07c99-212">Skip Verification in Full Trust</span></span>  
 <span data-ttu-id="07c99-213"><xref:System.Security.SecurityRulesAttribute> 특성에서 <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성을 `true`로 설정하여 완전히 신뢰할 수 있는 어셈블리에 대한 확인을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-213">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>  
  
 `[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`  
  
 <span data-ttu-id="07c99-214"><xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성은 기본적으로 `false`이므로 확인을 건너뛰려면 속성을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-214">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="07c99-215">이 작업은 최적화 목적으로만 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-215">This should be done for optimization purposes only.</span></span> <span data-ttu-id="07c99-216">사용 하 여 어셈블리의 투명 한 코드를 확인할 수 있는지 확인 해야 합니다 `transparent` 옵션을 [PEVerify 도구](../../../docs/framework/tools/peverify-exe-peverify-tool.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07c99-216">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c99-217">참고자료</span><span class="sxs-lookup"><span data-stu-id="07c99-217">See also</span></span>

- [<span data-ttu-id="07c99-218">보안 투명 코드, 수준 1</span><span class="sxs-lookup"><span data-stu-id="07c99-218">Security-Transparent Code, Level 1</span></span>](../../../docs/framework/misc/security-transparent-code-level-1.md)
- [<span data-ttu-id="07c99-219">보안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="07c99-219">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)
