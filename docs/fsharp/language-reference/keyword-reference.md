---
title: 키워드 참조
description: 모든 F# 언어 키워드에 대한 정보에 대한 링크를 찾습니다.
f1_keywords:
- new_FS
- use_FS
- end_FS
- lsl_FS
- exception_FS
- asr_FS
- if_FS
- internal_FS
- default_FS
- in_FS
- lsr_FS
- open_FS
- static_FS
- assert_FS
- match_FS
- land_FS
- with_FS
- inherit_FS
- mutable_FS
- downto_FS
- false_FS
- sig_FS
- and_FS
- true_FS
- namespace_FS
- public_FS
- lxor_FS
- val_FS
- void_FS
- downcast_FS
- function_FS
- while_FS
- for_FS
- class_FS
- done_FS
- to_FS
- module_FS
- let_FS
- delegate_FS
- abstract_FS
- then_FS
- when_FS
- lazy_FS
- try_FS
- inline_FS
- do_FS
- upcast_FS
- begin_FS
- base_FS
- fun_FS
- struct_FS
- as_FS
- extern_FS
- null_FS
- lor_FS
- return_FS
- mod_FS
- private_FS
- of_FS
- or_FS
- member_FS
- type_FS
- rec_FS
- elif_FS
- override_FS
- interface_FS
- yield_FS
- else_FS
- finally_FS
- global_FS
- select_FS
- use!_FS
dev_langs:
- FSharp
ms.date: 11/04/2019
ms.openlocfilehash: 34959f471406643e85990c2c80a38a684759a7f9
ms.sourcegitcommit: b16eacb6f94a5b601882a861ad17cc5470a8d5d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80352315"
---
# <a name="keyword-reference"></a>키워드 참조

이 항목에는 모든 F# 언어 키워드에 대한 정보에 대한 링크가 포함되어 있습니다.

## <a name="f-keyword-table"></a>F# 키워드 표

다음 표에서는 모든 F# 키워드를 알파벳 순으로 표시하고 자세한 정보가 포함된 관련 항목에 대한 간략한 설명 및 링크를 보여 주어집니다.

|키워드|링크|설명|
|-------|----|-----------|
|`abstract`|[멤버](./members/index.md)<br /><br />[추상 클래스](abstract-classes.md)|선언된 형식에 구현이 없거나 가상이며 기본 구현이 있는 메서드를 나타냅니다.|
|`and`|[`let`바인딩](./functions/let-bindings.md)<br /><br />[레코드](records.md)<br /><br />[멤버](./members/index.md)<br /><br />[제약 조건](./generics/constraints.md)|상호 재귀 바인딩 및 레코드, 속성 선언 및 제네릭 매개 변수에 대한 여러 제약 조건에 사용됩니다.|
|`as`|[클래스](classes.md)<br /><br />[패턴 일치](Pattern-Matching.md)|현재 클래스 개체에 개체 이름을 지정하는 데 사용됩니다. 또한 패턴 일치 내에서 전체 패턴에 이름을 지정하는 데 사용됩니다.|
|`assert`|[어설션](assertions.md)|디버깅 하는 동안 코드를 확인 하는 데 사용 됩니다.|
|`base`|[클래스](classes.md)<br /><br />[상속](inheritance.md)|기본 클래스 개체의 이름으로 사용됩니다.|
|`begin`|[자세한 구문](verbose-syntax.md)|자세한 구문에서 코드 블록의 시작을 나타냅니다.|
|`class`|[클래스](classes.md)|자세한 구문에서 클래스 정의의 시작을 나타냅니다.|
|`default`|[멤버](./members/index.md)|추상 메서드의 구현을 나타냅니다. 가상 메서드를 만드는 추상 메서드 선언과 함께 사용됩니다.|
|`delegate`|[대리자](delegates.md)|대리자를 선언하는 데 사용됩니다.|
|`do`|[do 바인딩](./functions/do-bindings.md)<br /><br />[루프: `for...to` 식](loops-for-to-expression.md)<br /><br />[루프: `for...in` 식](loops-for-in-expression.md)<br /><br />[루프: `while...do` 식](loops-while-do-expression.md)|반복 구문 또는 명령적 코드를 실행하는 데 사용됩니다.|
|`done`|[자세한 구문](verbose-syntax.md)|자세한 구문에서 루핑 식에서 코드 블록의 끝을 나타냅니다.|
|`downcast`|[캐스팅 및 변환](casting-and-conversions.md)|상속 체인에서 더 낮은 유형으로 변환하는 데 사용됩니다.|
|`downto`|[루프: `for...to` 식](loops-for-to-expression.md)|역으로 `for` 계산할 때 사용되는 식입니다.|
|`elif`|[조건식:`if...then...else`](conditional-expressions-if-then-else.md)|조건부 분기에 사용됩니다. 의 `else if`짧은 형태입니다.|
|`else`|[조건식:`if...then...else`](conditional-expressions-if-then-else.md)|조건부 분기에 사용됩니다.|
|`end`|[구조체](structures.md)<br /><br />[구별된 공용 구조체](discriminated-unions.md)<br /><br />[레코드](records.md)<br /><br />[형식 확장](type-extensions.md)<br /><br />[자세한 구문](verbose-syntax.md)|형식 정의 및 형식 확장에서 멤버 정의 섹션의 끝을 나타냅니다.<br /><br />자세한 구문에서 키워드로 시작하는 코드 블록의 끝을 지정하는 `begin` 데 사용됩니다.|
|`exception`|[예외 처리](./exception-handling/index.md)<br /><br />[예외 형식](./exception-handling/exception-types.md)|예외 형식을 선언하는 데 사용됩니다.|
|`extern`|[외부 함수](./functions/external-functions.md)|선언된 프로그램 요소가 다른 이진 또는 어셈블리에 정의됨을 나타냅니다.|
|`false`|[기본 유형](basic-types.md)|부울 리터럴로 사용됩니다.|
|`finally`|[예외: `try...finally` 식](./exception-handling/the-try-finally-expression.md)|함께 `try` 사용하면 예외가 발생하는지 여부에 관계없이 실행되는 코드 블록을 소개합니다.|
|`fixed`|[고정](fixed.md)|스택에서 포인터를 "고정"하여 가비지가 수집되지 않도록 하는 데 사용됩니다.|
|`for`|[루프: `for...to` 식](loops-for-to-expression.md)<br /><br />[루프: for...in 식](loops-for-in-expression.md)|루핑 구문에 사용됩니다.|
|`fun`|[람다 표현식: `fun` 키워드](./functions/lambda-expressions-the-fun-keyword.md)|익명 함수라고도 하는 람다 식에 사용됩니다.|
|`function`|[일치 식](match-expressions.md)<br /><br />[람다 표현: 재미있는 키워드](./functions/lambda-expressions-the-fun-keyword.md)|단일 인수에 패턴이 `fun` 일치하는 lambda 식의 키워드 및 `match` 식에 대한 짧은 대안으로 사용됩니다.|
|`global`|[네임스페이스](namespaces.md)|최상위 .NET 네임스페이스를 참조하는 데 사용됩니다.|
|`if`|[조건식:`if...then...else`](conditional-expressions-if-then-else.md)|조건부 분기 구문에 사용됩니다.|
|`in`|[루프: for...in 식](loops-for-in-expression.md)<br /><br />[자세한 구문](verbose-syntax.md)|시퀀스 식및 자세한 구문에서 식을 바인딩과 구분하는 데 사용됩니다.|
|`inherit`|[상속](inheritance.md)|기본 클래스 또는 기본 인터페이스를 지정하는 데 사용됩니다.|
|`inline`|[함수](./functions/index.md)<br /><br />[인라인 함수](./functions/inline-functions.md)|호출자의 코드에 직접 통합되어야 하는 함수를 나타내는 데 사용됩니다.|
|`interface`|[인터페이스](interfaces.md)|인터페이스를 선언하고 구현하는 데 사용됩니다.|
|`internal`|[액세스 제어](access-control.md)|멤버가 어셈블리 내부에 표시되지만 외부로 표시되지 않도록 지정하는 데 사용됩니다.|
|`lazy`|[Lazy 식](lazy-expressions.md)|결과가 필요한 경우에만 수행할 식을 지정하는 데 사용됩니다.|
|`let`|[`let`바인딩](./functions/let-bindings.md)|이름을 값이나 함수에 연결하거나 바인딩하는 데 사용됩니다.|
|`let!`|[비동기 워크플로](asynchronous-workflows.md)<br /><br />[계산 식](computation-expressions.md)|비동기 워크플로에서 비동기 계산의 결과에 이름을 바인딩하거나 다른 계산 식에서 계산 형식의 결과에 이름을 바인딩하는 데 사용됩니다.|
|`match`|[일치 식](match-expressions.md)|값을 패턴과 비교하여 분기하는 데 사용됩니다.|
|`match!`|[계산 식](computation-expressions.md#match)|계산 식및 패턴 일치 결과에 대한 호출을 인라인하는 데 사용됩니다.|
|`member`|[멤버](./members/index.md)|개체 형식에서 속성 또는 메서드를 선언하는 데 사용됩니다.|
|`module`|[모듈](modules.md)|이름을 관련 형식, 값 및 함수 그룹과 연결하여 논리적으로 다른 코드와 분리하는 데 사용됩니다.|
|`mutable`|[let 바인딩](./functions/let-bindings.md)|변수, 즉 변경할 수 있는 값을 선언하는 데 사용됩니다.|
|`namespace`|[네임스페이스](namespaces.md)|이름을 관련 형식 및 모듈 그룹과 연결하여 논리적으로 다른 코드와 분리하는 데 사용됩니다.|
|`new`|[생성자](./members/constructors.md)<br /><br />[제약 조건](./generics/constraints.md)|개체를 만들거나 만들 수 있는 생성자 선언, 정의 또는 호출하는 데 사용됩니다.<br /><br />또한 형식에 특정 생성자가 있어야 함을 나타내기 위해 제네릭 매개 변수 제약 조건에서 사용됩니다.|
|`not`|[기호 및 연산자 참조](./symbol-and-operator-reference/index.md)<br /><br />[제약 조건](./generics/constraints.md)|실제로 키워드가 아닙니다. 그러나 `not struct` 조합에서 일반 매개 변수 제약 조건으로 사용 됩니다.|
|`null`|[Null 값](./values/null-values.md)<br /><br />[제약 조건](./generics/constraints.md)|개체가 없는 경우를 나타냅니다.<br /><br />일반 매개 변수 제약 조건에도 사용됩니다.|
|`of`|[구별된 공용 구조체](discriminated-unions.md)<br /><br />[대리자](delegates.md)<br /><br />[예외 형식](./exception-handling/exception-types.md)|값 범주의 범주 유형과 대리자 및 예외 선언을 나타내는 데 사용되는 구별된 공용 구조체에서 사용됩니다.|
|`open`|[가져오기 선언: `open` 키워드](import-declarations-the-open-keyword.md)|네임스페이스 또는 모듈의 내용을 자격 없이 사용할 수 있도록 하는 데 사용됩니다.|
|`or`|[기호 및 연산자 참조](./symbol-and-operator-reference/index.md)<br /><br />[제약 조건](./generics/constraints.md)|부울 `or` 연산자로 부울 조건과 함께 사용됩니다. `||`과 동일합니다.<br /><br />멤버 제약 조건에도 사용됩니다.|
|`override`|[멤버](./members/index.md)|기본 버전과 다른 추상 또는 가상 메서드버전을 구현하는 데 사용됩니다.|
|`private`|[액세스 제어](access-control.md)|멤버에 대한 액세스를 동일한 형식 또는 모듈의 코드로 제한합니다.|
|`public`|[액세스 제어](access-control.md)|형식 외부에서 멤버에 액세스할 수 있습니다.|
|`rec`|[함수](./functions/index.md)|함수가 재귀임을 나타내는 데 사용됩니다.|
|`return`|[비동기 워크플로](Asynchronous-Workflows.md)<br /><br />[계산 식](computation-expressions.md)|계산 식의 결과로 제공할 값을 나타내는 데 사용됩니다.|
|`return!`|[계산 식](computation-expressions.md)<br /><br />[비동기 워크플로](asynchronous-workflows.md)|계산식을 나타내는 데 사용됩니다.|
|`select`|[쿼리 식](query-expressions.md)|쿼리 식에서 추출할 필드 또는 열을 지정하는 데 사용됩니다. 이 키워드는 컨텍스트 키워드로, 실제로 예약된 단어가 아니며 적절한 컨텍스트에서 만 키워드처럼 작동합니다.|
|`static`|[멤버](./members/index.md)|형식의 인스턴스 없이 호출할 수 있는 메서드 또는 속성 또는 형식의 모든 인스턴스 간에 공유 되는 값 멤버를 나타내는 데 사용 됩니다.|
|`struct`|[구조체](structures.md)<br /><br /> [튜플](tuples.md)<br/><br/>[제약 조건](./generics/constraints.md)|구조 체를 선언 하는 데 사용 됩니다.<br /><br/>구조형 튜플을 지정하는 데 사용됩니다.<br/><br />일반 매개 변수 제약 조건에도 사용됩니다.<br /><br />모듈 정의에서 OCaml 호환성에 사용됩니다.|
|`then`|[조건식:`if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[생성자](./members/constructors.md)|조건식에 사용됩니다.<br /><br />또한 개체 구성 후 부작용을 수행하는 데 사용됩니다.|
|`to`|[루프: `for...to` 식](loops-for-to-expression.md)|범위를 `for` 나타내는 루프에 사용됩니다.|
|`true`|[기본 유형](basic-types.md)|부울 리터럴로 사용됩니다.|
|`try`|[예외: try...with 식](./exception-handling/the-try-with-expression.md)<br /><br />[예외: try...finally 식](./exception-handling/the-try-finally-expression.md)|예외를 생성할 수 있는 코드 블록을 도입하는 데 사용됩니다. 함께 `with` 사용하거나 `finally`.|
|`type`|[F# 형식](fsharp-types.md)<br /><br />[클래스](classes.md)<br /><br />[레코드](records.md)<br /><br />[구조체](structures.md)<br /><br />[열거형](enumerations.md)<br /><br />[구별된 공용 구조체](discriminated-unions.md)<br /><br />[형식 약어](type-abbreviations.md)<br /><br />[측정 단위](units-of-measure.md)|클래스, 레코드, 구조체, 구별된 공용 구조체, 열거형 유형, 측정 단위 또는 약어 유형을 선언하는 데 사용됩니다.|
|`upcast`|[캐스팅 및 변환](casting-and-conversions.md)|상속 체인에서 더 높은 유형으로 변환하는 데 사용됩니다.|
|`use`|[리소스 관리: `use` 키워드](resource-management-the-use-keyword.md)|`let` 리소스를 해제하기 위해 `Dispose` 호출해야 하는 값 대신 사용됩니다.|
|`use!`|[계산 식](computation-expressions.md)<br /><br />[비동기 워크플로](asynchronous-workflows.md)|비동기 `let!` 워크플로 및 리소스 를 사용 하려면 호출 해야 `Dispose` 하는 값에 대 한 다른 계산 식 대신 사용 됩니다.|
|`val`|[명시적 필드: `val` 키워드](./members/explicit-fields-the-val-keyword.md)<br /><br />[시그니처](signature-files.md)<br /><br />[멤버](./members/index.md)|제한된 상황에서 값을 나타내거나 멤버를 선언하는 형식에 서명에 사용됩니다.|
|`void`|[기본 유형](basic-types.md)|.NET `void` 형식을 나타냅니다. 다른 .NET 언어와 상호 운용할 때 사용됩니다.|
|`when`|[제약 조건](./generics/constraints.md)|패턴 일치에 부울 조건 *(가시 때)에*사용 되며 제네릭 형식 매개 변수에 대 한 제약 조건 절을 소개 합니다.|
|`while`|[루프: `while...do` 식](loops-while-do-expression.md)|루핑 구문이 소개됩니다.|
|`with`|[일치 식](match-expressions.md)<br /><br />[개체 식](object-expressions.md)<br /><br />[레코드 식 복사 및 업데이트](copy-and-update-record-expressions.md)<br /><br />[형식 확장](type-extensions.md)<br /><br />[예외: `try...with` 식](./exception-handling/the-try-with-expression.md)|패턴 일치 `match` 식의 키워드와 함께 사용됩니다. 또한 개체 표현식, 레코드 복사 식 및 형식 확장에 사용되어 멤버 정의를 도입하고 예외 처리기를 도입합니다.|
|`yield`|[목록,](lists.md) [배열,](arrays.md) [시퀀스](sequences.md)|시퀀스에 대한 값을 생성하기 위해 목록, 배열 또는 시퀀스 식에 사용됩니다. 일반적으로 대부분의 상황에서 암시적이기 때문에 생략할 수 있습니다.|
|`yield!`|[계산 식](computation-expressions.md)<br /><br />[비동기 워크플로](asynchronous-workflows.md)|계산 식에 사용 되어 포함 된 계산 식에 대 한 결과 컬렉션에 주어진된 계산 식의 결과 포함 하는 데 사용 됩니다.|

다음 토큰은 OCaml 언어의 키워드이므로 F#에서 예약됩니다.

- `asr`
- `land`
- `lor`
- `lsl`
- `lsr`
- `lxor`
- `mod`
- `sig`

`--mlcompatibility` 컴파일러 옵션을 사용하는 경우 위의 키워드를 식별자로 사용할 수 있습니다.

다음 토큰은 F# 언어의 향후 확장을 위한 키워드로 예약됩니다.

- `atomic`
- `break`
- `checked`
- `component`
- `const`
- `constraint`
- `constructor`
- `continue`
- `eager`
- `event`
- `external`
- `functor`
- `include`
- `method`
- `mixin`
- `object`
- `parallel`
- `process`
- `protected`
- `pure`
- `sealed`
- `tailcall`
- `trait`
- `virtual`
- `volatile`

## <a name="see-also"></a>참조

- [F # 언어 참조](index.md)
- [기호 및 연산자 참조](./symbol-and-operator-reference/index.md)
- [컴파일러 옵션](compiler-options.md)
