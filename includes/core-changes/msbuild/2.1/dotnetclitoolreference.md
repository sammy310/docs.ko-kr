---
ms.openlocfilehash: 370c6eb23a50ed388f0b10a5c5f4779ba2a1b144
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102623248"
---
### <a name="project-tools-now-included-in-sdk"></a>이제 프로젝트 도구가 SDK에 포함됨

이제 .NET Core 2.1 SDK에 일반적인 CLI 도구가 포함되며 더 이상 프로젝트에서 해당 도구를 참조할 필요가 없습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Core 2.0에서 프로젝트는 `<DotNetCliToolReference>` 프로젝트 설정을 사용하여 외부 .NET 도구를 참조합니다. .NET Core 2.1에서 해당 도구 중 일부는 .NET Core SDK에 포함되며 더 이상 설정이 필요하지 않습니다. 프로젝트에 해당 도구에 대한 참조를 포함하는 경우 다음과 같은 오류가 표시됩니다. **'Microsoft.EntityFrameworkCore.Tools.DotNet' 도구는 이제 .NET Core SDK에 포함됩니다.**

이제 도구가 .NET Core 2.1 SDK에 포함됨:

| \<DotNetCliToolReference> 값                   | 도구                                                                                                            |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `Microsoft.DotNet.Watcher.Tools`               | `dotnet-watch`               |
| `Microsoft.Extensions.SecretManager.Tools`     | [dotnet-user-secrets](https://github.com/dotnet/aspnetcore/blob/master/src/Tools/dotnet-user-secrets/README.md) |
| `Microsoft.Extensions.Caching.SqlConfig.Tools` | [dotnet-sql-cache](https://github.com/dotnet/aspnetcore/blob/master/src/Tools/dotnet-sql-cache/README.md)       |
| `Microsoft.EntityFrameworkCore.Tools.DotNet`   | [dotnet-ef](/ef/core/miscellaneous/cli/dotnet)                                                                  |

#### <a name="version-introduced"></a>도입된 버전

.NET Core SDK 2.1.300

#### <a name="recommended-action"></a>권장 조치

프로젝트에서 `<DotNetCliToolReference>` 설정을 제거합니다.

#### <a name="category"></a>범주

MSBuild

#### <a name="affected-apis"></a>영향을 받는 API

N/A
