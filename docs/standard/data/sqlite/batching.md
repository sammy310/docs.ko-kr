---
title: 일괄 처리
ms.date: 12/13/2019
description: 단일 명령으로 SQL 문의 일괄 처리를 실행하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450311"
---
# <a name="batching"></a>일괄 처리

SQLite는 기본적으로 SQL 문을 단일 명령으로 일괄 처리하는 것을 지원하지 않습니다. 그러나 관련된 네트워크가 없기 때문에 실제 성능에는 도움이 되지 않습니다. 다만 Microsoft.Data.Sqlite는 편의상 다른 ADO.NET 공급자처럼 동작하도록 하기 위해 명령문 일괄 처리를 구현합니다.

<xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>을 호출하면 명령문은 결과를 반환하는 첫 번째 명령문까지 실행됩니다. <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType>을 호출하면 결과를 반환하는 다음 명령문 또는 일괄 처리의 끝에 도달할 때까지 명령문을 계속 실행합니다. <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> 또는 <xref:System.Data.Common.DbDataReader.Close%2A>를 호출하면 `NextResult()`에서 사용되지 않은 나머지 명령문이 실행됩니다. 데이터 판독기를 삭제하지 않으면 종료자가 나머지 명령문을 실행하려고 하지만 발생한 오류는 무시됩니다. 이로 인해 일괄 처리를 사용할 때는 `DbDataReader` 개체를 삭제해야 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>참조

* [대량 삽입](bulk-insert.md)
