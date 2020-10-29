---
ms.openlocfilehash: c38cb8a6baee7ab16898c7ef449b391664c0dace
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434949"
---
### <a name="most-code-access-security-apis-are-obsolete"></a><span data-ttu-id="e01b2-101">대부분의 코드 액세스 보안 API가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="e01b2-101">Most code access security APIs are obsolete</span></span>

<span data-ttu-id="e01b2-102">.NET의 CAS(코드 액세스 보안) 관련 형식은 대부분 경고로 표시되며 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-102">Most code access security (CAS)-related types in .NET are now obsolete as warning.</span></span> <span data-ttu-id="e01b2-103">여기에는 <xref:System.Security.Permissions.SecurityPermissionAttribute>, CAS 권한 개체(예: <xref:System.Net.SocketPermission>), <xref:System.Security.Policy.EvidenceBase> 파생 형식 및 기타 지원되는 API와 같은 CAX 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-103">This includes CAS attributes, such as <xref:System.Security.Permissions.SecurityPermissionAttribute>, CAS permission objects, such as <xref:System.Net.SocketPermission>, <xref:System.Security.Policy.EvidenceBase>-derived types, and other supporting APIs.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e01b2-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e01b2-104">Change description</span></span>

<span data-ttu-id="e01b2-105">.NET Framework 2.x - 4.x에서 CAS 특성 및 API는 CAS 요청 스택이 성공하거나 실패하도록 하는 등 코드 실행 과정에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-105">In .NET Framework 2.x - 4.x, CAS attributes and APIs can influence the course of code execution, including ensuring that CAS-demand stack walks succeed or fail.</span></span>

```csharp
// In .NET Framework, the attribute causes CAS stack walks
// to terminate successfully when this permission is demanded.
[SocketPermission(SecurityAction.Assert, Host = "contoso.com", Port = "443")]
public void DoSomething()
{
    // open a socket to contoso.com:443
}
```

<span data-ttu-id="e01b2-106">.NET Core 2.x - 3.x에서 런타임은 CAS 특성이나 CAS API를 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-106">In .NET Core 2.x - 3.x, the runtime does not honor CAS attributes or CAS APIs.</span></span> <span data-ttu-id="e01b2-107">런타임은 메서드 항목의 특성을 무시하고 대부분의 프로그래밍 API는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-107">The runtime ignores attributes on method entry, and most programmatic APIs have no effect.</span></span>

```csharp
// The .NET Core runtime ignores the following attribute.
[SocketPermission(SecurityAction.Assert, Host = "contoso.com", Port = "443")]
public void DoSomething()
{
    // open a socket to contoso.com:443
}
```

<span data-ttu-id="e01b2-108">또한 광범위한 API에 대한 프로그래밍 방식 호출(`Assert`)은 항상 성공하지만 제한적 API에 대한 프로그래밍 방식 호출(`Deny`, `PermitOnly`)은 런타임에 항상 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-108">Additionally, programmatic calls to expansive APIs (`Assert`) always succeed, while programmatic calls to restrictive APIs (`Deny`, `PermitOnly`) always throw an exception at run time.</span></span> <span data-ttu-id="e01b2-109">(<xref:System.Security.Permissions.PrincipalPermission>은 이 규칙의 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-109">(<xref:System.Security.Permissions.PrincipalPermission> is an exception to this rule.</span></span> <span data-ttu-id="e01b2-110">아래의 [권장 사항](#cas-action) 섹션을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="e01b2-110">See the [Recommended action](#cas-action) section below.)</span></span>

```csharp
public void DoAssert()
{
    // The line below has no effect at run time.
    new SocketPermission(PermissionState.Unrestricted).Assert();
}

public void DoDeny()
{
    // The line below throws PlatformNotSupportedException at run time.
    new SocketPermission(PermissionState.Unrestricted).Deny();
}
```

<span data-ttu-id="e01b2-111">.NET 5.0 이상 버전에서 대부분의 CAS 관련 API는 더 이상 사용되지 않으며 `SYSLIB0003` 컴파일 시간 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-111">In .NET 5.0 and later versions, most CAS-related APIs are obsolete and produce compile-time warning `SYSLIB0003`.</span></span>

```csharp
[SocketPermission(SecurityAction.Assert, Host = "contoso.com", Port = "443")] // warning SYSLIB0003
public void DoSomething()
{
    new SocketPermission(PermissionState.Unrestricted).Assert(); // warning SYSLIB0003
    new SocketPermission(PermissionState.Unrestricted).Deny(); // warning SYSLIB0003
}
```

<span data-ttu-id="e01b2-112">이는 컴파일 시간 전용 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-112">This is a compile-time only change.</span></span> <span data-ttu-id="e01b2-113">.NET Core의 이전 버전에서 런타임 변경은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-113">There is no run-time change from previous versions of .NET Core.</span></span> <span data-ttu-id="e01b2-114">.NET Core 2.x - 3.x에서 작업을 수행하지 않는 메서드는 .NET 5.0 이상에서도 런타임에 계속 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-114">Methods that perform no operation in .NET Core 2.x - 3.x will continue to perform no operation at run time in .NET 5.0 and later.</span></span> <span data-ttu-id="e01b2-115">.NET Core 2.x - 3.x에서 <xref:System.PlatformNotSupportedException>을 throw하는 메서드는 .NET 5.0 이상에서도 런타임에 <xref:System.PlatformNotSupportedException>을 계속 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-115">Methods that throw <xref:System.PlatformNotSupportedException> in .NET Core 2.x - 3.x will continue to throw a <xref:System.PlatformNotSupportedException> at run time in .NET 5.0 and later.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e01b2-116">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e01b2-116">Reason for change</span></span>

<span data-ttu-id="e01b2-117">[CAS(코드 액세스 보안)](../../../../docs/framework/misc/code-access-security.md)는 지원되지 않는 레거시 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-117">[Code access security (CAS)](../../../../docs/framework/misc/code-access-security.md) is an unsupported legacy technology.</span></span> <span data-ttu-id="e01b2-118">CAS를 사용하도록 설정하는 인프라는 .NET Framework 2.x - 4.x에만 있지만 사용되지 않으며 서비스 또는 보안 수정을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-118">The infrastructure to enable CAS exists only in .NET Framework 2.x - 4.x, but is deprecated and not receiving servicing or security fixes.</span></span>

<span data-ttu-id="e01b2-119">CAS가 사용되지 않기 때문에 [지원 인프라가 .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md) 또는 .NET 5.0+으로 전달되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-119">Due to CAS's deprecation, the [supporting infrastructure was not brought forward to .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md) or .NET 5.0+.</span></span> <span data-ttu-id="e01b2-120">그러나 앱이 .NET Framework 및 .NET Core에 대해 크로스 컴파일을 수행할 수 있도록 API가 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-120">However, the APIs were brought forward so that apps could cross-compile against .NET Framework and .NET Core.</span></span> <span data-ttu-id="e01b2-121">따라서 일부 CAS 관련 API가 존재하고 호출할 수 있지만 런타임에 작업을 수행하지 않는 “열기 실패” 시나리오가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-121">This led to "fail open" scenarios, where some CAS-related APIs exist and are callable but perform no action at run time.</span></span> <span data-ttu-id="e01b2-122">그러면 런타임에서 CAS 관련 특성 또는 프로그래밍 API 호출을 적용하도록 하는 구성 요소에 대한 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-122">This can lead to security issues for components that expect the runtime to honor CAS-related attributes or programmatic API calls.</span></span> <span data-ttu-id="e01b2-123">런타임에서 이러한 특성이나 API를 사용하지 않음을 더욱 잘 전달하기 위해 .NET 5.0에서는 대부분 사용되지 않음으로 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-123">To better communicate that the runtime doesn't respect these attributes or APIs, we have obsoleted the majority of them in .NET 5.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e01b2-124">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e01b2-124">Version introduced</span></span>

<span data-ttu-id="e01b2-125">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="e01b2-125">5.0 RC1</span></span>

#### <a name=""></a><span data-ttu-id="e01b2-126"><a id="cas-action">권장 작업</a></span><span class="sxs-lookup"><span data-stu-id="e01b2-126"><a id="cas-action">Recommended action</a></span></span>

- <span data-ttu-id="e01b2-127">보안 권한을 어설션하려면 사용 권한을 어설션하는 호출이나 특성을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="e01b2-127">If you're asserting any security permission, remove the attribute or call that asserts the permission.</span></span>

  ```csharp
  // REMOVE the attribute below.
  [SecurityPermission(SecurityAction.Assert, ControlThread = true)]
  public void DoSomething()
  {
  }

  public void DoAssert()
  {
      // REMOVE the line below.
      new SecurityPermission(SecurityPermissionFlag.ControlThread).Assert();
  }
  ```

- <span data-ttu-id="e01b2-128">`PermitOnly`를 통해 사용 권한을 거부하거나 제한하려면 보안 관리자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="e01b2-128">If you're denying or restricting (via `PermitOnly`) any permission, contact your security advisor.</span></span> <span data-ttu-id="e01b2-129">CAS 특성은 .NET 5.0+ 런타임에 적용되지 않기 때문에 CAS 인프라를 잘못 사용하여 이러한 메서드에 대한 액세스를 제한하는 경우 애플리케이션에서 보안 허점이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-129">Because CAS attributes are not honored by the .NET 5.0+ runtime, your application could have a security hole if it incorrectly relies on the CAS infrastructure to restrict access to these methods.</span></span>

  ```csharp
  // REVIEW the attribute below; could indicate security vulnerability.
  [SecurityPermission(SecurityAction.Deny, ControlThread = true)]
  public void DoSomething()
  {
  }

  public void DoPermitOnly()
  {
      // REVIEW the line below; could indicate security vulnerability.
      new SecurityPermission(SecurityPermissionFlag.ControlThread).PermitOnly();
  }
  ```

- <span data-ttu-id="e01b2-130"><xref:System.Security.Permissions.PrincipalPermission>을 제외한 모든 사용 권한을 요청하려면 요청을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="e01b2-130">If you're demanding any permission (except <xref:System.Security.Permissions.PrincipalPermission>), remove the demand.</span></span> <span data-ttu-id="e01b2-131">모든 요청은 런타임에 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-131">All demands will succeed at run time.</span></span>

  ```csharp
  // REMOVE the attribute below; it will always succeed.
  [SecurityPermission(SecurityAction.Demand, ControlThread = true)]
  public void DoSomething()
  {
  }

  public void DoDemand()
  {
      // REMOVE the line below; it will always succeed.
      new SecurityPermission(SecurityPermissionFlag.ControlThread).Demand();
  }
  ```

- <span data-ttu-id="e01b2-132"><xref:System.Security.Permissions.PrincipalPermission>을 요청하려면 [PrincipalPermissionAttribute가 오류로 사용되지 않음](../../../../docs/core/compatibility/corefx.md#permission-action)에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e01b2-132">If you're demanding <xref:System.Security.Permissions.PrincipalPermission>, consult the guidance for [PrincipalPermissionAttribute is obsolete as error](../../../../docs/core/compatibility/corefx.md#permission-action).</span></span> <span data-ttu-id="e01b2-133">이 지침은 <xref:System.Security.Permissions.PrincipalPermission>과 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-133">That guidance applies for both <xref:System.Security.Permissions.PrincipalPermission> and <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>

- <span data-ttu-id="e01b2-134">이러한 경고를 반드시 사용하지 않도록 설정해야 하는 경우(권장되지 않음) 코드에서 `SYSLIB0003` 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-134">If you absolutely must disable these warnings (which is not recommended), you can suppress the `SYSLIB0003` warning in code.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0003 // disable the warning
  [SecurityPermission(SecurityAction.Demand, ControlThread = true)]
  #pragma warning restore SYSLIB0003 // re-enable the warning
  public void DoSomething()
  {
  }

  public void DoDemand()
  {
  #pragma warning disable SYSLIB0003 // disable the warning
      new SecurityPermission(SecurityPermissionFlag.ControlThread).Demand();
  #pragma warning restore SYSLIB0003 // re-enable the warning
  }
  ```

  <span data-ttu-id="e01b2-135">프로젝트 파일에서 경고를 표시하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-135">You can also suppress the warning in your project file.</span></span> <span data-ttu-id="e01b2-136">이렇게 하면 프로젝트 내의 모든 소스 파일에 대한 경고를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-136">Doing so disables the warning for all source files within the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0003 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="e01b2-137">`SYSLIB0003`을 표시하지 않으면 CAS 관련 사용되지 않음 경고만 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-137">Suppressing `SYSLIB0003` disables only the CAS-related obsoletion warnings.</span></span> <span data-ttu-id="e01b2-138">다른 경고를 사용하지 않도록 설정하거나 .NET 5.0+ 런타임의 동작을 변경하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01b2-138">It does not disable any other warnings or change the behavior of the .NET 5.0+ runtime.</span></span>

#### <a name="category"></a><span data-ttu-id="e01b2-139">범주</span><span class="sxs-lookup"><span data-stu-id="e01b2-139">Category</span></span>

- <span data-ttu-id="e01b2-140">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="e01b2-140">Core .NET libraries</span></span>
- <span data-ttu-id="e01b2-141">보안</span><span class="sxs-lookup"><span data-stu-id="e01b2-141">Security</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e01b2-142">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e01b2-142">Affected APIs</span></span>

- <xref:System.AppDomain.PermissionSet?displayProperty=fullName>
- <xref:System.Configuration.ConfigurationPermission?displayProperty=fullName>
- <xref:System.Configuration.ConfigurationPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.Common.DBDataPermission?displayProperty=fullName>
- <xref:System.Data.Common.DBDataPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.Odbc.OdbcPermission?displayProperty=fullName>
- <xref:System.Data.Odbc.OdbcPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.OleDb.OleDbPermission?displayProperty=fullName>
- <xref:System.Data.OleDb.OleDbPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.OracleClient.OraclePermission?displayProperty=fullName>
- <xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>
- <xref:System.Data.SqlClient.SqlClientPermission?displayProperty=fullName>
- <xref:System.Data.SqlClient.SqlClientPermissionAttribute?displayProperty=fullName>
- <xref:System.Diagnostics.EventLogPermission?displayProperty=fullName>
- <xref:System.Diagnostics.EventLogPermissionAttribute?displayProperty=fullName>
- <xref:System.Diagnostics.PerformanceCounterPermission?displayProperty=fullName>
- <xref:System.Diagnostics.PerformanceCounterPermissionAttribute?displayProperty=fullName>
- <xref:System.DirectoryServices.DirectoryServicesPermission?displayProperty=fullName>
- <xref:System.DirectoryServices.DirectoryServicesPermissionAttribute?displayProperty=fullName>
- <xref:System.Drawing.Printing.PrintingPermission?displayProperty=fullName>
- <xref:System.Drawing.Printing.PrintingPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.DnsPermission?displayProperty=fullName>
- <xref:System.Net.DnsPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.Mail.SmtpPermission?displayProperty=fullName>
- <xref:System.Net.Mail.SmtpPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.NetworkInformation.NetworkInformationPermission?displayProperty=fullName>
- <xref:System.Net.NetworkInformation.NetworkInformationPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermission?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.PnrpPermission?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.PnrpPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.SocketPermission?displayProperty=fullName>
- <xref:System.Net.SocketPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.WebPermission?displayProperty=fullName>
- <xref:System.Net.WebPermissionAttribute?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.AllowReversePInvokeCallsAttribute?displayProperty=fullName>
- <xref:System.Security.CodeAccessPermission?displayProperty=fullName>
- <xref:System.Security.HostProtectionException?displayProperty=fullName>
- <xref:System.Security.IPermission?displayProperty=fullName>
- <xref:System.Security.IStackWalk?displayProperty=fullName>
- <xref:System.Security.NamedPermissionSet?displayProperty=fullName>
- <xref:System.Security.PermissionSet?displayProperty=fullName>
- <xref:System.Security.Permissions.CodeAccessSecurityAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.GacIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.GacIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.HostProtectionResource?displayProperty=fullName>
- <xref:System.Security.Permissions.IUnrestrictedPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageContainment?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageFilePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageFilePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStoragePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStoragePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntry?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntryCollection?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntryEnumerator?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionAudio?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionImage?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionVideo?displayProperty=fullName>
- <xref:System.Security.Permissions.PermissionSetAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.PermissionState?displayProperty=fullName>
- <xref:System.Security.Permissions.PrincipalPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.PublisherIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.PublisherIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ResourcePermissionBase?displayProperty=fullName>
- <xref:System.Security.Permissions.ResourcePermissionBaseEntry?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermissionFlag?displayProperty=fullName>
- <xref:System.Security.Permissions.SiteIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.SiteIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNameIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNamePublicKeyBlob?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionClipboard?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionWindow?displayProperty=fullName>
- <xref:System.Security.Permissions.UrlIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.UrlIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermissionLevel?displayProperty=fullName>
- <xref:System.Security.Permissions.ZoneIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.ZoneIdentityPermissionAttribute?displayProperty=fullName>
- [<span data-ttu-id="e01b2-143">System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable\<StrongName>)</span><span class="sxs-lookup"><span data-stu-id="e01b2-143">System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable\<StrongName>)</span></span>](/dotnet/api/system.security.policy.applicationtrust.-ctor#System_Security_Policy_ApplicationTrust__ctor_System_Security_PermissionSet_System_Collections_Generic_IEnumerable_System_Security_Policy_StrongName__)
- <xref:System.Security.Policy.ApplicationTrust.FullTrustAssemblies?displayProperty=fullName>
- <xref:System.Security.Policy.FileCodeGroup?displayProperty=fullName>
- <xref:System.Security.Policy.GacInstalled?displayProperty=fullName>
- <xref:System.Security.Policy.IIdentityPermissionFactory?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.AddNamedPermissionSet(System.Security.NamedPermissionSet)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.ChangeNamedPermissionSet(System.String,System.Security.PermissionSet)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.GetNamedPermissionSet(System.String)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.RemoveNamedPermissionSet%2A?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyStatement.PermissionSet?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyStatement.%23ctor%2A?displayProperty=fullName>
- <xref:System.Security.Policy.Publisher?displayProperty=fullName>
- <xref:System.Security.Policy.Site?displayProperty=fullName>
- <xref:System.Security.Policy.StrongName?displayProperty=fullName>
- <xref:System.Security.Policy.StrongNameMembershipCondition?displayProperty=fullName>
- <xref:System.Security.Policy.Url?displayProperty=fullName>
- <xref:System.Security.Policy.Zone?displayProperty=fullName>
- <xref:System.Security.SecurityManager?displayProperty=fullName>
- <xref:System.ServiceProcess.ServiceControllerPermission?displayProperty=fullName>
- <xref:System.ServiceProcess.ServiceControllerPermissionAttribute?displayProperty=fullName>
- <xref:System.Transactions.DistributedTransactionPermission?displayProperty=fullName>
- <xref:System.Transactions.DistributedTransactionPermissionAttribute?displayProperty=fullName>
- <xref:System.Web.AspNetHostingPermission?displayProperty=fullName>
- <xref:System.Web.AspNetHostingPermissionAttribute?displayProperty=fullName>
- <xref:System.Xaml.Permissions.XamlLoadPermission?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.AppDomain.PermissionSet`
- `T:System.Configuration.ConfigurationPermission`
- `T:System.Configuration.ConfigurationPermissionAttribute`
- `T:System.Data.Common.DBDataPermission`
- `T:System.Data.Common.DBDataPermissionAttribute`
- `T:System.Data.Odbc.OdbcPermission`
- `T:System.Data.Odbc.OdbcPermissionAttribute`
- `T:System.Data.OleDb.OleDbPermission`
- `T:System.Data.OleDb.OleDbPermissionAttribute`
- `T:System.Data.OracleClient.OraclePermission`
- `T:System.Data.OracleClient.OraclePermissionAttribute`
- `T:System.Data.SqlClient.SqlClientPermission`
- `T:System.Data.SqlClient.SqlClientPermissionAttribute`
- `T:System.Diagnostics.EventLogPermission`
- `T:System.Diagnostics.EventLogPermissionAttribute`
- `T:System.Diagnostics.PerformanceCounterPermission`
- `T:System.Diagnostics.PerformanceCounterPermissionAttribute`
- `T:System.DirectoryServices.DirectoryServicesPermission`
- `T:System.DirectoryServices.DirectoryServicesPermissionAttribute`
- `T:System.Drawing.Printing.PrintingPermission`
- `T:System.Drawing.Printing.PrintingPermissionAttribute`
- `T:System.Net.DnsPermission`
- `T:System.Net.DnsPermissionAttribute`
- `T:System.Net.Mail.SmtpPermission`
- `T:System.Net.Mail.SmtpPermissionAttribute`
- `T:System.Net.NetworkInformation.NetworkInformationPermission`
- `T:System.Net.NetworkInformation.NetworkInformationPermissionAttribute`
- `T:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermission`
- `T:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermissionAttribute`
- `T:System.Net.PeerToPeer.PnrpPermission`
- `T:System.Net.PeerToPeer.PnrpPermissionAttribute`
- `T:System.Net.SocketPermission`
- `T:System.Net.SocketPermissionAttribute`
- `T:System.Net.WebPermission`
- `T:System.Net.WebPermissionAttribute`
- `T:System.Runtime.InteropServices.AllowReversePInvokeCallsAttribute`
- `T:System.Security.CodeAccessPermission`
- `T:System.Security.HostProtectionException`
- `T:System.Security.IPermission`
- `T:System.Security.IStackWalk`
- `T:System.Security.NamedPermissionSet`
- `T:System.Security.PermissionSet`
- `T:System.Security.Permissions.CodeAccessSecurityAttribute`
- `T:System.Security.Permissions.DataProtectionPermission`
- `T:System.Security.Permissions.DataProtectionPermissionAttribute`
- `T:System.Security.Permissions.DataProtectionPermissionFlags`
- `T:System.Security.Permissions.EnvironmentPermission`
- `T:System.Security.Permissions.EnvironmentPermissionAccess`
- `T:System.Security.Permissions.EnvironmentPermissionAttribute`
- `T:System.Security.Permissions.FileDialogPermission`
- `T:System.Security.Permissions.FileDialogPermissionAccess`
- `T:System.Security.Permissions.FileDialogPermissionAttribute`
- `T:System.Security.Permissions.FileIOPermission`
- `T:System.Security.Permissions.FileIOPermissionAccess`
- `T:System.Security.Permissions.FileIOPermissionAttribute`
- `T:System.Security.Permissions.GacIdentityPermission`
- `T:System.Security.Permissions.GacIdentityPermissionAttribute`
- `T:System.Security.Permissions.HostProtectionAttribute`
- `T:System.Security.Permissions.HostProtectionResource`
- `T:System.Security.Permissions.IUnrestrictedPermission`
- `T:System.Security.Permissions.IsolatedStorageContainment`
- `T:System.Security.Permissions.IsolatedStorageFilePermission`
- `T:System.Security.Permissions.IsolatedStorageFilePermissionAttribute`
- `T:System.Security.Permissions.IsolatedStoragePermission`
- `T:System.Security.Permissions.IsolatedStoragePermissionAttribute`
- `T:System.Security.Permissions.KeyContainerPermission`
- `T:System.Security.Permissions.KeyContainerPermissionAccessEntry`
- `T:System.Security.Permissions.KeyContainerPermissionAccessEntryCollection`
- `T:System.Security.Permissions.KeyContainerPermissionAccessEntryEnumerator`
- `T:System.Security.Permissions.KeyContainerPermissionAttribute`
- `T:System.Security.Permissions.KeyContainerPermissionFlags`
- `T:System.Security.Permissions.MediaPermission`
- `T:System.Security.Permissions.MediaPermissionAttribute`
- `T:System.Security.Permissions.MediaPermissionAudio`
- `T:System.Security.Permissions.MediaPermissionImage`
- `T:System.Security.Permissions.MediaPermissionVideo`
- `T:System.Security.Permissions.PermissionSetAttribute`
- `T:System.Security.Permissions.PermissionState`
- `T:System.Security.Permissions.PrincipalPermission`
- `T:System.Security.Permissions.PrincipalPermissionAttribute`
- `T:System.Security.Permissions.PublisherIdentityPermission`
- `T:System.Security.Permissions.PublisherIdentityPermissionAttribute`
- `T:System.Security.Permissions.ReflectionPermission`
- `T:System.Security.Permissions.ReflectionPermissionAttribute`
- `T:System.Security.Permissions.ReflectionPermissionFlag`
- `T:System.Security.Permissions.RegistryPermission`
- `T:System.Security.Permissions.RegistryPermissionAccess`
- `T:System.Security.Permissions.RegistryPermissionAttribute`
- `T:System.Security.Permissions.ResourcePermissionBase`
- `T:System.Security.Permissions.ResourcePermissionBaseEntry`
- `T:System.Security.Permissions.SecurityAction`
- `T:System.Security.Permissions.SecurityAttribute`
- `T:System.Security.Permissions.SecurityPermission`
- `T:System.Security.Permissions.SecurityPermissionAttribute`
- `T:System.Security.Permissions.SecurityPermissionFlag`
- `T:System.Security.Permissions.SiteIdentityPermission`
- `T:System.Security.Permissions.SiteIdentityPermissionAttribute`
- `T:System.Security.Permissions.StorePermission`
- `T:System.Security.Permissions.StorePermissionAttribute`
- `T:System.Security.Permissions.StorePermissionFlags`
- `T:System.Security.Permissions.StrongNameIdentityPermission`
- `T:System.Security.Permissions.StrongNameIdentityPermissionAttribute`
- `T:System.Security.Permissions.StrongNamePublicKeyBlob`
- `T:System.Security.Permissions.TypeDescriptorPermission`
- `T:System.Security.Permissions.TypeDescriptorPermissionAttribute`
- `T:System.Security.Permissions.TypeDescriptorPermissionFlags`
- `T:System.Security.Permissions.UIPermission`
- `T:System.Security.Permissions.UIPermissionAttribute`
- `T:System.Security.Permissions.UIPermissionClipboard`
- `T:System.Security.Permissions.UIPermissionWindow`
- `T:System.Security.Permissions.UrlIdentityPermission`
- `T:System.Security.Permissions.UrlIdentityPermissionAttribute`
- `T:System.Security.Permissions.WebBrowserPermission`
- `T:System.Security.Permissions.WebBrowserPermissionAttribute`
- `T:System.Security.Permissions.WebBrowserPermissionLevel`
- `T:System.Security.Permissions.ZoneIdentityPermission`
- `T:System.Security.Permissions.ZoneIdentityPermissionAttribute`
- `M:`System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable<StrongName>)`
- `P:System.Security.Policy.ApplicationTrust.FullTrustAssemblies`
- `T:System.Security.Policy.FileCodeGroup`
- `T:System.Security.Policy.GacInstalled`
- `T:System.Security.Policy.IIdentityPermissionFactory`
- `M:System.Security.Policy.PolicyLevel.AddNamedPermissionSet(System.Security.NamedPermissionSet)`
- `M:System.Security.Policy.PolicyLevel.ChangeNamedPermissionSet(System.String,System.Security.PermissionSet)`
- `M:System.Security.Policy.PolicyLevel.GetNamedPermissionSet(System.String)`
- `Overload:System.Security.Policy.PolicyLevel.RemoveNamedPermissionSet`
- `T:System.Security.Policy.PolicyStatement.PermissionSet`
- `Overload:System.Security.Policy.PolicyStatement.#ctor`
- `T:System.Security.Policy.Publisher`
- `T:System.Security.Policy.Site`
- `T:System.Security.Policy.StrongName`
- `T:System.Security.Policy.StrongNameMembershipCondition`
- `T:System.Security.Policy.Url`
- `T:System.Security.Policy.Zone`
- `T:System.Security.SecurityManager`
- `T:System.ServiceProcess.ServiceControllerPermission`
- `T:System.ServiceProcess.ServiceControllerPermissionAttribute`
- `T:System.Transactions.DistributedTransactionPermission`
- `T:System.Transactions.DistributedTransactionPermissionAttribute`
- `T:System.Web.AspNetHostingPermission`
- `T:System.Web.AspNetHostingPermissionAttribute`
- `T:System.Xaml.Permissions.XamlLoadPermission`

-->
