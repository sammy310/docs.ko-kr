---
title: 암호화
ms.date: 09/08/2020
description: 데이터베이스 파일을 암호화하는 방법을 알아봅니다.
ms.openlocfilehash: 1b33e1510a269aba87caba2cd39faab33791aa55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203412"
---
# <a name="encryption"></a>암호화

SQLite는 기본적으로 데이터베이스 파일 암호화를 지원하지 않습니다. 대신 [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), [wxSQLite3](https://utelle.github.io/wxsqlite3) 같은 수정된 버전의 SQLite를 사용해야 합니다. 이 문서에서는 SQLCipher의 지원되지 않는 오픈 소스 빌드를 사용하는 방법을 보여 주지만, 다른 솔루션도 일반적으로 동일한 패턴을 따르기 때문에 이 정보를 적용할 수 있습니다.

## <a name="installation"></a>설치

### <a name="net-core-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

암호화에 다른 네이티브 라이브러리를 사용하는 방법에 대한 자세한 내용은 [사용자 지정 SQLite 버전](custom-versions.md)을 참조하세요.

## <a name="specify-the-key"></a>키 지정

새 데이터베이스에서 암호화를 사용하려면 `Password` 연결 문자열 키워드를 사용하여 키를 지정합니다. <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>를 사용하여 사용자 입력의 값을 추가 또는 업데이트하고 연결 문자열 삽입 공격을 방지합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> 기존 데이터베이스를 암호화하고 암호를 해독하는 방법은 사용 중인 솔루션에 따라 달라집니다. 예를 들어 SQLCipher에서는 `sqlcipher_export()` 함수를 사용해야 합니다. 자세한 내용은 솔루션 설명서를 참조하세요.

## <a name="rekeying-the-database"></a>데이터베이스 키 다시 입력

암호화된 데이터베이스의 키를 변경하려면 `PRAGMA rekey` 문을 실행합니다.

아쉽지만 SQLite는 `PRAGMA` 문에서 매개 변수를 지원하지 않습니다. 대신 `quote()` 함수를 사용하여 SQL 삽입을 방지합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
