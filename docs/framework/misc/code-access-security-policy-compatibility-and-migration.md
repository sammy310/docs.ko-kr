---
title: 코드 액세스 보안 정책 호환성 및 마이그레이션
description: 요약을 읽고 .NET 4에서 코드 액세스 보안 정책 호환성 및 마이그레이션에 대 한 링크를 참조 하세요.
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: e5affd9d16635fa28342b5b7390a083185975f2b
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281734"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="2c881-103">코드 액세스 보안 정책 호환성 및 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2c881-103">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="2c881-104">CAS (코드 액세스 보안)의 정책 부분은 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-104">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="2c881-105">따라서 사용 되지 않는 정책 형식 및 멤버를 [명시적](#explicit_use) 또는 [암시적](#implicit_use) 으로 (다른 형식 및 멤버를 통해) 호출 하는 경우 컴파일 경고 및 런타임 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-105">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="2c881-106">다음 중 하나를 수행하여 경고와 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-106">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="2c881-107">사용 되지 않는 호출에 대 한 .NET Framework 4 대체 항목으로 [마이그레이션](#migration)</span><span class="sxs-lookup"><span data-stu-id="2c881-107">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="2c881-108">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="2c881-108">\- or -</span></span>

- <span data-ttu-id="2c881-109">[ \<NetFx40_LegacySecurityPolicy> 구성 요소](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 를 사용 하 여 레거시 CAS 정책 동작을 옵트인 (opt in) 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-109">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="2c881-110">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-110">This topic contains the following sections:</span></span>

- [<span data-ttu-id="2c881-111">명시적 사용</span><span class="sxs-lookup"><span data-stu-id="2c881-111">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="2c881-112">암시적 사용</span><span class="sxs-lookup"><span data-stu-id="2c881-112">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="2c881-113">오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="2c881-113">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="2c881-114">마이그레이션: 사용되지 않는 호출에 대한 대체 항목</span><span class="sxs-lookup"><span data-stu-id="2c881-114">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="2c881-115">호환성: CAS 정책 레거시 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="2c881-115">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="2c881-116">명시적 사용</span><span class="sxs-lookup"><span data-stu-id="2c881-116">Explicit Use</span></span>

<span data-ttu-id="2c881-117">보안 정책을 직접 조작하거나 샌드박싱에 CAS 정책이 필요한 멤버는 사용되지 않으며 기본적으로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-117">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="2c881-118">이벤트의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-118">Examples of these are:</span></span>

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

## <a name="implicit-use"></a><span data-ttu-id="2c881-119">암시적 사용</span><span class="sxs-lookup"><span data-stu-id="2c881-119">Implicit Use</span></span>

<span data-ttu-id="2c881-120">어셈블리 로드 오버로드가 여러 개이면 CAS 정책의 암시적 사용 때문에 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-120">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="2c881-121">이러한 오버로드는 CAS 정책을 확인하고 어셈블리에 대한 권한 부여 집합을 제공하는 데 사용되는 <xref:System.Security.Policy.Evidence> 매개 변수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-121">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="2c881-122">다음은 몇 가지 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-122">Here are some examples.</span></span> <span data-ttu-id="2c881-123">사용되지 않는 오버로드는 <xref:System.Security.Policy.Evidence>를 매개 변수로 받는 오버로드입니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-123">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

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

## <a name="errors-and-warnings"></a><span data-ttu-id="2c881-124">오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="2c881-124">Errors and Warnings</span></span>

<span data-ttu-id="2c881-125">사용되지 않는 형식과 멤버를 사용할 경우 다음과 같은 오류 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-125">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="2c881-126"><xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 형식 자체는 사용이 중단되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-126">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="2c881-127">컴파일 타임 경고:</span><span class="sxs-lookup"><span data-stu-id="2c881-127">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="2c881-128">런타임 예외:</span><span class="sxs-lookup"><span data-stu-id="2c881-128">Run-time exception:</span></span>

<span data-ttu-id="2c881-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="2c881-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="2c881-130">마이그레이션: 사용되지 않는 호출에 대한 대체 항목</span><span class="sxs-lookup"><span data-stu-id="2c881-130">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="2c881-131">어셈블리의 신뢰 수준 결정</span><span class="sxs-lookup"><span data-stu-id="2c881-131">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="2c881-132">CAS 정책은 대체로 어셈블리 또는 애플리케이션 도메인의 권한 부여 집합이나 신뢰 수준을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-132">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="2c881-133">.NET Framework 4는 보안 정책을 해결 하지 않아도 되는 다음과 같은 유용한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-133">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="2c881-134">애플리케이션 도메인 샌드박싱</span><span class="sxs-lookup"><span data-stu-id="2c881-134">Application Domain Sandboxing</span></span>

<span data-ttu-id="2c881-135"><xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> 메서드는 일반적으로 애플리케이션 도메인에 어셈블리를 샌드박싱하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-135">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="2c881-136">.NET Framework 4는이 용도로 사용할 필요가 없는 멤버를 노출 <xref:System.Security.Policy.PolicyLevel> 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-136">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="2c881-137">자세한 내용은 [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](how-to-run-partially-trusted-code-in-a-sandbox.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c881-137">For more information, see [How to: Run Partially Trusted Code in a Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="2c881-138">부분적으로 신뢰할 수 있는 코드에 대한 안전하거나 적절한 권한 집합 결정</span><span class="sxs-lookup"><span data-stu-id="2c881-138">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="2c881-139">호스트가 호스트된 코드를 샌드박싱하는 데 적절한 권한을 결정해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-139">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="2c881-140">.NET Framework 4 이전에는 CAS 정책에서 메서드를 사용 하 여이 작업을 수행 하는 방법을 제공 <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-140">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2c881-141">대체로 .NET Framework 4는 <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> 제공 된 증명 정보에 대 한 안전한 표준 권한 집합을 반환 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-141">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="2c881-142">비샌드박싱 시나리오: 어셈블리 로드 오버로드</span><span class="sxs-lookup"><span data-stu-id="2c881-142">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="2c881-143">어셈블리 로드 오버로드를 사용하는 이유는 어셈블리를 샌드박싱하는 대신 달리 사용할 수 없는 매개 변수를 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-143">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="2c881-144">.NET Framework 4부터 매개 변수로 개체를 요구 하지 않는 어셈블리 로드 오버 로드 ( <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 예:)를 <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType> 사용 하면이 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-144">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="2c881-145">어셈블리를 샌드박싱하려는 경우 <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-145">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="2c881-146">호환성: CAS 정책 레거시 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="2c881-146">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="2c881-147">[ \<NetFx40_LegacySecurityPolicy> 구성 요소](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 를 사용 하 여 프로세스나 라이브러리가 레거시 CAS 정책을 사용 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-147">The [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="2c881-148">이 요소를 사용하도록 설정하면 정책 및 증거 오버로드가 이전 버전의 프레임워크와 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-148">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="2c881-149">CAS 정책 동작은 런타임 버전별로 지정되므로 특정 런타임 버전에 대해 CAS 정책을 수정해도 다른 버전의 CAS 정책에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-149">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2c881-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c881-150">See also</span></span>

- [<span data-ttu-id="2c881-151">방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행</span><span class="sxs-lookup"><span data-stu-id="2c881-151">How to: Run Partially Trusted Code in a Sandbox</span></span>](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="2c881-152">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="2c881-152">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
