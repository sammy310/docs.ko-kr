---
title: 사용자 정의 함수
ms.date: 12/13/2019
description: 사용자 정의 스칼라 및 집계 함수를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450413"
---
# <a name="user-defined-functions"></a>사용자 정의 함수

대부분의 데이터베이스에는 함수를 정의하는 데 사용할 수 있는 SQL의 절차적 언어가 있습니다. 그러나 SQLite는 앱과 함께 In Process로 실행됩니다. SQL의 새로운 언어를 배울 필요 없이 앱의 프로그래밍 언어를 사용할 수 있습니다.

## <a name="scalar-functions"></a>스칼라 함수

스칼라 함수는 쿼리의 각 행에 대해 단일 스칼라 값을 반환합니다. 새 스칼라 함수를 정의하고 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>을 사용하여 기본 제공 함수를 재정의합니다.

지원되는 매개 변수 목록과 `func` 인수에 대한 반환 형식에 대해서는 [데이터 형식](types.md)을 참조하세요.

`state` 인수를 지정하면 해당 값이 함수의 모든 호출에 전달됩니다. 이를 사용하여 클로저를 방지합니다.

쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 함수가 결정적일 경우 `isDeterministic`을 지정합니다.

다음 예제에서는 스칼라 함수를 추가하여 실린더의 반지름을 계산하는 방법을 보여 줍니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>연산자

다음 SQLite 연산자는 해당 스칼라 함수에 의해 구현됩니다. 앱에서 이러한 스칼라 함수를 정의하면 이러한 연산자의 동작이 재정의됩니다.

| 연산자          | 기능      |
| ----------------- | ------------- |
| X GLOB Y          | glob(Y, X)    |
| X LIKE Y          | like(Y, X)    |
| X LIKE Y ESCAPE Z | like(Y, X, Z) |
| X MATCH Y         | match(Y, X)   |
| X REGEXP Y        | regexp(Y, X)  |

다음 예제에서는 해당하는 연산자를 사용하도록 regexp 함수를 정의하는 방법을 보여 줍니다. SQLite는 regexp 함수의 기본 구현을 포함하지 않습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>집계 함수

집계 함수는 쿼리의 모든 행에 대해 집계된 단일 값을 반환합니다. <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>를 사용하여 집계 함수를 정의하고 재정의합니다.

`seed` 인수는 컨텍스트의 초기 상태를 지정합니다. 또한 이를 사용하여 클로저를 방지합니다.

`func` 인수는 행당 한 번 호출됩니다. 컨텍스트를 사용하여 최종 결과를 누적합니다. 컨텍스트를 반환합니다. 이 패턴을 사용하면 컨텍스트를 값 형식 또는 변경 불가능으로 허용합니다.

`resultSelector`를 지정하지 않으면 컨텍스트의 최종 상태가 결과로 사용됩니다. 이렇게 하면 각 행의 수를 늘리고 반환하기만 하면 되는 sum 및 count와 같은 함수의 정의를 단순화할 수 있습니다.

모든 행을 반복한 후 컨텍스트의 최종 결과를 계산하려면 `resultSelector`를 지정합니다.

`func` 인수에 대한 지원되는 매개 변수 목록과 `resultSelector`에 대한 반환 형식에 대해서는 [데이터 형식](types.md)을 참조하세요.

함수가 결정적인 경우 쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 `isDeterministic`을 지정합니다.

다음 예제에서는 집계 함수를 정의하여 열의 표준 편차를 계산합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>오류

사용자 정의 함수에서 예외를 throw하는 경우 메시지는 SQLite로 반환됩니다. 그러면 SQLite에서 오류가 발생시키고 Microsoft.Data.Sqlite에서 SqliteException을 throw합니다. 자세한 내용은 [데이터베이스 오류](database-errors.md)를 참조하세요.

기본적으로 오류 SQLite 오류 코드는 SQLITE_ERROR(또는 1)입니다. 그러나 지정된 <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode>를 사용하여 함수에서 <xref:Microsoft.Data.Sqlite.SqliteException>을 throw하여 변경할 수 있습니다.

## <a name="debugging"></a>디버깅

SQLite는 구현을 직접 호출합니다. 이렇게 하면 SQLite가 쿼리를 평가하는 동안 트리거되는 중단점을 추가할 수 있습니다. 사용자 정의 함수를 만드는 데 도움이 되는 전체 .NET 디버깅 환경을 사용할 수 있습니다.

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
* [SQLite 핵심 함수](https://www.sqlite.org/lang_corefunc.html)
* [SQLite 집계 함수](https://www.sqlite.org/lang_aggfunc.html)
