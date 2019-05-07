---
title: F# 둘러보기
description: 이 자습서에서는 예제 코드를 사용하여 F# 프로그래밍 언어의 주요 기능을 살펴봅니다.
ms.date: 11/06/2018
ms.openlocfilehash: 4b3ec7fd2c42712440ea7d7045c560ab20390b45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61901732"
---
# <a name="tour-of-f"></a>F\# 둘러보기

F#에 대해 자세히 이해하려면 F# 코드를 읽고 작성하는 방법이 가장 좋습니다. 이 문서에서는 F# 언어의 주요 기능 중 일부를 둘러보고 컴퓨터에서 실행할 수 있는 코드 조각을 제공합니다. 개발 환경 설정에 대한 자세한 내용은 [시작하기](tutorials/getting-started/index.md)를 참조하십시오.

F#에 함수(function)와 유형(type)이라는 두 가지 기본 개념이 있습니다.  둘러보기에서는 이 두 가지 개념에 해당하는 언어의 기능을 강조합니다.

## <a name="executing-the-code-online"></a>온라인에서 코드 실행

F#이 컴퓨터에 설치되지 않았다면 [Fable REPL](https://fable.io/repl/)을 사용하여 온라인의 모든 샘플을 실행할 수 없습니다. Fable은 F#과 유사하며 브라우저에서 직접 실행할 수 있습니다. REPL에서 다음에 나오는 예제를 보기 위해서는 Fable REPL의 왼쪽 메뉴 바에서 **Samples > Learn > Tour of F#** 를 확인하세요.

## <a name="functions-and-modules"></a>함수와 모듈

F# 프로그램의 가장 기본적인 부분은 ***모듈***로 구성된 ***함수***입니다.  [함수](language-reference/functions/index.md)는 입력에 대한 작업으로 출력을 생성하고, F#에서 작업을 그룹화하는 기본 방식인 [모듈](language-reference/modules.md)로 구성됩니다.  [`let` 바인딩](language-reference/functions/let-bindings.md)을 사용하여 정의하며, 함수 이름을 지정하고 해당 인수를 정의할 수 있습니다.

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` 바인딩 이름으로 유사한 다른 언어에서 변수에 값을 바인딩하는 방법을 수도 있습니다.  `let` 바인딩은 ***변경할 수 없는*** 기본적으로 값 또는 함수 이름에 바인딩된 후 변경할 수 없습니다 즉 원위치 합니다.  이 변수는 다른 언어로 대조적 ***변경할 수 있는***, 즉 해당 값에서에서 변경할 수 있습니다 언제 든 지 시간입니다.  변경할 수 있는 바인딩을 필요로 하는 경우 사용할 수 있습니다 `let mutable ...` 구문입니다.

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>숫자, 부울 및 문자열

.NET 언어로, F# 지원 동일한 기본 [기본 형식](language-reference/primitive-types.md) .NET에 존재 하는 합니다.

다양 한 숫자 형식은 F#의 표현 됩니다 다음과 같습니다.

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

부울 값 이며 다음과 같은 기본 조건부 논리를 수행 합니다. 여기서:

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

어떤 basic 다음과 같습니다 [문자열](language-reference/strings.md) 조작 다음과 같습니다.

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>튜플

[튜플](language-reference/tuples.md) F#에서는 큰 문제가 됩니다.  이들은 자체 값으로 취급 될 수 있는 명명 되지 않은 않았지만 순서가 지정 된 값의 그룹입니다.  다른 값에서 집계 된 값으로 생각 합니다.  편리 하 게 함수에서 여러 값을 반환 하거나 임시 편의 대 한 값 그룹화와 같은 다양 한 용도로 갖습니다.

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

F# 4.1을 기준으로 만들 수도 있습니다 `struct` 튜플.  이러한도 완벽 하 게 상호 작용도 C# 7/Visual Basic 15 튜플 `struct` 튜플.

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

반드시 `struct` 튜플은 값 형식, 튜플 참조를 암시적으로 변환할 수 없으므로 또는 그 반대의 경우도 마찬가지입니다.  참조 및 구조체 튜플 간에 명시적으로 변환 해야 합니다.

## <a name="pipelines-and-composition"></a>파이프라인 및 컴퍼지션

와 같은 연산자를 파이프할 `|>` F#의 데이터를 처리 하는 경우 널리 사용 됩니다. 이러한 연산자는 "파이프라인" 함수의 유연한 방식으로 설정할 수 있도록 하는 함수입니다. 다음 예제에서는 간단한 기능 파이프라인 빌드를 이러한 연산자를 활용할 수는 어떻게 과정을 안내 합니다.

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

앞의 예제 수 목록 처리 함수를 첫 번째 클래스 함수를 포함 하 여 F#의 많은 기능을 사용 하 고 [부분 응용 프로그램](language-reference/functions/index.md#partial-application-of-arguments)합니다. 각 이러한 개념에 대 한 심층적 이해가, 다소 고급 될 수 있지만 명확 해야 하는 방법을 쉽게 파이프라인을 빌드할 때 데이터를 처리 하는 데 함수를 사용할 수 있습니다.

## <a name="lists-arrays-and-sequences"></a>목록, 배열 및 시퀀스

목록, 배열 및 시퀀스는 F# 핵심 라이브러리의 세 가지 기본 컬렉션 형식입니다.

[나열](language-reference/lists.md) 은 정렬 된, 변경할 수 없는 컬렉션 같은 형식의 요소입니다.  즉, 많은 경우 열거형 하지만 임의 액세스 및 연결에 대 한 잘못 된 선택에 대 한 의미는 단일 연결 목록의 합니다.  일반적으로 사용 하지 않는 단일 연결 목록을 나타내는 목록 다른 인기 있는 언어로 나열 달리이 있습니다.

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[배열](language-reference/arrays.md) 은 고정 크기 *변경할 수 있는* 형식이 같은 요소의 컬렉션입니다.  요소의 빠른 임의 액세스를 지원 하며 F# 목록에서는 방금 연속 된 메모리 블록을 이기 때문에 보다 빠릅니다.

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[시퀀스](language-reference/sequences.md) 동일한 형식의 모든 요소를 논리적으로 연속 됩니다.  이들은 목록과 배열 되는 모든 논리적 일련의 요소에 "보기"의 수는 보다 일반적인 형식입니다.  또한 될까요 될 수 있으므로 ***지연***, 즉, 요소는 필요할 때에 계산할 수 있습니다.

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>재귀 함수

컬렉션 또는 요소의 시퀀스로 처리는 사용 하 여 일반적으로 수행 됩니다 [재귀](language-reference/functions/index.md#recursive-functions) F#에 있습니다.  F#에 루프 및 명령형 프로그래밍에 대 한 지원으로 재귀는 정확성을 보장 하기 위해 더 쉽기 때문에 기본 설정 합니다.

> [!NOTE]
> 다음 예제에서는 패턴 일치를 통해 사용 된 `match` 식입니다.  이 문서의 뒷부분에서이 기본 구문을 다룹니다.

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F# 또한가 마무리 호출 최적화에 대 한 전체 지원 있습니다 빠른 루프 구문으로는 재귀 호출을 최적화할 수 있습니다.

## <a name="record-and-discriminated-union-types"></a>레코드와 구별 된 공용 구조체 형식

레코드 및 공용 구조체 형식을 F# 코드에 사용 되는 두 가지 기본 데이터 형식이 되며 일반적으로 가장 좋은 방법은 F# 프로그램에서 데이터를 나타냅니다.  이렇게 하면 해당 클래스와 유사 다른 언어로, 주요 차이점 중 하나 이지만 구조적 같음 의미 체계를가지고 있다고 합니다.  즉, "고유 하 게" 비교할 수는 같음 간단-다른 같으면 하나 선택 합니다.

[레코드](language-reference/records.md) 선택적 멤버 (예: 메서드)를 사용 하 여 명명 된 값의 집계 됩니다.  C# 또는 Java에 익숙한 경우 다음이 있어야 Poco 또는 Pojo-비슷한 의례 줄이고 구조적 일치성이 포함 된 합니다.

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

F# 4.1을 기준으로 나타낼 수도 있습니다 레코드는 `struct`s입니다.  사용 하 여 `[<Struct>]` 특성:

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[구별 된 공용 구조체 (DUs)](language-reference/discriminated-unions.md) 명명 된 폼의 경우 숫자가 될 수 있는 값입니다.  데이터 형식에 저장 된 여러 고유 값 중 하나일 수 있습니다.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

DUs로 이용할 수 있습니다 *단일 사례 구별 된 공용 구조체*기본 형식을 통해 모델링 되는 도메인과 수 있도록 합니다.  종종, 문자열 및 다른 기본 형식과 무언가 나타내는 데 사용 됩니다 하 고 특정 의미를 지정 하므로 됩니다.  그러나 기본 데이터 표현의 실수로 잘못 된 값을 할당할 때 발생할 수 있습니다!  각 유형의 단일 사례 공용 구조체의 고유 정보를 나타내는이 시나리오의 정확성을 적용할 수 있습니다.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

에 단일 사례 구별 된 공용 구조체, 기본 값을 가져오려면 위의 샘플에서 보여 주는 것 처럼 명시적으로 unwrap 해야 있습니다.

또한 DUs 기능도 재귀 정의 트리 및 본질적으로 재귀적 데이터를 쉽게 표현할 수 있습니다.  예를 들어 다음과 같습니다 사용 하 여 이진 검색 트리를 표시 하는 방법 `exists` 및 `insert` 함수입니다.

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

DUs 데이터 형식에서 트리의 재귀 구조를 나타낼 수 있으므로이 재귀 구조에서 작동 간단 하 고 정확성을 보장 합니다.  또한 아래와 같이 패턴 일치에 지원 됩니다.

또한 DUs로 나타낼 수 있습니다 `struct`와 s는 `[<Struct>]` 특성:

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

그러나 두 가지 주요 작업을 수행할 때는 염두에:

1. DU 구조체를 재귀적으로 정의 일 수 없습니다.
2. DU 구조체에는 각 해당 사례에 대 한 고유한 이름을 가져야 합니다.

위의 따르지 컴파일 오류가 발생 합니다.

## <a name="pattern-matching"></a>패턴 일치

[일치 패턴](language-reference/pattern-matching.md) 기능은 F# 언어는 F# 형식에서 작동 하는 것에 대 한 정확성을 사용 하도록 설정 합니다.  위의 샘플에서 이와 매우 많은 `match x with ...` 구문입니다.  이 구조를 사용 하면 컴파일러에 일치 하는 철저 한 패턴을 통해 데이터 형식을 사용 하는 경우 모든 가능한 사례에 대 한 계정 수를 적용할 데이터 형식의 "모양"를 이해할 수 있습니다.  올바른지, 매우 강력한 이며 컴파일 시간에 런타임 문제가 일반적으로 될 항목이 "리프트"를 영리 하 게 사용할 수 있습니다.

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

사용 하는 것을 알았을 것은 `_` 패턴입니다.  이 [와일드 카드 패턴](language-reference/pattern-matching.md#wildcard-pattern), "신경을 어떤 대상을" 설명할 방법이 있는 합니다.  실수로 철저 한 패턴 일치를 무시 하 고 더 이상 사용 하 여 주의 하지 않으면 컴파일 타임 사항이에서 이점을 얻을 수 편리 하기는 하지만 `_`합니다.  분해 된 형식의 특정 부분에 신경 때 가장 적합 하면 패턴 일치 식의에서 의미 있는 모든 사례는 열거 된 경우 일치 또는 마지막 절을 패턴입니다.

[활성 패턴](language-reference/active-patterns.md) 패턴 일치를 사용 하는 다른 강력한 구성 됩니다.  그러면 패턴 일치 호출 사이트에서 분해 하는 사용자 지정 양식, 입력된 데이터를 분할할 수 있습니다.  또한 매개 변수화 할 수, 있으므로 다음 파티션 함수로 정의 합니다.  활성 패턴을 지원 하기 위해 이전 예제를 확장 합니다. 다음과 같이 표시 됩니다.

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>선택적 형식

구별 된 공용 구조체 유형의 특수 경우는 옵션 종류를 F# 핵심 라이브러리의 일부는 매우 유용 합니다.

[옵션 형식](language-reference/options.md) 는 두 가지 경우 중 하나를 나타내는 형식: 값 또는 전혀 아무 작업도 수행 합니다.  값 수 또는 특정 작업으로 나타나지 않을 수 있는 모든 시나리오에서 사용 됩니다.  이 강제로 수행 런타임 별로 중요 하지 않고 컴파일 시간 문제가 있으므로 두 경우에 대 한 계정 수 있습니다.  Api에서 자주 사용 되 이러한 위치 `null` 에 대해 걱정할 필요가 없도록 아무것도 대신 나타내는 데 사용 됩니다 `NullReferenceException` 대부분에서입니다.

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>측정 단위

F#의 형식 시스템의 고유한 특징 중 하나는 측정 단위를 통해 숫자 리터럴에 대 한 컨텍스트를 제공할 수 있습니다.

[측정 단위](language-reference/units-of-measure.md) 미터로 등의 단위를 숫자 형식에 연결할 수 있도록 및 있는 함수에서 작업을 수행 숫자 리터럴 대신 단위입니다.  그러면 컴파일러가 특정 컨텍스트에서 의미가에 전달 된 숫자 리터럴 형식에 해당 종류의 작업을 사용 하 여 연결 된 런타임 오류를 없앰으로써 확인할 수 있습니다.

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

F# 핵심 라이브러리는 많은 SI 단위 유형 및 변환 단위를 정의합니다.  자세한 내용은 체크 아웃 합니다 [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)합니다.

## <a name="classes-and-interfaces"></a>클래스 및 인터페이스

F#에.NET 클래스에 대 한 전체 지원을 [인터페이스](language-reference/interfaces.md), [추상 클래스](language-reference/abstract-classes.md)합니다 [상속](language-reference/inheritance.md)등.

[클래스](language-reference/classes.md) .NET 개체를 나타내는 형식인 속성, 메서드 및 이벤트를 사용할 수 있는 해당 [멤버](language-reference/members/index.md)합니다.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

제네릭 클래스 정의 매우 간단 이기도 합니다.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

인터페이스를 구현 하려면 사용할 수 있습니다 `interface ... with` 구문 요소나 [개체 식](language-reference/object-expressions.md)합니다.

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>사용 형식

중요 한 질문에 잠재 고객 클래스, 레코드, 구분 된 공용 구조체 및 튜플의 존재 여부: 사용 해야 하는?  요소와 마찬가지로 대부분의 상황에서에서 답변 상황에 따라 달라 집니다.

튜플 함수에서 여러 값을 반환 하 고 임시 집계 값을 사용 하 여 자체 값으로 탁월 합니다.

레코드는 "의 다음 단계인" 튜플, 레이블 및 선택적 멤버에 대 한 지원 이라는 것입니다.  이러한 옵션은 데이터 전송 중에 프로그램을 통해 격식이 표현을 유용 합니다.  구조적 같음에 있기 때문에 비교를 사용 하 여 쉽게 사용할 수는 있습니다.

구별 된 공용 구조체는 여러 가지 이지만 핵심 혜택에 대 한 모든 가능한 "모양" 데이터를 가질 수 있는 계정에 패턴 일치와 함께에서 사용 해야 할 수 있습니다.  

클래스는 상당히 많은 정보를 나타내는 한도 기능에 해당 정보를 연결 해야 하는 등의 이유로 적합 합니다.  일반적으로 일부 데이터를 개념적으로 관련이 있는 기능이 클래스 및 개체 지향 프로그래밍의 원리를 사용 하 여 경우에 큰 이점이 있습니다.  클래스는 또한 기본 데이터 형식을 C# 및 Visual Basic의 경우와 상호 작용할 때 거의 모든 항목에 대 한 클래스를 사용 하는 이러한 언어입니다.

## <a name="next-steps"></a>다음 단계

지금까지 살펴본 언어의 주요 기능 중 일부는 이제 첫 번째 F# 프로그램 작성을 준비 해야 합니다!  체크 아웃 [Getting Started](tutorials/getting-started/index.md) 에 개발 환경을 설정 하 여 일부 코드를 작성 하는 방법을 알아봅니다.

자세히 학습을 위한 다음 단계를 원하는 수 있지만 것이 좋습니다 [에 함수형 프로그래밍 소개 F# ](introduction-to-functional-programming/index.md) 핵심 함수형 프로그래밍 개념에 익숙하지 가져오려고 합니다.  이러한 강력한 프로그램 F# 빌드에 필수적인 됩니다.

또한 체크 아웃 합니다 [F# 언어 참조](language-reference/index.md) F#에서 광범위 한 개념적 콘텐츠를 보려면.
