---
title: '호환성이 손상되는 변경: 기본이 아닌 진단 ID를 사용하는 API 사용되지 않음'
description: 일부 API가 사용자 지정 진단 ID를 사용하여 사용되지 않음으로 표시된 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 9bd7ce18aed38955f9abc91e0c8b09e827c401d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759929"
---
# <a name="api-obsoletions-with-non-default-diagnostic-ids"></a><span data-ttu-id="d978b-103">기본이 아닌 진단 ID를 사용하는 API 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="d978b-103">API obsoletions with non-default diagnostic IDs</span></span>

<span data-ttu-id="d978b-104">일부 API는 .NET 5.0부터 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-104">Some APIs have been marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="d978b-105">이러한 호환성이 손상되는 변경은 ‘사용자 지정 진단 ID’를 사용하여 사용되지 않는 것으로 표시된 API에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-105">This breaking change is specific to APIs that have been marked as obsolete *with a custom diagnostic ID*.</span></span> <span data-ttu-id="d978b-106">C# 컴파일러에 대한 기본 사용되지 않음 진단 ID인 [CS0618](../../../../csharp/language-reference/compiler-messages/cs0618.md)을 표시하지 않아도 이러한 API를 사용할 때 컴파일러에서 생성되는 경고는 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-106">Suppressing the default obsoletion diagnostic ID, which is [CS0618](../../../../csharp/language-reference/compiler-messages/cs0618.md) for the C# compiler, does not suppress the warnings that the compiler generates when these APIs are used.</span></span>

## <a name="change-description"></a><span data-ttu-id="d978b-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d978b-107">Change description</span></span>

<span data-ttu-id="d978b-108">이전 .NET 버전에서는 빌드 경고 없이 이러한 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-108">In previous .NET versions, these APIs can be used without any build warning.</span></span> <span data-ttu-id="d978b-109">.NET 5.0 이상 버전에서 이러한 API를 사용하면 사용자 지정 진단 ID를 사용하는 컴파일 시간 경고 또는 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-109">In .NET 5.0 and later versions, use of these APIS produces a compile-time warning or error with a custom diagnostic ID.</span></span> <span data-ttu-id="d978b-110">사용자 지정 진단 ID를 사용하면 모든 사용되지 않음 경고를 완전히 표시하지 않는 대신 사용되지 않음 경고를 개별적으로 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-110">The use of custom diagnostic IDs allows you to suppress the obsoletion warnings individually instead of blanket-suppressing all obsoletion warnings.</span></span>

<span data-ttu-id="d978b-111">다음 표에는 사용되지 않는 API에 대한 사용자 지정 진단 ID와 해당 경고 메시지가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-111">The following table lists the custom diagnostic IDs and their corresponding warning messages for obsoleted APIs.</span></span>

| <span data-ttu-id="d978b-112">진단 ID</span><span class="sxs-lookup"><span data-stu-id="d978b-112">Diagnostic ID</span></span> | <span data-ttu-id="d978b-113">Description</span><span class="sxs-lookup"><span data-stu-id="d978b-113">Description</span></span> | <span data-ttu-id="d978b-114">심각도</span><span class="sxs-lookup"><span data-stu-id="d978b-114">Severity</span></span> |
| - | - |
| `SYSLIB0001` | <span data-ttu-id="d978b-115">UTF-7 인코딩은 안전하지 않으므로 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-115">The UTF-7 encoding is insecure and should not be used.</span></span> <span data-ttu-id="d978b-116">대신 UTF-8을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d978b-116">Consider using UTF-8 instead.</span></span> | <span data-ttu-id="d978b-117">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-117">Warning</span></span> |
| `SYSLIB0002` | <span data-ttu-id="d978b-118"><xref:System.Security.Permissions.PrincipalPermissionAttribute>는 런타임에 적용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-118"><xref:System.Security.Permissions.PrincipalPermissionAttribute> is not honored by the runtime and must not be used.</span></span> | <span data-ttu-id="d978b-119">Error</span><span class="sxs-lookup"><span data-stu-id="d978b-119">Error</span></span> |
| `SYSLIB0003` | <span data-ttu-id="d978b-120">CAS(코드 액세스 보안)가 런타임에 지원되거나 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-120">Code access security (CAS) is not supported or honored by the runtime.</span></span> | <span data-ttu-id="d978b-121">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-121">Warning</span></span> |
| `SYSLIB0004` | <span data-ttu-id="d978b-122">CER(제약이 있는 실행 영역) 기능이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-122">The constrained execution region (CER) feature is not supported.</span></span> | <span data-ttu-id="d978b-123">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-123">Warning</span></span> |
| `SYSLIB0005` | <span data-ttu-id="d978b-124">GAC(전역 어셈블리 캐시)가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-124">The global assembly cache (GAC) is not supported.</span></span> | <span data-ttu-id="d978b-125">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-125">Warning</span></span> |
| `SYSLIB0006` | <span data-ttu-id="d978b-126"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType>이 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-126"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> | <span data-ttu-id="d978b-127">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-127">Warning</span></span> |
| `SYSLIB0007` | <span data-ttu-id="d978b-128">이 암호화 알고리즘의 기본 구현이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-128">The default implementation of this cryptography algorithm is not supported.</span></span> | <span data-ttu-id="d978b-129">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-129">Warning</span></span> |
| `SYSLIB0008` | <span data-ttu-id="d978b-130"><xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-130">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> | <span data-ttu-id="d978b-131">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-131">Warning</span></span> |
| `SYSLIB0009` | <span data-ttu-id="d978b-132"><xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> 및 <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> 메서드가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-132">The <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> and <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> methods are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> | <span data-ttu-id="d978b-133">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-133">Warning</span></span> |
| `SYSLIB0010`| <span data-ttu-id="d978b-134">일부 원격 API가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-134">Some remoting APIs are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> | <span data-ttu-id="d978b-135">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-135">Warning</span></span> |
| `SYSLIB0011` | <span data-ttu-id="d978b-136"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization이 사용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-136"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is obsolete and should not be used.</span></span> | <span data-ttu-id="d978b-137">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-137">Warning</span></span> |
| `SYSLIB0012` | <span data-ttu-id="d978b-138"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> 및 <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>은 .NET Framework 호환성을 위해서만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-138"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> and <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> are only included for .NET Framework compatibility.</span></span> <span data-ttu-id="d978b-139">대신 <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d978b-139">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span> | <span data-ttu-id="d978b-140">경고</span><span class="sxs-lookup"><span data-stu-id="d978b-140">Warning</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="d978b-141">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d978b-141">Version introduced</span></span>

<span data-ttu-id="d978b-142">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d978b-142">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d978b-143">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d978b-143">Recommended action</span></span>

- <span data-ttu-id="d978b-144">경고에 제공된 URL 링크를 사용하여 각 진단 ID에 대해 제공된 특정 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d978b-144">Follow the specific guidance provided for the each diagnostic ID using the URL link provided on the warning.</span></span>

- <span data-ttu-id="d978b-145">이러한 사용되지 않음에 대한 경고나 오류는 사용되지 않는 형식이나 멤버에 대한 표준 진단 ID를 사용하여 표시하지 않을 수 없으며, 사용자 지정 `SYSLIBxxxx` 진단 ID 값을 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d978b-145">Warnings or errors for these obsoletions can't be suppressed using the standard diagnostic ID for obsolete types or members; use the custom `SYSLIBxxxx` diagnostic ID value instead.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d978b-146">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d978b-146">Affected APIs</span></span>

### <a name="syslib0001"></a><span data-ttu-id="d978b-147">SYSLIB0001</span><span class="sxs-lookup"><span data-stu-id="d978b-147">SYSLIB0001</span></span>

- <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>
- <xref:System.Text.UTF7Encoding.%23ctor%2A>

### <a name="syslib0002"></a><span data-ttu-id="d978b-148">SYSLIB0002</span><span class="sxs-lookup"><span data-stu-id="d978b-148">SYSLIB0002</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute.%23ctor(System.Security.Permissions.SecurityAction)>

### <a name="syslib0003"></a><span data-ttu-id="d978b-149">SYSLIB0003</span><span class="sxs-lookup"><span data-stu-id="d978b-149">SYSLIB0003</span></span>

<span data-ttu-id="d978b-150">`System.Security.Permissions` 네임스페이스의 클래스:</span><span class="sxs-lookup"><span data-stu-id="d978b-150">Classes in the `System.Security.Permissions` namespace:</span></span>

- <xref:System.Security.Permissions.CodeAccessSecurityAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.DataProtectionPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.GacIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.GacIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageFilePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageFilePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStoragePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStoragePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntry?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntryCollection?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAccessEntryEnumerator?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.PermissionSetAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.PrincipalPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.PublisherIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.PublisherIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ResourcePermissionBase?displayProperty=fullName>
- <xref:System.Security.Permissions.ResourcePermissionBaseEntry?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.SiteIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.SiteIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermission?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNameIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.StrongNamePublicKeyBlob?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.UrlIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.UrlIdentityPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermissionAttribute?displayProperty=fullName>
- <xref:System.Security.Permissions.ZoneIdentityPermission?displayProperty=fullName>
- <xref:System.Security.Permissions.ZoneIdentityPermissionAttribute?displayProperty=fullName>

<span data-ttu-id="d978b-151">`CodeAccessSecurityAttribute`에서 파생되는 클래스:</span><span class="sxs-lookup"><span data-stu-id="d978b-151">Classes that derive from `CodeAccessSecurityAttribute`:</span></span>

- <xref:System.Configuration.ConfigurationPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.Common.DBDataPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.Odbc.OdbcPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.OleDb.OleDbPermissionAttribute?displayProperty=fullName>
- <xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>
- <xref:System.Data.SqlClient.SqlClientPermissionAttribute?displayProperty=fullName>
- <xref:System.Diagnostics.EventLogPermissionAttribute?displayProperty=fullName>
- <xref:System.Diagnostics.PerformanceCounterPermissionAttribute?displayProperty=fullName>
- <xref:System.DirectoryServices.DirectoryServicesPermissionAttribute?displayProperty=fullName>
- <xref:System.Drawing.Printing.PrintingPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.DnsPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.SocketPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.WebPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.Mail.SmtpPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.NetworkInformation.NetworkInformationPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.PnrpPermissionAttribute?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermissionAttribute?displayProperty=fullName>
- <xref:System.ServiceProcess.ServiceControllerPermissionAttribute?displayProperty=fullName>
- <xref:System.Transactions.DistributedTransactionPermissionAttribute?displayProperty=fullName>
- <xref:System.Web.AspNetHostingPermissionAttribute?displayProperty=fullName>

<span data-ttu-id="d978b-152">인터페이스:</span><span class="sxs-lookup"><span data-stu-id="d978b-152">Interfaces:</span></span>

- <xref:System.Security.Permissions.IUnrestrictedPermission?displayProperty=fullName>
- <xref:System.Security.IPermission?displayProperty=fullName>
- <xref:System.Security.IStackWalk?displayProperty=fullName>
- <xref:System.Security.Policy.IIdentityPermissionFactory?displayProperty=fullName>

<span data-ttu-id="d978b-153">`IStackWalk`를 구현하는 클래스:</span><span class="sxs-lookup"><span data-stu-id="d978b-153">Classes that implement `IStackWalk`:</span></span>

- <xref:System.Security.NamedPermissionSet?displayProperty=fullName>
- <xref:System.Security.PermissionSet?displayProperty=fullName>

<span data-ttu-id="d978b-154">`IPermission`을 구현하는 클래스:</span><span class="sxs-lookup"><span data-stu-id="d978b-154">Classes that implement `IPermission`:</span></span>

- <xref:System.Security.CodeAccessPermission?displayProperty=fullName>

<span data-ttu-id="d978b-155">`CodeAccessPermission`에서 파생되는 클래스:</span><span class="sxs-lookup"><span data-stu-id="d978b-155">Classes that derive from `CodeAccessPermission`:</span></span>

- <xref:System.Configuration.ConfigurationPermission?displayProperty=fullName>
- <xref:System.Data.Common.DBDataPermission?displayProperty=fullName>
- <xref:System.Data.Odbc.OdbcPermission?displayProperty=fullName>
- <xref:System.Data.OleDb.OleDbPermission?displayProperty=fullName>
- <xref:System.Data.SqlClient.SqlClientPermission?displayProperty=fullName>
- <xref:System.Data.OracleClient.OraclePermission?displayProperty=fullName>
- <xref:System.Drawing.Printing.PrintingPermission?displayProperty=fullName>
- <xref:System.Net.DnsPermission?displayProperty=fullName>
- <xref:System.Net.SocketPermission?displayProperty=fullName>
- <xref:System.Net.WebPermission?displayProperty=fullName>
- <xref:System.Net.Mail.SmtpPermission?displayProperty=fullName>
- <xref:System.Net.NetworkInformation.NetworkInformationPermission?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.PnrpPermission?displayProperty=fullName>
- <xref:System.Net.PeerToPeer.Collaboration.PeerCollaborationPermission?displayProperty=fullName>
- <xref:System.Transactions.DistributedTransactionPermission?displayProperty=fullName>
- <xref:System.Web.AspNetHostingPermission?displayProperty=fullName>
- <xref:System.Xaml.Permissions.XamlLoadPermission?displayProperty=fullName>

<span data-ttu-id="d978b-156">`ResourcePermissionBase`에서 파생되는 클래스:</span><span class="sxs-lookup"><span data-stu-id="d978b-156">Classes that derive from `ResourcePermissionBase`:</span></span>

- <xref:System.Diagnostics.EventLogPermission?displayProperty=fullName>
- <xref:System.Diagnostics.PerformanceCounterPermission?displayProperty=fullName>
- <xref:System.DirectoryServices.DirectoryServicesPermission?displayProperty=fullName>
- <xref:System.ServiceProcess.ServiceControllerPermission?displayProperty=fullName>

<span data-ttu-id="d978b-157">`System.Security.Permissions` 네임스페이스의 열거형:</span><span class="sxs-lookup"><span data-stu-id="d978b-157">Enums in the `System.Security.Permissions` namespace:</span></span>

- <xref:System.Security.Permissions.DataProtectionPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.EnvironmentPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.FileDialogPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.HostProtectionResource?displayProperty=fullName>
- <xref:System.Security.Permissions.IsolatedStorageContainment?displayProperty=fullName>
- <xref:System.Security.Permissions.KeyContainerPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionAudio?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionImage?displayProperty=fullName>
- <xref:System.Security.Permissions.MediaPermissionVideo?displayProperty=fullName>
- <xref:System.Security.Permissions.PermissionState?displayProperty=fullName>
- <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>
- <xref:System.Security.Permissions.RegistryPermissionAccess?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName>
- <xref:System.Security.Permissions.SecurityPermissionFlag?displayProperty=fullName>
- <xref:System.Security.Permissions.StorePermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.TypeDescriptorPermissionFlags?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionClipboard?displayProperty=fullName>
- <xref:System.Security.Permissions.UIPermissionWindow?displayProperty=fullName>
- <xref:System.Security.Permissions.WebBrowserPermissionLevel?displayProperty=fullName>

<span data-ttu-id="d978b-158">코드 액세스 보안 형식에 따라 달라지는 클래스 및 멤버:</span><span class="sxs-lookup"><span data-stu-id="d978b-158">Classes and members that depend on code access security types:</span></span>

- <xref:System.AppDomain.PermissionSet?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.AllowReversePInvokeCallsAttribute?displayProperty=fullName>
- <xref:System.Security.HostProtectionException?displayProperty=fullName>
- <xref:System.Security.Policy.FileCodeGroup?displayProperty=fullName>
- <xref:System.Security.Policy.StrongName?displayProperty=fullName>
- <xref:System.Security.Policy.StrongNameMembershipCondition?displayProperty=fullName>
- [<span data-ttu-id="d978b-159">System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable\<StrongName>)</span><span class="sxs-lookup"><span data-stu-id="d978b-159">System.Security.Policy.ApplicationTrust.ApplicationTrust(PermissionSet, IEnumerable\<StrongName>)</span></span>](/dotnet/api/system.security.policy.applicationtrust.-ctor#System_Security_Policy_ApplicationTrust__ctor_System_Security_PermissionSet_System_Collections_Generic_IEnumerable_System_Security_Policy_StrongName__)
- <xref:System.Security.Policy.ApplicationTrust.FullTrustAssemblies?displayProperty=fullName>
- <xref:System.Security.Policy.GacInstalled?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyStatement.%23ctor%2A?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.AddNamedPermissionSet(System.Security.NamedPermissionSet)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.ChangeNamedPermissionSet(System.String,System.Security.PermissionSet)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.GetNamedPermissionSet(System.String)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.RemoveNamedPermissionSet(System.String)?displayProperty=fullName>
- <xref:System.Security.Policy.PolicyLevel.RemoveNamedPermissionSet(System.Security.NamedPermissionSet)?displayProperty=nameWithType>
- <xref:System.Security.Policy.PolicyStatement.PermissionSet?displayProperty=fullName>
- <xref:System.Security.Policy.Publisher?displayProperty=fullName>
- <xref:System.Security.Policy.Site?displayProperty=fullName>
- <xref:System.Security.Policy.Url?displayProperty=fullName>
- <xref:System.Security.Policy.Zone?displayProperty=fullName>
- <xref:System.Security.SecurityManager?displayProperty=fullName>

### <a name="syslib0004"></a><span data-ttu-id="d978b-160">SYSLIB0004</span><span class="sxs-lookup"><span data-stu-id="d978b-160">SYSLIB0004</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

### <a name="syslib0005"></a><span data-ttu-id="d978b-161">SYSLIB0005</span><span class="sxs-lookup"><span data-stu-id="d978b-161">SYSLIB0005</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType>

### <a name="syslib0006"></a><span data-ttu-id="d978b-162">SYSLIB0006</span><span class="sxs-lookup"><span data-stu-id="d978b-162">SYSLIB0006</span></span>

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

### <a name="syslib0007"></a><span data-ttu-id="d978b-163">SYSLIB0007</span><span class="sxs-lookup"><span data-stu-id="d978b-163">SYSLIB0007</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

### <a name="syslib0008"></a><span data-ttu-id="d978b-164">SYSLIB0008</span><span class="sxs-lookup"><span data-stu-id="d978b-164">SYSLIB0008</span></span>

- <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType>

### <a name="syslib0009"></a><span data-ttu-id="d978b-165">SYSLIB0009</span><span class="sxs-lookup"><span data-stu-id="d978b-165">SYSLIB0009</span></span>

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

### <a name="syslib0010"></a><span data-ttu-id="d978b-166">SYSLIB0010</span><span class="sxs-lookup"><span data-stu-id="d978b-166">SYSLIB0010</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

### <a name="syslib0011"></a><span data-ttu-id="d978b-167">SYSLIB0011</span><span class="sxs-lookup"><span data-stu-id="d978b-167">SYSLIB0011</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

### <a name="syslib0012"></a><span data-ttu-id="d978b-168">SYSLIB0012</span><span class="sxs-lookup"><span data-stu-id="d978b-168">SYSLIB0012</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>
