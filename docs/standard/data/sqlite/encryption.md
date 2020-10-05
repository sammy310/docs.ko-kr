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
# <a name="encryption"></a><span data-ttu-id="df0e9-103">암호화</span><span class="sxs-lookup"><span data-stu-id="df0e9-103">Encryption</span></span>

<span data-ttu-id="df0e9-104">SQLite는 기본적으로 데이터베이스 파일 암호화를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="df0e9-105">대신 [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), [wxSQLite3](https://utelle.github.io/wxsqlite3) 같은 수정된 버전의 SQLite를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="df0e9-106">이 문서에서는 SQLCipher의 지원되지 않는 오픈 소스 빌드를 사용하는 방법을 보여 주지만, 다른 솔루션도 일반적으로 동일한 패턴을 따르기 때문에 이 정보를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="df0e9-107">설치</span><span class="sxs-lookup"><span data-stu-id="df0e9-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="df0e9-108">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="df0e9-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="df0e9-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="df0e9-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="df0e9-110">암호화에 다른 네이티브 라이브러리를 사용하는 방법에 대한 자세한 내용은 [사용자 지정 SQLite 버전](custom-versions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0e9-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="df0e9-111">키 지정</span><span class="sxs-lookup"><span data-stu-id="df0e9-111">Specify the key</span></span>

<span data-ttu-id="df0e9-112">새 데이터베이스에서 암호화를 사용하려면 `Password` 연결 문자열 키워드를 사용하여 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-112">To enable encryption on a new database, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="df0e9-113"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>를 사용하여 사용자 입력의 값을 추가 또는 업데이트하고 연결 문자열 삽입 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> <span data-ttu-id="df0e9-114">기존 데이터베이스를 암호화하고 암호를 해독하는 방법은 사용 중인 솔루션에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-114">The method for encrypting and decrypting existing databases varies depending on which solution you're using.</span></span> <span data-ttu-id="df0e9-115">예를 들어 SQLCipher에서는 `sqlcipher_export()` 함수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-115">For example, you need to use the `sqlcipher_export()` function on SQLCipher.</span></span> <span data-ttu-id="df0e9-116">자세한 내용은 솔루션 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0e9-116">Check your solution's documentation for details.</span></span>

## <a name="rekeying-the-database"></a><span data-ttu-id="df0e9-117">데이터베이스 키 다시 입력</span><span class="sxs-lookup"><span data-stu-id="df0e9-117">Rekeying the database</span></span>

<span data-ttu-id="df0e9-118">암호화된 데이터베이스의 키를 변경하려면 `PRAGMA rekey` 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-118">If you want to change the key of an encrypted database, issue a `PRAGMA rekey` statement.</span></span>

<span data-ttu-id="df0e9-119">아쉽지만 SQLite는 `PRAGMA` 문에서 매개 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-119">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="df0e9-120">대신 `quote()` 함수를 사용하여 SQL 삽입을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="df0e9-120">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
