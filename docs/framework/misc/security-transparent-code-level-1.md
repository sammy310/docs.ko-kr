---
title: 보안 투명 코드, 수준 1
description: 수준 1 투명도 코드 모델, 투명도 특성 및 보안 투명도 예를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- transparent
- SecurityTreatAsSafeAttribute
- SecurityTransparentAttribute
- SecurityCriticalAttribute
- security-transparent code
- security [.NET Framework], security-transparent code
ms.assetid: 5fd8f46d-3961-46a7-84af-2eb1f48e75cf
ms.openlocfilehash: 75cf38412f3ba21832c5e63898b10bcf681f5904
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855701"
---
# <a name="security-transparent-code-level-1"></a><span data-ttu-id="ec953-103">보안 투명 코드, 수준 1</span><span class="sxs-lookup"><span data-stu-id="ec953-103">Security-Transparent Code, Level 1</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="ec953-104">투명도를 통해 개발자는 부분적으로 신뢰할 수 있는 코드에 기능을 노출하는 더 안전한 .NET Framework 라이브러리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-104">Transparency helps developers write more secure .NET Framework libraries that expose functionality to partially trusted code.</span></span> <span data-ttu-id="ec953-105">수준 1 투명도는 .NET Framework 버전 2.0에서 새로 추가되었고 주로 Microsoft 내에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-105">Level 1 transparency was introduced in the .NET Framework version 2.0 and was primarily used only within Microsoft.</span></span> <span data-ttu-id="ec953-106">.NET Framework 4부터 [수준 2 투명도](security-transparent-code-level-2.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-106">Starting with the .NET Framework 4, you can use [level 2 transparency](security-transparent-code-level-2.md).</span></span> <span data-ttu-id="ec953-107">그러나 이전 보안 규칙과 함께 실행되어야 하는 레거시 코드를 식별할 수 있도록 수준 1 투명도가 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-107">However, level 1 transparency has been retained so that you can identify legacy code that must run with the earlier security rules.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ec953-108">수준 1 투명도는 호환성 목적으로만 지정해야 합니다. 즉, <xref:System.Security.AllowPartiallyTrustedCallersAttribute>를 사용하거나 투명도 모델을 사용하지 않는 .NET Framework 3.5 이하를 사용하여 개발된 코드에만 수준 1을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-108">You should specify level 1 transparency for compatibility only; that is, specify level 1 only for code that was developed with the .NET Framework 3.5 or earlier that uses the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> or does not use the transparency model.</span></span> <span data-ttu-id="ec953-109">예를 들어 부분적으로 신뢰할 수 있는 호출자(APTCA)의 호출을 허용하는 .NET Framework 2.0 어셈블리에는 수준 1 투명도를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-109">For example, use level 1 transparency for .NET Framework 2.0 assemblies that allow calls from partially trusted callers (APTCA).</span></span> <span data-ttu-id="ec953-110">.NET Framework 4 용으로 개발 된 코드의 경우 항상 수준 2 투명도를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-110">For code that is developed for the .NET Framework 4, always use level 2 transparency.</span></span>  
  
 <span data-ttu-id="ec953-111">이 항목에는 다음과 같은 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-111">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="ec953-112">수준 1 투명도 모델</span><span class="sxs-lookup"><span data-stu-id="ec953-112">The Level 1 Transparency Model</span></span>](#the_level_1_transparency_model)  
  
- [<span data-ttu-id="ec953-113">투명도 특성</span><span class="sxs-lookup"><span data-stu-id="ec953-113">Transparency Attributes</span></span>](#transparency_attributes)  
  
- [<span data-ttu-id="ec953-114">보안 투명도 예제</span><span class="sxs-lookup"><span data-stu-id="ec953-114">Security Transparency Examples</span></span>](#security_transparency_examples)  
  
<a name="the_level_1_transparency_model"></a>
## <a name="the-level-1-transparency-model"></a><span data-ttu-id="ec953-115">수준 1 투명도 모델</span><span class="sxs-lookup"><span data-stu-id="ec953-115">The Level 1 Transparency Model</span></span>  
 <span data-ttu-id="ec953-116">수준 1 투명도를 사용할 경우 코드를 보안 투명, 보안 안전에 중요 및 보안에 중요 메서드로 구분하는 보안 모델을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-116">When you use Level 1 transparency, you are using a security model that separates code into security-transparent, security-safe-critical, and security-critical methods.</span></span>  
  
 <span data-ttu-id="ec953-117">전체 어셈블리, 어셈블리의 일부 클래스 또는 클래스의 일부 메서드를 보안 투명으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-117">You can mark a whole assembly, some classes in an assembly, or some methods in a class as security-transparent.</span></span> <span data-ttu-id="ec953-118">보안 투명 코드는 권한을 높일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-118">Security-transparent code cannot elevate privileges.</span></span> <span data-ttu-id="ec953-119">이 제한에 따라 다음 세 가지 결과가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-119">This restriction has three consequences:</span></span>  
  
- <span data-ttu-id="ec953-120">보안 투명 코드는 <xref:System.Security.Permissions.SecurityAction.Assert> 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-120">Security-transparent code cannot perform <xref:System.Security.Permissions.SecurityAction.Assert> actions.</span></span>  
  
- <span data-ttu-id="ec953-121">보안 투명 코드로 충족되는 링크 요청은 전체 요청이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-121">Any link demand that would be satisfied by security-transparent code becomes a full demand.</span></span>  
  
- <span data-ttu-id="ec953-122">보안 투명 코드에서 실행되어야 하는 안전하지 않은(확인할 수 없는) 코드로 인해 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> 보안 권한에 대한 전체 요청이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-122">Any unsafe (unverifiable) code that must execute in security-transparent code causes a full demand for the <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> security permission.</span></span>  
  
 <span data-ttu-id="ec953-123">이들 규칙은 CLR(공용 언어 런타임)에서 실행 중에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-123">These rules are enforced during execution by the common language runtime (CLR).</span></span> <span data-ttu-id="ec953-124">보안 투명 코드는 호출하는 코드의 모든 보안 요구 사항을 다시 호출자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-124">Security-transparent code passes all the security requirements of the code it calls back to its callers.</span></span> <span data-ttu-id="ec953-125">보안 투명 코드를 통해 전달되는 요청은 권한을 높일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-125">Demands that flow through the security-transparent code cannot elevate privileges.</span></span> <span data-ttu-id="ec953-126">조금 신뢰 애플리케이션이 보안 투명 코드를 호출하고 높은 권한에 대한 요청이 발생하면 요청이 다시 조금 신뢰 코드로 전달되고 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-126">If a low-trust application calls security-transparent code and causes a demand for high privilege, the demand will flow back to the low-trust code and fail.</span></span> <span data-ttu-id="ec953-127">보안 투명 코드는 자산 작업을 수행할 수 없으므로 요청을 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-127">The security-transparent code cannot stop the demand because it cannot perform assert actions.</span></span> <span data-ttu-id="ec953-128">완전 신뢰 코드에서 같은 보안 투명 코드를 호출하면 요청이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-128">The same security-transparent code called from full-trust code results in a successful demand.</span></span>  
  
 <span data-ttu-id="ec953-129">보안에 중요는 보안 투명과 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-129">Security-critical is the opposite of security-transparent.</span></span> <span data-ttu-id="ec953-130">보안에 중요 코드는 완전 신뢰를 기반으로 실행되고 모든 권한 있는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-130">Security-critical code executes with full trust and can perform all privileged operations.</span></span> <span data-ttu-id="ec953-131">보안 안전에 중요 코드는 부분적으로 신뢰할 수 있는 호출자가 액세스할 권한이 없는 리소스를 사용하도록 허용하지 않는지 확인하는 폭넓은 보안 감사를 통과한 권한 있는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-131">Security-safe-critical code is privileged code that has been through an extensive security audit to confirm that it does not allow partially trusted callers to use resources they do not have permission to access.</span></span>  
  
 <span data-ttu-id="ec953-132">투명도를 명시적으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-132">You have to apply transparency explicitly.</span></span> <span data-ttu-id="ec953-133">데이터 조작 및 논리를 처리하는 대부분 코드는 일반적으로 보안 투명으로 표시되지만, 권한 상승을 수행하는 더 적은 코드는 보안에 중요 또는 보안 안전에 중요로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-133">The majority of your code that handles data manipulation and logic can typically be marked as security-transparent, whereas the lesser amount of code that performs elevations of privileges is marked as security-critical or security-safe-critical.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ec953-134">수준 1 투명도는 어셈블리 범위로 제한되고 어셈블리 간에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-134">Level 1 transparency is limited to assembly scope; it is not enforced between assemblies.</span></span> <span data-ttu-id="ec953-135">수준 1 투명도는 주로 Microsoft 내에서 보안 감사 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-135">Level 1 transparency was primarily used within Microsoft for security audit purposes.</span></span> <span data-ttu-id="ec953-136">다른 어셈블리의 보안 투명 코드에서 수준 1 어셈블리 내의 보안에 중요 형식 및 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-136">Security-critical types and members within a level 1 assembly can be accessed by security-transparent code in other assemblies.</span></span> <span data-ttu-id="ec953-137">모든 수준 1 보안에 중요 형식 및 멤버에서 완전 신뢰를 위해 링크 요청을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-137">It is important that you perform link demands for full trust in all your level 1 security-critical types and members.</span></span> <span data-ttu-id="ec953-138">보안 안전에 중요 형식 및 멤버는 형식 또는 멤버가 액세스하는 보호된 리소스에 대한 권한이 호출자에게 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-138">Security-safe-critical types and members must also confirm that callers have permissions for protected resources that are accessed by the type or member.</span></span>  
  
 <span data-ttu-id="ec953-139">.NET Framework 이전 버전과의 호환성을 위해 투명도 특성을 사용하여 주석 처리되지 않은 모든 멤버는 보안 안전에 중요로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-139">For backward compatibility with earlier versions of the .NET Framework, all members that are not annotated with transparency attributes are considered to be security-safe-critical.</span></span> <span data-ttu-id="ec953-140">주석으로 처리되지 않은 모든 형식은 투명으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-140">All types that are not annotated are considered to be transparent.</span></span> <span data-ttu-id="ec953-141">투명도의 유효성을 검사하는 정적 분석 규칙은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-141">There are no static analysis rules to validate transparency.</span></span> <span data-ttu-id="ec953-142">따라서 런타임에 투명도 오류를 디버그해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-142">Therefore, you may need to debug transparency errors at run time.</span></span>  
  
<a name="transparency_attributes"></a>
## <a name="transparency-attributes"></a><span data-ttu-id="ec953-143">투명도 특성</span><span class="sxs-lookup"><span data-stu-id="ec953-143">Transparency Attributes</span></span>  
 <span data-ttu-id="ec953-144">다음 표에서는 투명도에 대한 코드를 주석으로 처리하는 데 사용하는 세 가지 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-144">The following table describes the three attributes that you use to annotate your code for transparency.</span></span>  
  
|<span data-ttu-id="ec953-145">attribute</span><span class="sxs-lookup"><span data-stu-id="ec953-145">Attribute</span></span>|<span data-ttu-id="ec953-146">Description</span><span class="sxs-lookup"><span data-stu-id="ec953-146">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute>|<span data-ttu-id="ec953-147">어셈블리 수준에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-147">Allowed only at the assembly level.</span></span> <span data-ttu-id="ec953-148">어셈블리의 모든 형식 및 멤버를 보안 투명으로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-148">Identifies all types and members in the assembly as security-transparent.</span></span> <span data-ttu-id="ec953-149">어셈블리는 보안에 중요 코드를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-149">The assembly cannot contain any security-critical code.</span></span>|  
|<xref:System.Security.SecurityCriticalAttribute>|<span data-ttu-id="ec953-150"><xref:System.Security.SecurityCriticalAttribute.Scope%2A> 속성 없이 어셈블리 수준에서 사용될 경우 기본적으로 어셈블리의 모든 코드를 보안 투명으로 식별하지만 어셈블리에 보안에 중요 코드를 포함할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-150">When used at the assembly level without the <xref:System.Security.SecurityCriticalAttribute.Scope%2A> property, identifies all code in the assembly as security-transparent by default, but indicates that the assembly may contain security-critical code.</span></span><br /><br /> <span data-ttu-id="ec953-151">클래스 수준에서 사용될 경우 클래스 또는 메서드를 보안에 중요로 식별하지만 클래스 멤버는 비와 같이 식별하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-151">When used at the class level, identifies the class or method as security-critical, but not the members of the class.</span></span> <span data-ttu-id="ec953-152">모든 멤버를 보안에 중요로 설정하려면 <xref:System.Security.SecurityCriticalAttribute.Scope%2A> 속성을 <xref:System.Security.SecurityCriticalScope.Everything>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-152">To make all the members security-critical, set the <xref:System.Security.SecurityCriticalAttribute.Scope%2A> property to <xref:System.Security.SecurityCriticalScope.Everything>.</span></span><br /><br /> <span data-ttu-id="ec953-153">멤버 수준에서 사용될 경우 특성은 해당 멤버에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-153">When used at the member level, the attribute applies only to that member.</span></span><br /><br /> <span data-ttu-id="ec953-154">보안에 중요로 식별된 클래스 또는 멤버는 권한 상승을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-154">The class or member identified as security-critical can perform elevations of privilege.</span></span> <span data-ttu-id="ec953-155">**중요:**  수준 1 투명도에서 보안에 중요 한 형식 및 멤버는 어셈블리 외부에서 호출 될 때 보안 안전에 중요로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-155">**Important:**  In level 1 transparency, security-critical types and members are treated as security-safe-critical when they are called from outside the assembly.</span></span> <span data-ttu-id="ec953-156">권한이 없는 권한 상승을 방지하려면 완전 신뢰를 위한 링크 요청을 통해 보안에 중요 형식 및 멤버를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-156">You should protect security-critical types and members with a link demand for full trust to avoid unauthorized elevation of privilege.</span></span>|  
|<xref:System.Security.SecuritySafeCriticalAttribute>|<span data-ttu-id="ec953-157">어셈블리의 보안 투명 코드에서 액세스할 수 있는 보안에 중요 코드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-157">Identifies security-critical code that can be accessed by security-transparent code in the assembly.</span></span> <span data-ttu-id="ec953-158">그러지 않으면 보안 투명 코드가 같은 어셈블리의 private 또는 internal 보안에 중요 멤버에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-158">Otherwise, security-transparent code cannot access private or internal security-critical members in the same assembly.</span></span> <span data-ttu-id="ec953-159">이렇게 하면 보안에 중요 코드에 영향을 미치고 예기치 않은 권한 상승이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-159">Doing so would influence security-critical code and make unexpected elevations of privilege possible.</span></span> <span data-ttu-id="ec953-160">보안 안전에 중요 코드는 엄격한 보안 감사를 통과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-160">Security-safe-critical code should undergo a rigorous security audit.</span></span> <span data-ttu-id="ec953-161">**참고:**  보안 안전에 중요 한 형식 및 멤버는 호출자에 게 보호 된 리소스에 액세스할 수 있는 권한이 있는지 여부를 확인 하기 위해 호출자 권한이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-161">**Note:**  Security-safe-critical types and members must validate the permissions of callers to determine whether the caller has authority to access protected resources.</span></span>|  
  
 <span data-ttu-id="ec953-162"><xref:System.Security.SecuritySafeCriticalAttribute> 특성을 사용하면 보안 투명 코드가 같은 어셈블리의 보안에 중요 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-162">The <xref:System.Security.SecuritySafeCriticalAttribute> attribute enables security-transparent code to access security-critical members in the same assembly.</span></span> <span data-ttu-id="ec953-163">어셈블리에서 보안 투명 및 보안에 중요 코드를 두 어셈블리로 구분하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-163">Consider the security-transparent and security-critical code in your assembly as separated into two assemblies.</span></span> <span data-ttu-id="ec953-164">보안 투명 코드는 보안에 중요 코드의 private 또는 internal 멤버를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-164">The security-transparent code would not be able to see the private or internal members of the security-critical code.</span></span> <span data-ttu-id="ec953-165">또한 일반적으로 보안에 중요 코드는 public 인터페이스에 대한 액세스 권한이 있는지 감사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-165">Additionally, the security-critical code is generally audited for access to its public interface.</span></span> <span data-ttu-id="ec953-166">사용자는 어셈블리 외부에서 private 또는 internal 상태에 액세스할 수 있다고 예상하지 않고 격리된 상태로 유지하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-166">You would not expect a private or internal state to be accessible outside the assembly; you would want to keep the state isolated.</span></span> <span data-ttu-id="ec953-167"><xref:System.Security.SecuritySafeCriticalAttribute> 특성은 필요할 때 격리를 재정의하는 기능을 제공하면서 보안 투명 및 보안에 중요 코드 간의 상태 격리를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-167">The <xref:System.Security.SecuritySafeCriticalAttribute> attribute maintains the isolation of state between security-transparent and security-critical code while providing the ability to override the isolation when it is necessary.</span></span> <span data-ttu-id="ec953-168">보안 투명 코드는 해당 멤버를 <xref:System.Security.SecuritySafeCriticalAttribute>로 표시하지 않으면 private 또는 internal 보안에 중요 코드에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-168">Security-transparent code cannot access private or internal security-critical code unless those members have been marked with <xref:System.Security.SecuritySafeCriticalAttribute>.</span></span> <span data-ttu-id="ec953-169"><xref:System.Security.SecuritySafeCriticalAttribute>를 적용하기 전에 공개적으로 노출된 것처럼 해당 멤버를 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-169">Before applying the <xref:System.Security.SecuritySafeCriticalAttribute>, audit that member as if it were publicly exposed.</span></span>  
  
### <a name="assembly-wide-annotation"></a><span data-ttu-id="ec953-170">어셈블리 수준 주석</span><span class="sxs-lookup"><span data-stu-id="ec953-170">Assembly-wide Annotation</span></span>  
 <span data-ttu-id="ec953-171">다음 표에서는 어셈블리 수준에서 보안 특성을 사용하는 효과에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-171">The following table describes the effects of using security attributes at the assembly level.</span></span>  
  
|<span data-ttu-id="ec953-172">어셈블리 특성</span><span class="sxs-lookup"><span data-stu-id="ec953-172">Assembly attribute</span></span>|<span data-ttu-id="ec953-173">어셈블리 상태</span><span class="sxs-lookup"><span data-stu-id="ec953-173">Assembly state</span></span>|  
|------------------------|--------------------|  
|<span data-ttu-id="ec953-174">부분적으로 신뢰할 수 있는 어셈블리에 대한 특성 없음</span><span class="sxs-lookup"><span data-stu-id="ec953-174">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="ec953-175">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-175">All types and members are transparent.</span></span>|  
|<span data-ttu-id="ec953-176">완전히 신뢰할 수 있는 어셈블리에 대한 특성 없음(전역 어셈블리 캐시에 포함 또는 `AppDomain`에서 완전 신뢰로 식별됨)</span><span class="sxs-lookup"><span data-stu-id="ec953-176">No attribute on a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`)</span></span>|<span data-ttu-id="ec953-177">모든 형식은 투명하고 모든 멤버는 보안 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-177">All types are transparent and all members are security-safe-critical.</span></span>|  
|`SecurityTransparent`|<span data-ttu-id="ec953-178">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-178">All types and members are transparent.</span></span>|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="ec953-179">모든 형식 및 멤버가 보안에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-179">All types and members are security-critical.</span></span>|  
|`SecurityCritical`|<span data-ttu-id="ec953-180">모든 코드가 기본적으로 투명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-180">All code defaults to transparent.</span></span> <span data-ttu-id="ec953-181">그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-181">However, individual types and members can have other attributes.</span></span>|  
  
<a name="security_transparency_examples"></a>
## <a name="security-transparency-examples"></a><span data-ttu-id="ec953-182">보안 투명도 예제</span><span class="sxs-lookup"><span data-stu-id="ec953-182">Security Transparency Examples</span></span>  
 <span data-ttu-id="ec953-183">.NET Framework 2.0 투명도 규칙(수준 1 투명도)을 사용하려면 다음 어셈블리 주석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-183">To use the .NET Framework 2.0 transparency rules (level 1 transparency), use the following assembly annotation:</span></span>  
  
```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 <span data-ttu-id="ec953-184">어셈블리가 중요 코드를 포함하지 않고 권한을 높이지 않음을 나타내도록 전체 어셈블리를 투명하게 설정하려면 다음 특성을 사용하여 어셈블리에 투명도를 명시적으로 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-184">If you want to make a whole assembly transparent to indicate that the assembly does not contain any critical code and does not elevate privileges in any way, you can explicitly add transparency to the assembly with the following attribute:</span></span>  
  
```csharp  
[assembly: SecurityTransparent]  
```  
  
 <span data-ttu-id="ec953-185">같은 어셈블리에서 위험 및 투명 코드를 혼합하려면 먼저 다음과 같이 어셈블리를 <xref:System.Security.SecurityCriticalAttribute> 특성으로 표시하여 어셈블리가 위험 코드를 포함할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-185">If you want to mix critical and transparent code in the same assembly, start by marking the assembly with the <xref:System.Security.SecurityCriticalAttribute> attribute to indicate that the assembly can contain critical code, as follows:</span></span>  
  
```csharp  
[assembly: SecurityCritical]  
```  
  
 <span data-ttu-id="ec953-186">보안에 위험 작업을 수행하려면 다음 코드 예제와 같이 위험 작업을 수행할 코드를 다른 <xref:System.Security.SecurityCriticalAttribute> 특성으로 명시적으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-186">If you want to perform security-critical actions, you must explicitly mark the code that will perform the critical action with another <xref:System.Security.SecurityCriticalAttribute> attribute, as shown in the following code example:</span></span>  
  
```csharp  
[assembly: SecurityCritical]  
public class A  
{  
    [SecurityCritical]  
    private void Critical()  
    {  
        // critical  
    }  
  
    public int SomeProperty  
    {  
        get {/* transparent */ }  
        set {/* transparent */ }  
    }  
}  
public class B  
{
    internal string SomeOtherProperty  
    {  
        get { /* transparent */ }  
        set { /* transparent */ }  
    }  
}  
```  
  
 <span data-ttu-id="ec953-187">명시적으로 보안에 위험으로 표시된 `Critical` 메서드를 제외하고 이전 코드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-187">The previous code is transparent except for the `Critical` method, which is explicitly marked as security-critical.</span></span> <span data-ttu-id="ec953-188">어셈블리 수준 <xref:System.Security.SecurityCriticalAttribute> 특성을 사용해도 투명도는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="ec953-188">Transparency is the default setting, even with the assembly-level <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec953-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec953-189">See also</span></span>

- [<span data-ttu-id="ec953-190">보안 투명 코드, 수준 2</span><span class="sxs-lookup"><span data-stu-id="ec953-190">Security-Transparent Code, Level 2</span></span>](security-transparent-code-level-2.md)
- [<span data-ttu-id="ec953-191">보안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="ec953-191">Security Changes</span></span>](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
