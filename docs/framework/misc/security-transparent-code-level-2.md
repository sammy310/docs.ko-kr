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
ms.openlocfilehash: ea782b346f6c53664a8aeb736c7d7a4509d83985
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974939"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="523e0-102">보안 투명 코드, 수준 2</span><span class="sxs-lookup"><span data-stu-id="523e0-102">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="523e0-103">수준 2 투명도는 .NET Framework 4에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-103">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="523e0-104">이 모델의 세 가지 개념은 투명 코드, 보안 안전에 중요 코드 및 보안에 중요 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="523e0-105">완전 신뢰로 실행되는 코드를 포함하는 투명 코드는 다른 투명 코드나 보안 안전에 중요 코드만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="523e0-106">도메인의 부분 신뢰 권한 집합(있는 경우)에서 허용하는 작업만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="523e0-107">투명 코드는 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-107">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="523e0-108"><xref:System.Security.CodeAccessPermission.Assert%2A> 또는 권한 상승을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="523e0-109">안전하지 않거나 확인할 수 없는 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-109">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="523e0-110">중요한 코드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-110">Directly call critical code.</span></span>

  - <span data-ttu-id="523e0-111"><xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성이 포함된 코드나 네이티브 코드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="523e0-112"><xref:System.Security.Permissions.SecurityAction.LinkDemand>로 보호된 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="523e0-113">중요한 형식에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-113">Inherit from critical types.</span></span>

  <span data-ttu-id="523e0-114">또한 투명 메서드는 중요한 가상 메서드를 재정의하거나 중요한 인터페이스 메서드를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="523e0-115">안전에 중요 코드는 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="523e0-116">이 코드는 완전 신뢰 코드의 제한된 노출 영역을 노출하고, 정확성 및 보안 확인은 안전에 중요 코드에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="523e0-117">보안에 중요 코드는 모든 코드를 호출할 수 있고 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="523e0-118">사용 예제 및 동작</span><span class="sxs-lookup"><span data-stu-id="523e0-118">Usage Examples and Behaviors</span></span>

<span data-ttu-id="523e0-119">.NET Framework 4 개 규칙 (수준 2 투명도)을 지정 하려면 어셈블리에 대해 다음 주석을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-119">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="523e0-120">.NET Framework 2.0 규칙(수준 1 투명도)으로 잠그려면 다음 주석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-120">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="523e0-121">어셈블리에 주석을 추가 하지 않으면 기본적으로 .NET Framework 4 규칙이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-121">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="523e0-122">그러나 권장 되는 모범 사례는 기본값에 따라 대신 <xref:System.Security.SecurityRulesAttribute> 특성을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-122">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="523e0-123">어셈블리 수준 주석</span><span class="sxs-lookup"><span data-stu-id="523e0-123">Assembly-wide Annotation</span></span>

<span data-ttu-id="523e0-124">어셈블리 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-124">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="523e0-125">특성 없음: 특성을 지정하지 않으면 보안에 중요하게 되어 상속 규칙을 위반하는 경우(예: 투명한 가상 또는 인터페이스 메서드를 재정의하거나 구현할 경우)를 제외하고 런타임은 모든 코드를 보안에 중요 코드로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-125">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="523e0-126">이 경우 메서드는 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-126">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="523e0-127">특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-127">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="523e0-128">`SecurityTransparent`: 모든 코드가 투명합니다. 전체 어셈블리는 권한이 필요하거나 안전하지 않은 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-128">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="523e0-129">`SecurityCritical`: 이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-129">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="523e0-130">이 시나리오는 특성을 지정하지 않는 것과 비슷하지만, 공용 언어 런타임이 투명도 규칙을 자동으로 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-130">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="523e0-131">예를 들어 가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 기본적으로 해당 메서드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-131">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="523e0-132">메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석으로 처리해야 합니다. 그러지 않으면 로드 시 <xref:System.TypeLoadException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-132">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="523e0-133">이 규칙은 기본 클래스와 파생 클래스가 둘 다 같은 어셈블리에 있을 경우에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-133">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="523e0-134">`AllowPartiallyTrustedCallers`(수준 2만 해당): 모든 코드가 기본적으로 투명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-134">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="523e0-135">그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-135">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="523e0-136">다음 표에서는 수준 2에 대 한 어셈블리 수준 동작과 수준 1을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-136">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="523e0-137">Assembly 특성</span><span class="sxs-lookup"><span data-stu-id="523e0-137">Assembly attribute</span></span>|<span data-ttu-id="523e0-138">수준 2</span><span class="sxs-lookup"><span data-stu-id="523e0-138">Level 2</span></span>|<span data-ttu-id="523e0-139">수준 1</span><span class="sxs-lookup"><span data-stu-id="523e0-139">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="523e0-140">부분적으로 신뢰할 수 있는 어셈블리에 대한 특성 없음</span><span class="sxs-lookup"><span data-stu-id="523e0-140">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="523e0-141">형식 및 멤버는 기본적으로 투명하지만 보안에 중요하거나 보안 안전에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-141">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="523e0-142">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-142">All types and members are transparent.</span></span>|
|<span data-ttu-id="523e0-143">특성 없음</span><span class="sxs-lookup"><span data-stu-id="523e0-143">No attribute</span></span>|<span data-ttu-id="523e0-144">특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-144">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="523e0-145">보안에 중요하게 되어 상속 규칙을 위반하는 경우를 제외하고 모든 형식 및 멤버가 보안에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-145">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="523e0-146">완전히 신뢰할 수 있는 어셈블리(전역 어셈블리 캐시에 포함 또는 `AppDomain`에서 완전 신뢰로 식별됨)에서 모든 형식은 투명하고 모든 멤버는 보안 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-146">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="523e0-147">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-147">All types and members are transparent.</span></span>|<span data-ttu-id="523e0-148">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-148">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="523e0-149">해당 없음.</span><span class="sxs-lookup"><span data-stu-id="523e0-149">Not applicable.</span></span>|<span data-ttu-id="523e0-150">모든 형식 및 멤버가 보안에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-150">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="523e0-151">이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-151">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="523e0-152">가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 해당 메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석을 달아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-152">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="523e0-153">모든 코드가 기본적으로 투명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-153">All code defaults to transparent.</span></span> <span data-ttu-id="523e0-154">그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-154">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="523e0-155">형식 및 멤버 주석</span><span class="sxs-lookup"><span data-stu-id="523e0-155">Type and Member Annotation</span></span>

<span data-ttu-id="523e0-156">형식에 적용되는 보안 특성은 형식에 의해 도입되는 멤버에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-156">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="523e0-157">그러나 기본 클래스 또는 인터페이스 구현의 가상 또는 추상 재정의에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-157">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="523e0-158">형식 및 멤버 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-158">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="523e0-159">`SecurityCritical`: 형식 또는 멤버가 중요하고 완전 신뢰 코드를 통해서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-159">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="523e0-160">보안에 중요 형식에 도입된 메서드는 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-160">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="523e0-161">기본 클래스 또는 인터페이스에 도입되고 보안에 중요 클래스에서 재정의되거나 구현되는 가상 및 추상 메서드는 기본적으로 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-161">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="523e0-162">이들 메서드는 `SecuritySafeCritical` 또는 `SecurityCritical`로 식별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-162">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="523e0-163">`SecuritySafeCritical`: 형식 또는 멤버가 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-163">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="523e0-164">그러나 형식 또는 멤버는 투명(부분적으로 신뢰할 수 있는) 코드에서 호출할 수 있고 다른 중요한 코드와 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-164">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="523e0-165">코드는 보안을 위해 감사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-165">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="523e0-166">재정의 패턴</span><span class="sxs-lookup"><span data-stu-id="523e0-166">Override Patterns</span></span>

<span data-ttu-id="523e0-167">다음 표에서는 수준 2 투명도에 허용되는 메서드 재정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-167">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="523e0-168">기본 가상/인터페이스 멤버</span><span class="sxs-lookup"><span data-stu-id="523e0-168">Base virtual/interface member</span></span>|<span data-ttu-id="523e0-169">재정의/인터페이스</span><span class="sxs-lookup"><span data-stu-id="523e0-169">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="523e0-170">상속 규칙</span><span class="sxs-lookup"><span data-stu-id="523e0-170">Inheritance Rules</span></span>

<span data-ttu-id="523e0-171">이 섹션에서는 액세스 권한과 기능에 따라 다음 순서가 `Transparent`, `Critical` 및 `SafeCritical` 코드에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-171">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="523e0-172">형식에 대한 규칙: 왼쪽에서 오른쪽으로 이동하면 액세스 권한이 더 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-172">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="523e0-173">파생 형식은 기본 형식 이상으로 제한적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-173">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="523e0-174">메서드에 대한 규칙: 파생 메서드는 기본 메서드의 접근성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-174">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="523e0-175">기본 동작의 경우 주석으로 처리되지 않은 모든 파생 메서드는 `Transparent`입니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-175">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="523e0-176">재정의된 메서드가 `SecurityCritical`로 명시적으로 주석을 달지 않으면 중요한 형식의 파생 항목으로 인해 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-176">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="523e0-177">다음 표에서는 허용되는 형식 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-177">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="523e0-178">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="523e0-178">Base class</span></span>|<span data-ttu-id="523e0-179">파생 클래스는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-179">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="523e0-180">다음 표에서는 허용되지 않는 형식 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-180">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="523e0-181">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="523e0-181">Base class</span></span>|<span data-ttu-id="523e0-182">파생 클래스는 다음과 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-182">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="523e0-183">다음 표에서는 허용되는 메서드 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-183">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="523e0-184">기본 메서드</span><span class="sxs-lookup"><span data-stu-id="523e0-184">Base method</span></span>|<span data-ttu-id="523e0-185">파생 메서드는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-185">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="523e0-186">다음 표에서는 허용되지 않는 메서드 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-186">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="523e0-187">기본 메서드</span><span class="sxs-lookup"><span data-stu-id="523e0-187">Base method</span></span>|<span data-ttu-id="523e0-188">파생 메서드는 다음과 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-188">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="523e0-189">이들 상속 규칙은 수준 2 형식 및 멤버에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-189">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="523e0-190">수준 1 어셈블리의 형식은 수준 2 보안에 중요 형식 및 멤버에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-190">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="523e0-191">따라서 수준 2 형식 및 멤버에는 수준 1 상속자에 대한 별도의 상속 요청이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-191">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="523e0-192">추가 정보 및 규칙</span><span class="sxs-lookup"><span data-stu-id="523e0-192">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="523e0-193">LinkDemand 지원</span><span class="sxs-lookup"><span data-stu-id="523e0-193">LinkDemand Support</span></span>

<span data-ttu-id="523e0-194">수준 2 투명도 모델은 <xref:System.Security.Permissions.SecurityAction.LinkDemand>를 <xref:System.Security.SecurityCriticalAttribute> 특성으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-194">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="523e0-195">레거시(수준 1) 코드에서 <xref:System.Security.Permissions.SecurityAction.LinkDemand>는 자동으로 <xref:System.Security.Permissions.SecurityAction.Demand>로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-195">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="523e0-196">반사</span><span class="sxs-lookup"><span data-stu-id="523e0-196">Reflection</span></span>

<span data-ttu-id="523e0-197">중요한 메서드를 호출하거나 중요한 필드를 읽으면 private 메서드나 필드를 호출한 것처럼 완전 신뢰에 대한 요청이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-197">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="523e0-198">따라서 완전 신뢰 코드는 중요한 메서드를 호출할 수 있지만 부분 신뢰 코드는 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-198">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="523e0-199">형식, 메서드 또는 필드가 `SecurityCritical`, `SecuritySafeCritical` 또는 `SecurityTransparent`인지 확인하려고 <xref:System.Reflection> 네임스페이스에 <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> 및 <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A> 속성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-199">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="523e0-200">이들 속성을 사용하여 특성이 있는지 확인하는 것이 아니라 리플렉션을 통해 투명도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-200">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="523e0-201">투명도 규칙은 복잡하고 특성이 있는지 확인하는 것으로는 충분하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-201">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="523e0-202">`SafeCritical` 메서드는 <xref:System.Type.IsSecurityCritical%2A> 및 <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>에 대 한 `true`를 반환 합니다 .이는 중요 한 코드와 동일한 기능을 포함 하지만 투명 코드에서 호출할 수 있기 `SafeCritical` 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-202">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="523e0-203">동적 메서드는 연결된 모듈의 투명도를 상속합니다. 형식의 투명도를 상속하지 않습니다(형식에 연결된 경우).</span><span class="sxs-lookup"><span data-stu-id="523e0-203">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="523e0-204">완전 신뢰에서 확인 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="523e0-204">Skip Verification in Full Trust</span></span>

<span data-ttu-id="523e0-205"><xref:System.Security.SecurityRulesAttribute> 특성에서 <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성을 `true`로 설정하여 완전히 신뢰할 수 있는 어셈블리에 대한 확인을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-205">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="523e0-206"><xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성은 기본적으로 `false`이므로 확인을 건너뛰려면 속성을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-206">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="523e0-207">이 작업은 최적화 목적으로만 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-207">This should be done for optimization purposes only.</span></span> <span data-ttu-id="523e0-208">[PEVerify 도구의](../tools/peverify-exe-peverify-tool.md)`transparent` 옵션을 사용 하 여 어셈블리의 투명 코드를 확인할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="523e0-208">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="523e0-209">참조</span><span class="sxs-lookup"><span data-stu-id="523e0-209">See also</span></span>

- [<span data-ttu-id="523e0-210">보안 투명 코드, 수준 1</span><span class="sxs-lookup"><span data-stu-id="523e0-210">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="523e0-211">보안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="523e0-211">Security Changes</span></span>](../security/security-changes.md)
