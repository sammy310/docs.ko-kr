---
title: 암호화
ms.date: 12/13/2019
description: 데이터베이스 파일을 암호화 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450485"
---
# <a name="encryption"></a><span data-ttu-id="45f9a-103">암호화</span><span class="sxs-lookup"><span data-stu-id="45f9a-103">Encryption</span></span>

<span data-ttu-id="45f9a-104">SQLite는 기본적으로 데이터베이스 파일 암호화를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="45f9a-105">대신, [sqlcipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/)또는 [wxSQLite3](https://utelle.github.io/wxsqlite3) [와 같은 SQLite](https://www.hwaci.com/sw/sqlite/see.html)의 수정 된 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="45f9a-106">이 문서에서는 SQLCipher의 지원 되지 않는 오픈 소스 빌드를 사용 하는 방법을 보여 주지만 일반적으로 동일한 패턴을 따르기 때문에 다른 솔루션에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="45f9a-107">설치</span><span class="sxs-lookup"><span data-stu-id="45f9a-107">Installation</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="45f9a-108">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="45f9a-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="45f9a-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="45f9a-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="45f9a-110">암호화에 다른 네이티브 라이브러리를 사용 하는 방법에 대 한 자세한 내용은 [사용자 지정 SQLite 버전](custom-versions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45f9a-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="45f9a-111">키 지정</span><span class="sxs-lookup"><span data-stu-id="45f9a-111">Specify the key</span></span>

<span data-ttu-id="45f9a-112">암호화를 사용 하려면 `Password` 연결 문자열 키워드를 사용 하 여 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="45f9a-113"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>를 사용 하 여 사용자 입력의 값을 추가 하거나 업데이트 하 고 연결 문자열 삽입 공격을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="45f9a-114">데이터베이스 키를 재입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-114">Rekeying the database</span></span>

<span data-ttu-id="45f9a-115">데이터베이스의 암호화 키를 변경 하려면 `PRAGMA rekey` 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="45f9a-116">데이터베이스의 암호를 해독 하려면 `NULL`를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="45f9a-117">불행 하 게 SQLite는 `PRAGMA` 문에서 매개 변수를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="45f9a-118">대신 `quote()` 함수를 사용 하 여 SQL 삽입을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f9a-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
