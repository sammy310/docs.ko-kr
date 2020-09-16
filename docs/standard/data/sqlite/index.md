---
title: 개요
ms.date: 12/13/2019
description: Microsoft.Data.Sqlite 개요
ms.openlocfilehash: 7c952848f7e7ea04f11fe9340f77a1f376a1be07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552442"
---
# <a name="microsoftdatasqlite-overview"></a>Microsoft.Data.Sqlite 개요

Microsoft.Data.Sqlite는 SQLite용 경량 [ADO.NET](../../../framework/data/adonet/index.md) 공급자입니다. SQLite용 [Entity Framework Core](/ef/core/) 공급자는 이 라이브러리를 토대로 빌드됩니다. 그러나 독립적으로 또는 다른 데이터 액세스 라이브러리와 함께 사용할 수도 있습니다.

## <a name="installation"></a>설치

안정적인 최신 버전은 [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite)에서 제공됩니다.

### <a name="net-core-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>사용법

이 라이브러리는 연결, 명령, 데이터 판독기 등에 공통적으로 적용되는 ADO.NET 추상화를 구현합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>참조

* [연결 문자열](connection-strings.md)
* [API 참조](../../../../api/index.md?view=msdata-sqlite-3.0)
* [SQL 구문](https://www.sqlite.org/lang.html)
