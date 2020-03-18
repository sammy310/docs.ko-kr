---
title: 개요
ms.date: 12/13/2019
description: Microsoft.Data.Sqlite 개요
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "77543601"
---
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="6393c-103">Microsoft.Data.Sqlite 개요</span><span class="sxs-lookup"><span data-stu-id="6393c-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="6393c-104">Microsoft.Data.Sqlite는 SQLite용 경량 [ADO.NET](../../../framework/data/adonet/index.md) 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="6393c-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="6393c-105">SQLite용 [Entity Framework Core](/ef/core/) 공급자는 이 라이브러리를 토대로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6393c-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="6393c-106">그러나 독립적으로 또는 다른 데이터 액세스 라이브러리와 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6393c-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="6393c-107">설치</span><span class="sxs-lookup"><span data-stu-id="6393c-107">Installation</span></span>

<span data-ttu-id="6393c-108">안정적인 최신 버전은 [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite)에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6393c-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="6393c-109">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="6393c-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[<span data-ttu-id="6393c-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6393c-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="6393c-111">사용법</span><span class="sxs-lookup"><span data-stu-id="6393c-111">Usage</span></span>

<span data-ttu-id="6393c-112">이 라이브러리는 연결, 명령, 데이터 판독기 등에 공통적으로 적용되는 ADO.NET 추상화를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6393c-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="6393c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6393c-113">See also</span></span>

* [<span data-ttu-id="6393c-114">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="6393c-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="6393c-115">API 참조</span><span class="sxs-lookup"><span data-stu-id="6393c-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0)
* [<span data-ttu-id="6393c-116">SQL 구문</span><span class="sxs-lookup"><span data-stu-id="6393c-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
