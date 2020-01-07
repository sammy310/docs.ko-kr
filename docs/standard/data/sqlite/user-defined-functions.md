---
title: 사용자 정의 함수
ms.date: 12/13/2019
description: 사용자 정의 스칼라 및 집계 함수를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450413"
---
# <a name="user-defined-functions"></a>사용자 정의 함수

대부분의 데이터베이스에는 함수를 정의 하는 데 사용할 수 있는 SQL의 절차적 언어가 있습니다. 그러나 SQLite는 앱과 함께 in-process로 실행 됩니다. SQL의 새로운 언어를 배울 필요 없이 앱의 프로그래밍 언어를 사용할 수 있습니다.

## <a name="scalar-functions"></a>스칼라 함수

스칼라 함수는 쿼리의 각 행에 대해 단일 스칼라 값을 반환 합니다. 새 스칼라 함수를 정의 하 고 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>를 사용 하 여 기본 제공 함수를 재정의 합니다.

`func` 인수에 대해 지원 되는 매개 변수 및 반환 형식 목록은 [데이터 형식](types.md) 을 참조 하세요.

`state` 인수를 지정 하면 해당 값이 함수의 모든 호출에 전달 됩니다. 이를 사용 하 여 클로저를 방지 합니다.

쿼리가 쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 함수가 결정적 일 경우 `isDeterministic`를 지정 합니다.

다음 예제에서는 스칼라 함수를 추가 하 여 실린더의 반지름을 계산 하는 방법을 보여 줍니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>연산자

다음 SQLite 연산자는 해당 스칼라 함수에 의해 구현 됩니다. 앱에서 이러한 스칼라 함수를 정의 하면 이러한 연산자의 동작이 재정의 됩니다.

| 연산자          | 기능      |
| ----------------- | ------------- |
| X GLOB Y          | glob (Y, X)    |
| Y와 같은 X          | like (Y, X)    |
| X와 같은 Y 이스케이프 Z | like (Y, X, Z) |
| X 일치 Y         | match (Y, X)   |
| X REGEXP Y        | regexp (Y, X)  |

다음 예제에서는 해당 하는 연산자를 사용 하도록 regexp 함수를 정의 하는 방법을 보여 줍니다. SQLite는 regexp 함수의 기본 구현을 포함 하지 않습니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>집계 함수

집계 함수는 쿼리의 모든 행에 대해 집계 된 단일 값을 반환 합니다. <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>를 사용 하 여 집계 함수를 정의 하 고 재정의 합니다.

`seed` 인수는 컨텍스트의 초기 상태를 지정 합니다. 이를 사용 하 여 클로저를 방지 합니다.

`func` 인수는 행당 한 번 호출 됩니다. 컨텍스트를 사용 하 여 최종 결과를 누적 합니다. 컨텍스트를 반환 합니다. 이 패턴을 사용 하면 컨텍스트를 값 형식 또는 변경할 수 없습니다.

`resultSelector` 지정 하지 않으면 컨텍스트의 최종 상태가 결과로 사용 됩니다. 이렇게 하면 각 행의 수를 늘리고 반환 하기만 하면 되는 sum 및 count와 같은 함수의 정의가 간단해 집니다.

모든 행을 반복한 후 컨텍스트의 최종 결과를 계산 하려면 `resultSelector`를 지정 합니다.

`resultSelector`에 대 한 `func` 인수 및 반환 형식에 대해 지원 되는 매개 변수 형식 목록은 [데이터 형식](types.md) 을 참조 하세요.

함수가 결정적 이면 쿼리를 컴파일할 때 SQLite에서 추가 최적화를 사용할 수 있도록 `isDeterministic`를 지정 합니다.

다음 예에서는 집계 함수를 정의 하 여 열의 표준 편차를 계산 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>오류

사용자 정의 함수에서 예외를 throw 하는 경우 메시지는 SQLite로 반환 됩니다. 그러면 SQLite에서 오류 및 SqliteException이 발생 합니다. Sqlite에서이를 throw 합니다. 자세한 내용은 [데이터베이스 오류](database-errors.md)를 참조 하세요.

기본적으로 SQLite 오류 코드는 SQLITE_ERROR (또는 1)입니다. 그러나 지정 된 <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode>를 사용 하 여 함수에서 <xref:Microsoft.Data.Sqlite.SqliteException>를 throw 하 여 변경할 수 있습니다.

## <a name="debugging"></a>디버깅

SQLite는 구현을 직접 호출 합니다. 이렇게 하면 SQLite가 쿼리를 평가 하는 동안 트리거되는 중단점을 추가할 수 있습니다. 사용자 정의 함수를 만드는 데 도움이 되는 전체 .NET 디버깅 환경을 사용할 수 있습니다.

## <a name="see-also"></a>참조

* [데이터 형식](types.md)
* [SQLite 핵심 함수](https://www.sqlite.org/lang_corefunc.html)
* [SQLite 집계 함수](https://www.sqlite.org/lang_aggfunc.html)
