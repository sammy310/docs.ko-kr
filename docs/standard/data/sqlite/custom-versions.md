---
title: 사용자 지정 SQLite 버전
ms.date: 05/14/2020
description: 네이티브 SQLite 라이브러리의 사용자 지정 버전을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 15db10db26bc7c5017313ca020a0e1e528ba207a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440839"
---
# <a name="custom-sqlite-versions"></a>사용자 지정 SQLite 버전

`Microsoft.Data.Sqlite`는 `SQLitePCLRaw`를 기반으로 빌드됩니다. 번들을 사용하거나 `SQLitePCLRaw` 공급자를 구성하여 네이티브 SQLite 라이브러리의 사용자 지정 버전을 사용할 수 있습니다.

## <a name="bundles"></a>번들

`SQLitePCLRaw`는 다양한 플랫폼에서 적절한 종속성을 쉽게 가져올 수 있도록 편의 기반 번들 패키지를 제공합니다. 주 `Microsoft.Data.Sqlite` 패키지는 기본적으로 `SQLitePCLRaw.bundle_e_sqlite3`을 가져옵니다. 다른 번들을 사용하려면 사용하려는 번들 패키지와 함께 `Microsoft.Data.Sqlite.Core` 패키지를 대신 설치합니다. 번들은 `Microsoft.Data.Sqlite`에 의해 자동으로 초기화됩니다.

| 번들 | 설명 |
|--|--|
| [SQLitePCLRaw.bundle_e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | 모든 플랫폼에서 SQLite의 일관된 버전을 제공합니다. FTS4, FTS5, JSON1 및 R*Tree 확장을 포함합니다. 기본값입니다. |
| [SQLitePCLRaw.bundle_e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | `SQLCipher`의 비공식 오픈 소스 빌드를 제공합니다. |
| [SQLitePCLRaw.bundle_green](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | iOS에서 시스템 SQLite 라이브러리를 사용하는 것을 제외하고 `bundle_e_sqlite3`과 동일합니다. |
| [SQLitePCLRaw.bundle_winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | Windows 10의 시스템 SQLite 라이브러리인 `winsqlite3.dll`을 사용합니다. |
| [SQLitePCLRaw.bundle_zetetic](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | Zetetic의 공식 `SQLCipher` 빌드를 사용합니다(포함되지 않음). |

예를 들어 비공식 오픈 소스 `SQLCipher` 빌드를 사용하려면 다음 명령을 사용합니다.

### <a name="net-core-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a>사용 가능한 SQLitePCLRaw 공급자

번들을 사용하지 않는 경우 핵심 어셈블리에서 SQLite의 사용 가능한 공급자를 사용할 수 있습니다.

| 공급자 | 설명 |
|--|--|
| [SQLitePCLRaw.provider.dynamic](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | `dynamic` 공급자는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> 특성을 사용하는 대신 네이티브 라이브러리를 로드합니다. 이 공급자를 사용하는 방법에 대한 자세한 내용은 [동적 공급자 사용](#use-the-dynamic-provider)을 참조하세요. |
| [SQLitePCLRaw.provider.e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | 기본 공급자는 `e_sqlite3`입니다. |
| [SQLitePCLRaw.provider.e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | `e_sqlcipher` 공급자는 비공식적이고 지원되지 않는 `SQLCipher`입니다. |
| [SQLitePCLRaw.provider.sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | `sqlite3` 공급자는 iOS, macOS 및 Linux용 시스템 제공 `SQLite`입니다. |
| [SQLitePCLRaw.provider.sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | `sqlcipher` 공급자는 `Zetetic`의 공식 `SQLCipher` 빌드를 위한 것입니다. |
| [SQLitePCLRaw.provider.winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | `winsqlite3` 공급자는 Windows 10 환경을 위한 것입니다. |

`sqlite3` 공급자를 사용하려면 다음 명령을 사용합니다.

### <a name="net-core-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

패키지가 설치되면 공급자를 `sqlite3` 인스턴스로 설정합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a>동적 공급자 사용

`SQLitePCLRaw.provider.dynamic_cdecl` 패키지를 활용하여 자체 SQLite 빌드를 사용할 수 있습니다. 이 경우 네이티브 라이브러리를 앱과 함께 배포해야 합니다. 단, 앱과 함께 네이티브 라이브러리를 배포하는 세부 방법은 사용 중인 .NET 플랫폼 및 런타임에 따라 크게 달라집니다.

먼저 `IGetFunctionPointer`를 구현해야 합니다. .NET Core에서의 구현은 다음과 같습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

그런 다음 `SQLitePCLRaw` 공급자를 구성합니다. 앱에서 `Microsoft.Data.Sqlite`를 사용하기 전에 이 작업을 수행해야 합니다. 또한 공급자를 재정의할 수 있는 `SQLitePCLRaw` 번들 패키지를 사용하지 않아야 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
