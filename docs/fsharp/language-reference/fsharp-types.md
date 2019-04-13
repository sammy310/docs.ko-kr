---
title: F# 형식
description: 에 사용 되는 유형에 대해 알아봅니다 F# 방법과 F# 형식 이름이 지정 되 고 설명 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: b48376c80b48df210bf7bc699a769d40fec60864
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193592"
---
# <a name="f-types"></a>F# 형식

이 항목에서 사용 되는 형식에 설명 합니다 F# 방법과 F# 형식 이름이 지정 되 고 설명 합니다.

## <a name="summary-of-f-types"></a>요약 F# 형식
일부 형식으로 간주 됩니다 *기본 형식*를 부울 형식과 같은 `bool` 및 바이트 및 문자 형식을 포함 하는 다양 한 크기의 정수 계열 및 부동 소수점 형식입니다. 이러한 형식에 설명 되어 있습니다 [기본 형식](primitive-types.md)합니다.

다른 언어에 기본 제공 되는 튜플, 목록, 배열, 시퀀스, 레코드를 포함할 형식과 구별 된 공용 구조체입니다. 학습 되며 다른.NET 언어를 사용한 경험이 있는 경우 F#에서 이러한 각 형식에 대 한 항목을 읽어보세요. 이러한 형식에 대 한 자세한 정보에 대 한 링크에 포함 된 합니다 [관련 항목](https://msdn.microsoft.com/library/#rel) 이 항목의 섹션입니다. 이러한 F#-특정 형식을 함수형 프로그래밍 언어에 공통 되는 프로그래밍의 스타일을 지원 합니다. 모듈에 연결 된 대부분의 이러한 형식에는 F# 이러한 형식에서 일반 작업을 지 원하는 라이브러리입니다.

매개 변수 형식에 대 한 정보를 포함 하 고 형식을 반환 하는 함수 형식입니다.

.NET Framework는 개체 형식, 인터페이스 형식, 대리자 형식 및 다른 사용자의 소스입니다. 다른.NET 언어의 경우와 마찬가지로 고유한 개체 형식을 정의할 수 있습니다.

또한 F# 코드 라는 별칭을 정의할 수 있습니다 *형식 약어*에 형식에 대 한 대체 이름. 형식을 나중에 변경 될 수 있습니다 및 형식에 따라 달라 지는 코드를 변경 하지 않으려는 경우 형식 약어를 사용할 수 있습니다. 또는 코드를 읽고 이해 하기 쉽게 만들 수 있는 형식에 대 한 이름으로 형식 약어를 사용할 수 있습니다.

F#염두에서 함수형 프로그래밍을 사용 하 여 설계 된 유용한 컬렉션 형식을 제공 합니다. 이 컬렉션 형식을 사용 스타일의 기능 보다는 코드를 작성할 수 있습니다. 자세한 내용은 [ F# 컬렉션 형식](fsharp-collection-types.md)합니다.

## <a name="syntax-for-types"></a>형식에 대 한 구문
F# 코드를 자주 작성 해야 할 형식 이름을 확인 해야 합니다. 모든 형식에는 구문 형식 및 형식 주석을, 추상 메서드 선언, 대리자 선언, 서명 및 다른 구문에 이러한 구문 형식을 사용 합니다. 인터프리터에서 새 프로그램 구문의 선언할 때마다 인터프리터는 해당 형식에 대 한 구문 및 구문 이름을 인쇄 합니다. 이 구문은 사용자 정의 형식에 대 한 식별자로만 또는 기본 제공 식별자와 이러한 수 있습니다 `int` 또는 `string`, 보다 복잡 한 형식에 대 한 구문은 복잡 하지만 합니다.

다음 표에서 구문에 대 한 측면을 보여 줍니다. F# 형식입니다.

|형식|형식 구문|예제|
|----|-----------|--------|
|기본 형식|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|집계 유형 (클래스, 구조체, 공용 구조체, 레코드, 열거형 및 등)|*type-name*|`System.DateTime`<br /><br />`Color`|
|형식 약어|*type-abbreviation-name*|`bigint`|
|정규화 된 형식|*namespaces.type-name*<br /><br />또는<br /><br />*modules.type-name*<br /><br />또는<br /><br />*namespaces.modules.type-name*|`System.IO.StreamWriter`|
|array|*type-name*[] or<br /><br />*type-name* array|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|2 차원 배열|*type-name*[,]|`int[,]`<br /><br />`float[,]`|
|3 차원 배열|*type-name*[,,]|`float[,,]`|
|tuple|*형식 name1* &#42; *형식-name2* 하는 중...|예를 들어 `(1,'b',3)` 형식이 `int * char * int`|
|제네릭 형식(generic type)|*type-parameter* *generic-type-name*<br /><br />또는<br /><br />*generic-type-name*&lt;*type-parameter-list*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|생성 된 형식 (제공 되는 특정 형식 인수가 있는 제네릭 형식)|*type-argument* *generic-type-name*<br /><br />또는<br /><br />*generic-type-name*&lt;*type-argument-list*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|단일 매개 변수가 있는 함수 형식|*parameter-type1* -&gt; *return-type*|사용 하는 함수는 `int` 반환을 `string` 형식이 `int -> string`|
|여러 매개 변수가 있는 함수 형식|*parameter-type1* -&gt; *parameter-type2* -&gt; ... -&gt; *return-type*|사용 하는 함수는 `int` 와 `float` 반환을 `string` 형식이 `int -> float -> string`|
|매개 변수로 고차 함수|(*function-type*)|`List.map` 형식이 `('a -> 'b) -> 'a list -> 'b list`|
|대리자(delegate)|대리자 *함수 형식*|`delegate of unit -> int`|
|유연한 형식|#*type-name*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>관련 항목

|항목|설명|
|-----|-----------|
|[기본 형식](primitive-types.md)|기본 제공 단순 형식과를 같은 정수 계열 형식, 부울 형식 및 문자 형식에 설명합니다.|
|[단위 형식](unit-type.md)|에 대해 설명 합니다 `unit` 형식, 형식 ()로 표시 됩니다 하 고 값이 한;에 해당 `void` 에서 C# 및 `Nothing` Visual Basic의 합니다.|
|[튜플](tuples.md)|쌍, 삼중 쌍, 상관에 그룹화 된 모든 형식의 연결 된 값으로 구성 된 형식인 튜플 형식을 설명 합니다.|
|[옵션](options.md)|옵션 형식을, 값 또는 비어 있을 수 있습니다 하는 형식에 설명 합니다.|
|[목록](lists.md)|정렬 된, 변경할 수 없는 일련의 요소는 목록에 설명 합니다. 동일한 형식의 모든 합니다.|
|[배열](arrays.md)|연속 된 메모리 블록을 차지 하는 고정된 크기 같은 형식의 변경 가능한 요소를 정렬 된 배열을 설명 합니다.|
|[시퀀스](sequences.md)|논리적으로 연속 된 값을 나타내는 시퀀스 유형을 설명 합니다. 개별 값이 필요한 경우에 계산 됩니다.|
|[레코드](records.md)|명명 된 값의 작은 집계 레코드 형식을 설명합니다.|
|[구별된 공용 구조체](discriminated-unions.md)|구별 된 공용 구조체 유형을, 값에 가능한 형식의 집합 중 하나가 될 수 있습니다 유형 설명 합니다.|
|[함수](functions/index.md)|함수 값을 설명합니다.|
|[클래스](classes.md)|.NET 참조 형식에 해당 하는 개체 형식을 클래스 형식을 설명 합니다. 클래스 형식 멤버, 속성, 구현 된 인터페이스 및 기본 형식을 포함할 수 있습니다.|
|[구조체](structures.md)|에 대해 설명 합니다 `struct` 형식,.NET 값 형식에 해당 하는 개체 형식입니다. `struct` 형식은 일반적으로 데이터의 작은 집계를 나타냅니다.|
|[인터페이스](interfaces.md)|특정 기능을 제공 하지만 데이터가 포함 되지 않은 멤버 집합이 나타내는 형식을 인터페이스 형식을 설명 합니다. 인터페이스 형식이 유용할 개체 형식에 의해 구현 되어야 합니다.|
|[대리자](delegates.md)|함수 개체를 나타내는 대리자 형식을 설명 합니다.|
|[열거형](enumerations.md)|열거형을, 명명 된 값 집합에 속하는 해당 값에 설명 합니다.|
|[특성](attributes.md)|다른 형식에 대 한 메타 데이터를 지정 하는 데 사용 되는 특성을 설명 합니다.|
|[예외 형식](exception-handling/exception-types.md)|오류 정보를 지정 하는 예외를 설명 합니다.|
