---
title: 사용자 지정 SQLite 버전
ms.date: 12/13/2019
description: 기본 SQLite 라이브러리의 사용자 지정 버전을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 8a2646138ea9dbecf412a2e8e0e347e2d71a5b0b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450389"
---
# <a name="custom-sqlite-versions"></a>사용자 지정 SQLite 버전

SQLitePCLRaw을 기반으로 합니다. 번들을 사용 하거나 SQLitePCLRaw 공급자를 구성 하 여 기본 SQLite 라이브러리의 사용자 지정 버전을 사용할 수 있습니다.

## <a name="bundles"></a>번들

SQLitePCLRaw는 다양 한 플랫폼에서 적절 한 종속성을 쉽게 가져올 수 있도록 번들 패키지를 제공 합니다.

기본적으로 bundle_e_sqlite3 SQLitePCLRaw는 주 Microsoft. Sqlite 패키지를 가져옵니다.

다른 번들을 사용 하려면 사용 하려는 번들 패키지와 함께 `Microsoft.Data.Sqlite.Core` 패키지를 설치 합니다. 번들은 Microsoft. Data. Sqlite에 의해 자동으로 초기화 됩니다.

| 번들 | 설명 |
| --- | --- |
| SQLitePCLRaw bundle_e_sqlite3 | 모든 플랫폼에서 SQLite의 일관 된 버전을 제공 합니다. FTS4, FTS5, JSON1 및를 포함 합니다. | R * 트리 확장 이것이 기본값입니다. |
| SQLitePCLRaw bundle_green | 시스템 SQLite 라이브러리를 사용 하는 iOS를 제외 하 고 bundle_e_sqlite3와 동일 합니다. |
| SQLitePCLRaw bundle_zetetic | Zetetic의 공식 SQLCipher 빌드를 사용 합니다 (포함 되지 않음). |
| SQLitePCLRaw bundle_winsqlite3 | Windows 10의 시스템 SQLite 라이브러리인 winsqlite3를 사용 합니다. |
| SQLitePCLRaw bundle_e_sqlcipher | SQLCipher의 비공식 오픈 소스 빌드를 제공 합니다. |

예를 들어, 비공식적으로 오픈 소스 SQLCipher 빌드를 사용 하려면 다음 명령을 사용 합니다.

### <a name="net-core-clitabnetcore-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>SQLitePCLRaw 공급자

`SQLitePCLRaw.provider.dynamic_cdecl` 패키지를 활용 하 여 SQLite의 고유한 빌드를 사용할 수 있습니다. 이 경우 네이티브 라이브러리를 앱과 함께 배포 해야 합니다. 앱을 사용 하 여 네이티브 라이브러리를 배포 하는 방법에 대 한 세부 정보는 사용 중인 .NET 플랫폼과 런타임에 따라 크게 달라 집니다.

먼저 IGetFunctionPointer를 구현 해야 합니다. 구현은 .NET Core에서 매우 간단 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

그런 다음 SQLitePCLRaw 공급자를 구성 합니다. 이 작업은 앱에서 사용 하기 전에 수행 해야 합니다. 또한 공급자를 재정의할 수 있는 SQLitePCLRaw 번들 패키지를 사용 하지 않도록 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
