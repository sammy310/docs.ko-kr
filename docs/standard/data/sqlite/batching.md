---
title: 일괄 처리
ms.date: 12/13/2019
description: 단일 명령으로 SQL 문의 일괄 처리를 실행 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450311"
---
# <a name="batching"></a>일괄 처리

SQLite는 기본적으로 SQL 문 일괄 처리를 단일 명령으로 지원 하지 않습니다. 그러나 네트워크와 관련 된 네트워크는 없기 때문에 실제 성능에는 도움이 되지 않습니다. 그러나 ADO.NET은 다른 공급자 처럼 동작 하도록 하기 위한 편의를 위해 문 일괄 처리를 구현 합니다.

<xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>를 호출할 때 문은 결과를 반환 하는 첫 번째 문으로 실행 됩니다. <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType>를 호출 하면 그 다음에 결과를 반환할 때까지 또는 일괄 처리의 끝에 도달할 때까지 문을 계속 실행 합니다. <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> 또는 <xref:System.Data.Common.DbDataReader.Close%2A>를 호출 하면 `NextResult()`에서 사용 되지 않은 나머지 모든 문이 실행 됩니다. 데이터 판독기를 삭제 하지 않으면 종료 자가 나머지 문을 실행 하려고 시도 하지만 발견 한 오류는 무시 됩니다. 따라서 일괄 처리를 사용 하는 경우 `DbDataReader` 개체를 삭제 하는 것이 중요 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>참조

* [대량 삽입](bulk-insert.md)
