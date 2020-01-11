---
title: ADO.NET 제한 사항
ms.date: 12/13/2019
description: 발생할 수 있는 몇 가지 ADO.NET 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901262"
---
# <a name="adonet-limitations"></a>ADO.NET 제한 사항

ADO.NET는 많은 수의 추상화 구현을 제공 하지만 몇 가지 제한 사항이 있습니다.

## <a name="database-schema-information"></a>데이터베이스 스키마 정보

<xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 메서드를 사용 하 여 쿼리 결과에 대 한 메타 데이터를 사용할 수 있습니다.

`DbConnection.GetSchema()` 구현 되지 않습니다. 이 API는 잘 정의 되어 있지 않으므로 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) 테이블 및 [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA와 같은 표준 SQLite api를 사용 하 여 데이터베이스 메타 데이터를 직접 검색 하는 것이 좋습니다.

자세한 내용은 [메타 데이터](metadata.md)를 참조 하세요.

## <a name="systemtransactions"></a>System.Transactions

Microsoft. Sqlite는 아직 시스템 트랜잭션을 지원 하지 않습니다. 대신 ADO.NET 트랜잭션을 사용 하십시오. 자세한 내용은 [트랜잭션](transactions.md)을 참조 하세요.

문제 [#13825](https://github.com/dotnet/efcore/issues/13825)에서 시스템이 트랜잭션을 지원 하지 않는다는 의견을 제공 합니다.

## <a name="data-adapters"></a>데이터 어댑터

`DbDataAdapter`은 (는) Microsoft에서 아직 구현 되지 않았습니다. Sqlite. 즉, ADO.NET `DataSet`와 `DataTable`만 사용 하 여 데이터를 로드 하 고 업데이트할 수 없습니다.

`DbDataAdapter`구현에 대 한 피드백을 제공 하려면 문제 [#13838](https://github.com/dotnet/efcore/issues/13838) 를 사용 합니다.

## <a name="output-parameters"></a>출력 매개 변수

SQLite는 출력 매개 변수를 지원 하지 않습니다.

## <a name="positional-parameters"></a>위치 매개 변수

Microsoft. Data. Sqlite는 명명 된 [매개 변수만](parameters.md)지원 합니다. 위치 매개 변수는 지원 되지 않습니다.

## <a name="stored-procedures"></a>저장 프로시저

SQLite는 저장 프로시저를 지원 하지 않습니다.

## <a name="isolation-levels"></a>격리 수준

SQLite 트랜잭션에서는 `Chaos` 및 `Snapshot` 격리 수준이 지원 되지 않습니다.

## <a name="see-also"></a>참조

* [비동기 제한 사항](async.md)
* [데이터 형식](types.md)
* [트랜잭션](transactions.md)
