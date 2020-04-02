---
ms.openlocfilehash: d8506893f5b3eefa6f46dc9f773e43b125ee5210
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291665"
---
### <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a>Azure: Microsoft 접두사가 있는 Azure 통합 패키지가 제거됨

ASP.NET Core와 Azure SDK 간의 통합을 제공하는 다음 `Microsoft.*` 패키지는 ASP.NET Core 5.0에 포함되지 않습니다.

* [Azure Key Vault](/azure/key-vault/)를 [구성 시스템](/aspnet/core/fundamentals/configuration/)에 통합하는 [Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/)
* Azure Key Vault를 [ASP.NET Core 데이터 보호 시스템](/aspnet/core/security/data-protection/introduction)에 통합하는 [Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/)
* [Azure Blob Storage](/azure/storage/blobs/)를 ASP.NET Core 데이터 보호 시스템에 통합하는 [Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/)

이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 1

#### <a name="old-behavior"></a>이전 동작

`Microsoft.*` 패키지가 Azure 서비스를 구성 및 데이터 보호 API와 통합했습니다.

#### <a name="new-behavior"></a>새 동작

새 `Azure.*` 패키지가 Azure 서비스를 구성 및 데이터 보호 API와 통합합니다.

#### <a name="reason-for-change"></a>변경 이유

`Microsoft.*` 패키지에 다음과 같은 문제가 있습니다.

* 오래된 버전의 Azure SDK를 사용합니다. 새 버전의 Azure SDK에 호환성이 손상되는 변경이 포함되어 간단한 업데이트를 수행할 수 없습니다.
* .NET Core 릴리스 일정에 연동됩니다. 패키지의 소유권을 Azure SDK 팀으로 이전하면 Azure SDK가 업데이트될 때 패키지 업데이트를 사용할 수 있습니다.

#### <a name="recommended-action"></a>권장 작업

ASP.NET Core 2.1 이상 프로젝트에서 이전 `Microsoft.*` 패키지를 새 `Azure.*` 패키지로 바꿉니다.

| 이전 | 새로 만들기 |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [Azure.AspNetCore.DataProtection.Keys](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [Azure.AspNetCore.DataProtection.Blobs](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [Azure.Extensions.Configuration.Secrets](https://www.nuget.org/packages/Azure.Extensions.Configuration.Secrets) |

새 패키지는 호환성이 손상되는 변경을 포함하는 새 버전의 Azure SDK를 사용합니다. 일반적인 사용 패턴은 변경되지 않습니다. 일부 오버로드 및 옵션은 기본 Azure SDK API의 변경 내용에 맞게 달라질 수 있습니다.

이전 패키지는

* .NET Core 2.1 및 3.1의 수명 동안 ASP.NET Core 팀에서 지원합니다.
* .NET 5에 포함되지 않습니다.

프로젝트를 .NET 5로 업그레이드하는 경우 `Azure.*` 패키지로 전환하여 지원을 유지하세요.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
