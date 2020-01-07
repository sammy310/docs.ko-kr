---
title: Dapper 제한 사항
ms.date: 12/13/2019
description: Dapper를 사용할 때 발생 하는 몇 가지 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450497"
---
# <a name="dapper-limitations"></a>Dapper 제한 사항

[Dapper](https://stackexchange.github.io/Dapper/)와 함께 Microsoft. Sqlite를 사용할 때 알아야 할 몇 가지 제한 사항이 있습니다.

## <a name="parameters"></a>매개 변수

SQLite 매개 변수 이름은 대/소문자를 구분 합니다. SQL에서 사용 되는 매개 변수 이름이 익명 개체의 속성에 대 한 대/소문자와 일치 하는지 확인 합니다. [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) 문제는이 환경을 개선 하는 데 도움이 됩니다.

또한 Dapper는 `@` 접두사를 사용 하는 매개 변수를 필요로 합니다. 다른 접두사는 작동 하지 않습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>데이터 형식

Dapper는 SqliteDataReader 인덱서를 사용 하 여 값을 읽습니다. 이 인덱서의 반환 형식은 object 이며 long, double, string 또는 byte [] 값만 반환 하는 것을 의미 합니다. 자세한 내용은 [데이터 형식](types.md)을 참조 하세요. Dapper는 이러한 기본 형식 및 다른 기본 형식 간의 변환을 대부분 처리 합니다. 아쉽게도 `DateTimeOffset`, `Guid`또는 `TimeSpan`를 처리 하지 않습니다. 결과에 이러한 형식을 사용 하려면 형식 처리기를 만듭니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

쿼리 하기 전에 형식 처리기를 추가 해야 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
* [비동기 제한 사항](async.md)
