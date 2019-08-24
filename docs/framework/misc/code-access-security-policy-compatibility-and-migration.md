---
title: 코드 액세스 보안 정책 호환성 및 마이그레이션
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15e693f716d02e6f7ef8b666ddf51a8bd352f642
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690288"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="812b6-102">코드 액세스 보안 정책 호환성 및 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="812b6-102">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="812b6-103">정책에 대 한 부분의 코드 액세스 보안 (CA)는.NET Framework 4에서는 사용 되지 않는 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-103">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="812b6-104">결과적으로 발생할 수 컴파일 경고 및 런타임 예외 사용 되지 않는 정책 형식과 멤버를 호출 하는 경우 [명시적](#explicit_use) 하거나 [암시적으로](#implicit_use) (을 통해 다른 형식 및 멤버).</span><span class="sxs-lookup"><span data-stu-id="812b6-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="812b6-105">다음 중 하나를 수행하여 경고와 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-105">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="812b6-106">[마이그레이션](#migration) 사용 되지 않는 호출에 대 한.NET Framework 4 대체 항목으로 마이그레이션되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-106">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="812b6-107">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="812b6-107">\- or -</span></span>

- <span data-ttu-id="812b6-108">사용 하 여 [ \<NetFx40_LegacySecurityPolicy > 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 레거시 CAS 정책은 동작을 옵트인 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-108">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="812b6-109">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-109">This topic contains the following sections:</span></span>

- [<span data-ttu-id="812b6-110">명시적으로 사용</span><span class="sxs-lookup"><span data-stu-id="812b6-110">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="812b6-111">암시적 사용</span><span class="sxs-lookup"><span data-stu-id="812b6-111">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="812b6-112">오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="812b6-112">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="812b6-113">마이그레이션: 사용 되지 않는 호출에 대 한 대체</span><span class="sxs-lookup"><span data-stu-id="812b6-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="812b6-114">호환성: CAS 정책 레거시 옵션을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="812b6-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="812b6-115">명시적 사용</span><span class="sxs-lookup"><span data-stu-id="812b6-115">Explicit Use</span></span>

<span data-ttu-id="812b6-116">보안 정책을 직접 조작하거나 샌드박싱에 CAS 정책이 필요한 멤버는 사용되지 않으며 기본적으로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="812b6-117">다음은 이러한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-117">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="812b6-118">암시적 사용</span><span class="sxs-lookup"><span data-stu-id="812b6-118">Implicit Use</span></span>

<span data-ttu-id="812b6-119">어셈블리 로드 오버로드가 여러 개이면 CAS 정책의 암시적 사용 때문에 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="812b6-120">이러한 오버로드는 CAS 정책을 확인하고 어셈블리에 대한 권한 부여 집합을 제공하는 데 사용되는 <xref:System.Security.Policy.Evidence> 매개 변수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="812b6-121">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-121">Here are some examples.</span></span> <span data-ttu-id="812b6-122">사용되지 않는 오버로드는 <xref:System.Security.Policy.Evidence>를 매개 변수로 받는 오버로드입니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="812b6-123">오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="812b6-123">Errors and Warnings</span></span>

<span data-ttu-id="812b6-124">사용되지 않는 형식과 멤버를 사용할 경우 다음과 같은 오류 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="812b6-125"><xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 형식 자체는 사용이 중단되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="812b6-126">컴파일 타임 경고:</span><span class="sxs-lookup"><span data-stu-id="812b6-126">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="812b6-127">런타임 예외:</span><span class="sxs-lookup"><span data-stu-id="812b6-127">Run-time exception:</span></span>

<span data-ttu-id="812b6-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="812b6-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="812b6-129">마이그레이션: 사용 되지 않는 호출에 대 한 대체</span><span class="sxs-lookup"><span data-stu-id="812b6-129">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="812b6-130">어셈블리의 신뢰 수준 결정</span><span class="sxs-lookup"><span data-stu-id="812b6-130">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="812b6-131">CAS 정책은 대체로 어셈블리 또는 애플리케이션 도메인의 권한 부여 집합이나 신뢰 수준을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="812b6-132">.NET Framework 4는 보안 정책을 확인 하는 필요 하지 않은 다음과 같은 유용한 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-132">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="812b6-133">애플리케이션 도메인 샌드박싱</span><span class="sxs-lookup"><span data-stu-id="812b6-133">Application Domain Sandboxing</span></span>

<span data-ttu-id="812b6-134"><xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> 메서드는 일반적으로 애플리케이션 도메인에 어셈블리를 샌드박싱하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="812b6-135">.NET Framework 4를 사용 하지 않은 멤버를 노출 <xref:System.Security.Policy.PolicyLevel> 이 목적입니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-135">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="812b6-136">자세한 내용은 [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)의 설명대로 신뢰할 수 없는 코드에 별도의 폴더를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="812b6-137">부분적으로 신뢰할 수 있는 코드에 대한 안전하거나 적절한 권한 집합 결정</span><span class="sxs-lookup"><span data-stu-id="812b6-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="812b6-138">호스트가 호스트된 코드를 샌드박싱하는 데 적절한 권한을 결정해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="812b6-139">.NET Framework 4 이전 CAS 정책을 사용 하 여이 작업을 수행 하는 방법을 제공 되는 <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="812b6-139">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="812b6-140">.NET Framework 4는 대신, 다음을 제공 합니다.는 <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> 안전 하 고 표준 권한 집합 제공된 된 증명 정보를 반환 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="812b6-140">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="812b6-141">비 샌드 박싱 시나리오: 어셈블리 로드 오버 로드</span><span class="sxs-lookup"><span data-stu-id="812b6-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="812b6-142">어셈블리 로드 오버로드를 사용하는 이유는 어셈블리를 샌드박싱하는 대신 달리 사용할 수 없는 매개 변수를 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="812b6-143">.NET Framework 4부터 어셈블리 로드 오버 로드 하지 않아도 되는 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 개체를 매개 변수로 <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>,이 시나리오를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-143">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="812b6-144">어셈블리를 샌드박싱하려는 경우 <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="812b6-145">호환성: CAS 정책 레거시 옵션을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="812b6-145">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="812b6-146">합니다 [ \<NetFx40_LegacySecurityPolicy > 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 프로세스나 라이브러리에서 레거시 CAS 정책을 사용 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-146">The [\<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="812b6-147">이 요소를 사용하도록 설정하면 정책 및 증거 오버로드가 이전 버전의 프레임워크와 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="812b6-148">CAS 정책 동작은 런타임 버전별로 지정되므로 특정 런타임 버전에 대해 CAS 정책을 수정해도 다른 버전의 CAS 정책에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="812b6-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="812b6-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="812b6-149">See also</span></span>

- [<span data-ttu-id="812b6-150">방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행</span><span class="sxs-lookup"><span data-stu-id="812b6-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="812b6-151">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="812b6-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
