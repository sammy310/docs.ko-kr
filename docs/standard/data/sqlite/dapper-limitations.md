---
title: Dapper 제한 사항
ms.date: 12/13/2019
description: Dapper를 사용할 때 발생하는 몇 가지 제한 사항에 대해 설명합니다.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901206"
---
# <a name="dapper-limitations"></a>Dapper 제한 사항

Microsoft.Data.Sqlite를 [Dapper](https://stackexchange.github.io/Dapper/)와 함께 사용할 때 알아야 할 몇 가지 제한 사항이 있습니다.

## <a name="parameters"></a>매개 변수

SQLite 매개 변수 이름은 대소문자를 구분합니다. SQL에서 사용되는 매개 변수 이름이 익명 개체의 속성과 대/소문자가 일치해야 합니다. 문제 [#18861](https://github.com/dotnet/efcore/issues/18861)이 이 환경을 개선할 수 있습니다.

또한 Dapper는 매개 변수가 `@` 접두사를 사용하도록 요구합니다. 다른 접두사는 작동하지 않습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>데이터 형식

Dapper는 SqliteDataReader 인덱서를 사용하여 값을 읽습니다. 이 인덱서의 반환 형식은 개체입니다. 즉, long, double, string 또는 byte[] 값만 반환합니다. 자세한 내용은 [데이터 형식](types.md)을 참조하세요. Dapper는 이러한 기본 형식과 다른 기본 형식 간의 변환을 대부분 처리합니다. 아쉽지만 `DateTimeOffset`, `Guid` 또는 `TimeSpan`은 처리하지 않습니다. 결과에 이러한 형식을 사용하려면 형식 처리기를 만듭니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

형식 처리기는 쿼리 전에 추가해야 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
* [비동기 제한 사항](async.md)
