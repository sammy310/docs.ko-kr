---
title: 사용자 지정 SQLite 버전
ms.date: 12/13/2019
description: 네이티브 SQLite 라이브러리의 사용자 지정 버전을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746984"
---
# <a name="custom-sqlite-versions"></a>사용자 지정 SQLite 버전

Microsoft.Data.Sqlite는 SQLitePCLRaw를 기반으로 합니다. 번들을 사용하거나 SQLitePCLRaw 공급자를 구성하여 네이티브 SQLite 라이브러리의 사용자 지정 버전을 사용할 수 있습니다.

## <a name="bundles"></a>번들

SQLitePCLRaw는 다양한 플랫폼에서 적절한 종속성을 쉽게 가져올 수 있도록 번들 패키지를 제공합니다.

기본 Microsoft.Data.Sqlite 패키지는 기본적으로 SQLitePCLRaw.bundle_e_sqlite3를 가져옵니다.

다른 번들을 사용하려면 사용하려는 번들 패키지와 함께 `Microsoft.Data.Sqlite.Core` 패키지를 대신 설치합니다. 번들은 Microsoft.Data.Sqlite에 의해 자동으로 초기화됩니다.

| 번들 | 설명 |
| --- | --- |
| SQLitePCLRaw.bundle_e_sqlite3 | 모든 플랫폼에서 SQLite의 일관된 버전을 제공합니다. FTS4, FTS5, JSON1 및 R*Tree 확장을 포함합니다. 기본값입니다. |
| SQLitePCLRaw.bundle_green | iOS에서 시스템 SQLite 라이브러리를 사용하는 것을 제외하고 bundle_e_sqlite3와 동일합니다. |
| SQLitePCLRaw.bundle_zetetic | Zetetic의 공식 SQLCipher 빌드를 사용합니다(포함되지 않음). |
| SQLitePCLRaw.bundle_winsqlite3 | Windows 10의 시스템 SQLite 라이브러리인 winsqlite3.dll을 사용합니다. |
| SQLitePCLRaw.bundle_e_sqlcipher | SQLCipher의 비공식 오픈 소스 빌드를 제공합니다. |

예를 들어 비공식 오픈 소스 SQLCipher 빌드를 사용하려면 다음 명령을 사용합니다.

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

## <a name="sqlitepclraw-providers"></a>SQLitePCLRaw 공급자

`SQLitePCLRaw.provider.dynamic_cdecl` 패키지를 활용하여 자체 SQLite 빌드를 사용할 수 있습니다. 이 경우 네이티브 라이브러리를 앱과 함께 배포해야 합니다. 단, 앱과 함께 네이티브 라이브러리를 배포하는 세부 방법은 사용 중인 .NET 플랫폼 및 런타임에 따라 크게 달라집니다.

먼저 IGetFunctionPointer를 구현해야 합니다. 구현은 .NET Core에서 매우 간단합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

그런 다음 SQLitePCLRaw 공급자를 구성합니다. 이 작업은 앱에서 Microsoft.Data.Sqlite를 사용하기 전에 수행해야 합니다. 또한 공급자를 재정의할 수 있는 SQLitePCLRaw 번들 패키지를 사용하지 않도록 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
