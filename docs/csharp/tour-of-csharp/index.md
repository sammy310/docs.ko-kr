---
title: C# 둘러보기 - C# 가이드
description: C#을 처음 사용하시나요? 언어의 기본 사항에 대해 알아봅니다. 이 개요에서 시작합니다.
ms.date: 01/28/2021
ms.openlocfilehash: b58aed5e75be8c71df295506480a2d97c22675aa
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104915"
---
# <a name="a-tour-of-the-c-language"></a>C# 언어 둘러보기

C#(“씨샵”이라고 발음합니다.)은 형식이 안전한 최신 개체 지향 프로그래밍 언어입니다. 개발자는 C#을 사용하면 .NET 에코시스템에서 실행되는 다양한 형식의 안전하고 강력한 애플리케이션을 빌드할 수 있습니다. C#은 C 언어 제품군에서 시작되었으며 C, C++, Java 및 JavaScript 프로그래머에게 친숙할 것입니다. 이 둘러보기에서는 C# 8 이상 언어의 주요 구성 요소를 간략하게 설명합니다. 대화형 예제를 통해 언어를 살펴보려면 [C# 소개](./tutorials/index.md) 자습서를 사용해 보세요.

C#은 개체 지향, 구성 요소 지향 프로그래밍 언어입니다. C#은 이러한 개념을 직접적으로 지원하는 언어 구문을 제공함으로써 소프트웨어 구성 요소를 만들고 사용할 수 있는 자연 언어로 자리매김하게 되었습니다. 원본 이후로 C#은 새로운 워크로드를 지원하기 위한 기능 및 새로운 소프트웨어 디자인 사례를 추가했습니다.

여러 가지 C# 기능은 강력한 지속형 애플리케이션을 만드는 데 도움이 됩니다. [***가비지 수집** _](../../standard/garbage-collection/index.md)은 연결할 수 없고 사용되지 않는 개체에서 사용하는 메모리를 자동으로 회수합니다. [‘Nullable 형식’](../nullable-references.md)은 할당된 개체를 참조하지 않는 변수로부터 보호합니다. [‘예외 처리’](../programming-guide/exceptions/index.md)는 오류 검색 및 복구에 대한 구조적이고 확장 가능한 방법을 제공합니다. [‘람다 식’](../language-reference/operators/lambda-expressions.md)은 함수형 프로그래밍 기술을 지원합니다. [‘LINQ(언어 통합 쿼리)’](../linq/index.md) 구문은 모든 소스의 데이터로 작업하기 위한 일반적인 패턴을 만듭니다. [‘비동기 작업’](../programming-guide/concepts/async/index.md)에 대한 언어 지원은 분산 시스템을 빌드하기 위한 구문을 제공합니다. C#에는 [_통합 형식 시스템](../programming-guide/types/index.md)이 있습니다. `int` 및 `double`과 같은 기본 형식을 포함하는 모든 C# 형식은 단일 루트 `object`에서 상속됩니다. 모든 형식은 일반 작업 집합을 공유합니다. 모든 형식의 값을 일관된 방식으로 저장 및 전송하고 작업을 수행할 수 있습니다. 또한 C#은 사용자 정의 [참조 형식](../language-reference/builtin-types/reference-types.md) 및 [값 형식](../language-reference/builtin-types/value-types.md)을 모두 지원합니다. C#은 개체의 동적 할당 및 경량 구조체의 인라인 스토리지를 허용합니다. C#은 향상된 형식 안전성과 성능을 제공하는 제네릭 메서드 및 형식을 지원합니다. C#은 컬렉션 클래스의 구현자가 클라이언트 코드에 대한 사용자 지정 동작을 정의하는 데 사용할 수 있는 반복기를 제공합니다.

C#은 시간 경과에 따라 프로그램 및 라이브러리가 호환 가능한 방식으로 개선될 수 있도록 버전 관리를 강조합니다. 버전 관리 고려 사항의 직접적인 영향을 받은 C# 설계의 측면에는 별도의 `virtual` 및 `override` 한정자, 메서드 오버로드 확인 규칙 및 명시적 인터페이스 멤버 선언에 대한 지원이 포함됩니다.

## <a name="net-architecture"></a>.NET 아키텍처

C# 프로그램은 CLR(공용 언어 런타임)이라는 가상 실행 시스템이며 클래스 라이브러리 세트인 .NET에서 실행됩니다. CLR은 국제 표준인 CLI(공용 언어 인프라)를 Microsoft에서 구현한 것입니다. CLI는 언어와 라이브러리가 원활하게 함께 작동하는 실행 및 개발 환경을 만들기 위한 기초입니다.

C#으로 작성된 소스 코드는 CLI 사양을 준수하는 [IL(중간 언어)](../../standard/managed-code.md)로 컴파일됩니다. IL 코드와 리소스(예: 비트맵 및 문자열)는 일반적으로 .dll 확장명과 함께 어셈블리에 저장됩니다. 어셈블리는 어셈블리의 형식, 버전 및 문화에 대한 정보를 제공하는 매니페스트를 포함합니다.

C# 프로그램이 실행되면 어셈블리가 CLR에 로드됩니다. CLR은 JIT(Just-In-Time) 컴파일을 수행하여 IL 코드를 네이티브 기계어 명령으로 변환합니다. CLR은 자동 가비지 수집, 예외 처리 및 리소스 관리와 관련된 다른 서비스도 제공합니다. CLR에서 실행되는 코드는 “관리 코드”라고도 합니다. 즉, 특정 플랫폼을 대상으로 하는 네이티브 기계어로 컴파일되는 “비관리 코드”와는 반대됩니다.

언어 상호 운용성은 .NET의 주요 기능입니다. C# 컴파일러에서 생성된 IL 코드는 CTS(공용 형식 사양)를 따릅니다. C#에서 생성된 IL 코드는 F#의 .NET 버전, Visual Basic, C++ 또는 20개가 넘는 다른 CTS 규격 언어에서 생성된 코드와 상호 작용할 수 있습니다. 단일 어셈블리는 다른 .NET 언어로 작성된 여러 모듈을 포함할 수 있고 형식은 마치 같은 언어로 작성된 것처럼 서로를 참조할 수 있습니다.

런타임 서비스 외에도 .NET에는 광범위한 라이브러리가 포함되어 있습니다. 이러한 라이브러리는 다양한 워크로드를 지원합니다. 이들은 파일 입/출력부터 문자열 조작, XML 구문 분석, 웹 애플리케이션 프레임워크, Windows Forms 컨트롤에 이르기까지 모든 항목에 대해 다양하고 유용한 기능을 제공하는 네임스페이스로 구성됩니다. 전형적인 C# 애플리케이션은 .NET 클래스 라이브러리를 광범위하게 사용하여 일반적인 “배관” 작업을 처리합니다.

.NET에 대한 자세한 내용은 [.NET의 개요](../../core/introduction.md)를 참조하세요.

## <a name="hello-world"></a>Hello World

“Hello, World” 프로그램은 프로그래밍 언어를 소개하는 데 일반적으로 사용됩니다. C#에서는 다음과 같습니다.

:::code language="csharp" interactive="try-dotnet" source="./snippets/shared/HelloWorld.cs":::

“Hello, World” 프로그램은 `System` 네임스페이스를 참조하는 `using` 지시문으로 시작합니다. 네임스페이스는 계층적으로 C# 프로그램 및 라이브러리를 구성하는 방법을 제공합니다. 네임스페이스에는 형식 및 다른 네임스페이스가 포함됩니다. 예를 들어 `System` 네임스페이스에는 많은 형식(예: 프로그램에 참조되는 `Console` 클래스) 및 많은 다른 네임스페이스(예: `IO` 및 `Collections`)가 포함되어 있습니다. 지정된 네임스페이스를 참조하는 `using` 지시문을 사용하여 해당 네임스페이스의 멤버인 형식을 정규화되지 않은 방식으로 사용할 수 있습니다. `using` 지시문 때문에, 프로그램은 `Console.WriteLine`을 `System.Console.WriteLine`의 약식으로 사용할 수 있습니다.

“Hello, World” 프로그램에서 선언된 `Hello` 클래스에는 단일 멤버인 `Main` 메서드가 있습니다. `Main` 메서드는 `static` 한정자로 선언됩니다. 인스턴스 메서드는 키워드 `this`를 사용하여 특정 바깥쪽 개체 인스턴스를 참조할 수 있지만 정적 메서드는 특정 개체에 대한 참조 없이 작동합니다. 관례상 `Main`이라는 정적 메서드가 C# 프로그램의 진입점으로 사용됩니다.

프로그램의 출력은 `System` 네임스페이스에 있는 `Console` 클래스의 `WriteLine` 메서드에 의해 생성됩니다. 이 클래스는 기본적으로는 컴파일러에서 자동으로 참조되는 표준 클래스 라이브러리를 통해 제공됩니다.

## <a name="types-and-variables"></a>형식 및 변수

C#에는 두 가지 종류의 형식, 즉 *값 형식* 과 *참조 형식* 이 있습니다. 값 형식의 변수에는 해당 데이터가 직접 포함됩니다. 참조 형식의 변수에는 개체라고도 하는 데이터에 대한 참조가 저장됩니다. 참조 형식에서는 두 개의 변수가 같은 개체를 참조할 수 있고 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다. 값 형식에서는 변수가 자체적으로 데이터 사본을 갖고 있으며 한 변수에 대한 작업이 다른 변수에 영향을 미칠 수 없습니다(`ref` 및 `out` 매개 변수 변수 제외).

식별자는 변수 이름입니다. 식별자는 공백이 없는 유니코드 문자 시퀀스입니다. 식별자에 `@` 접두사가 있으면 C# 예약어일 수 있습니다. 예약어를 식별자로 사용하면 다른 언어와 상호 작용할 때 유용할 수 있습니다.

C#의 값 형식은 ‘단순 형식’, ‘열거형 형식’, ‘구조체 형식’, ‘null 허용 값 형식’, ‘튜플 값 형식’으로 세분화됩니다. C#의 참조 형식은 *클래스 형식*, *인터페이스 형식*, *배열 형식* 및 *대리자 형식* 으로 세분화됩니다.

다음 개요는 C#의 형식 시스템에 대한 개요를 제공합니다.

- [값 형식](../language-reference/builtin-types/value-types.md)
  - [단순 형식](../language-reference/builtin-types/value-types.md#built-in-value-types)
    - [부호 있는 정수](../language-reference/builtin-types/integral-numeric-types.md): `sbyte`, `short`, `int`, `long`
    - [부호 없는 정수](../language-reference/builtin-types/integral-numeric-types.md): `byte`, `ushort`, `uint`, `ulong`
    - [유니코드 문자](../../standard/base-types/character-encoding-introduction.md): `char`(UTF-16 코드 단위)
    - [IEEE 이진 부동 소수점](../language-reference/builtin-types/floating-point-numeric-types.md): `float`, `double`
    - [고정밀 10진수 부동 소수점](../language-reference/builtin-types/floating-point-numeric-types.md): `decimal`
    - 부울: `bool`은 부울 값, 즉 `true` 또는 `false`를 나타내는 값입니다.
  - [열거형 형식](../language-reference/builtin-types/enum.md)
    - `enum E {...}`의 사용자 정의 형식입니다. `enum` 형식은 명명된 상수가 있는 고유한 형식입니다. 모든 `enum` 형식은 8가지 정수 형식 중 하나인 내부 형식을 갖습니다. `enum` 형식의 값 집합은 내부 형식의 값 집합과 동일합니다.
  - [구조체 형식](../language-reference/builtin-types/struct.md)
    - `struct S {...}` 양식의 사용자 정의 형식
  - [Nullable 값 형식](../language-reference/builtin-types/nullable-value-types.md)
    - `null` 값을 갖는 다른 모든 값 형식의 확장
  - [튜플 값 형식](../language-reference/builtin-types/value-tuples.md)
    - `(T1, T2, ...)` 양식의 사용자 정의 형식
- [참조 형식](../language-reference/keywords/reference-types.md)
  - [클래스 형식](../language-reference/keywords/class.md)
    - 다른 모든 형식의 기본 클래스: `object`
    - [유니코드 문자열](../../standard/base-types/character-encoding-introduction.md): `string`(UTF-16 코드 유닛 시퀀스)
    - `class C {...}` 양식의 사용자 정의 형식
  - [인터페이스 형식](../language-reference/keywords/interface.md)
    - `interface I {...}` 양식의 사용자 정의 형식
  - [배열 형식](../programming-guide/arrays/index.md)
    - 1차원 배열, 다차원 배열, 가변 배열. 예: `int[]`, `int[,]`, `int[][]`
  - [대리자 형식](../language-reference/builtin-types/reference-types.md#the-delegate-type)
    - `delegate int D(...)` 양식의 사용자 정의 형식

C# 프로그램에서는 *형식 선언* 을 사용하여 새 형식을 만듭니다. 형식 선언은 새 형식의 이름과 멤버를 지정합니다. 사용자 정의가 가능한 C#의 6가지 형식 범주는 클래스 형식, 구조체 형식, 인터페이스 형식, 열거형 형식, 대리자 형식, 튜플 값 형식입니다.

- `class` 형식은 데이터 멤버(필드) 및 함수 멤버(메서드, 속성 및 기타)를 포함하는 데이터 구조를 정의합니다. 클래스 형식은 단일 상속 및 다형성과 파생된 클래스가 기본 클래스를 확장하고 특수화할 수 있는 메커니즘을 지원합니다.
- `struct` 형식은 데이터 멤버 및 함수 멤버로 구조체를 나타내는 클래스 형식과 유사합니다. 그러나 클래스와 달리 구조체는 값 형식이며 일반적으로 힙 할당이 필요하지 않습니다. 구조체 형식은 사용자 지정 상속을 지원하지 않으며 모든 구조체 형식은 `object` 형식으로부터 암시적으로 상속됩니다.
- `interface` 형식은 계약을 공용 멤버의 명명된 집합으로 정의합니다. `interface`를 구현하는 `class` 또는 `struct`는 인터페이스의 멤버 구현을 제공해야 합니다. `interface`는 여러 기본 인터페이스에서 상속될 수 있으며 `class` 또는 `struct`는 여러 인터페이스를 구현할 수 있습니다.
- `delegate` 형식은 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타내는 형식입니다. 대리자는 메서드를 변수에 할당되고 매개 변수로 전달될 수 있는 엔터티로 취급할 수 있도록 합니다. 대리자는 함수 언어에서 제공하는 함수 형식과 유사합니다. 대리자는 다른 언어의 함수 포인터와 개념이 비슷하지만 함수 포인터와 달리 대리자는 개체 지향적이며 형식이 안전한 방식입니다.

`class`, `struct`, `interface` 및 `delegate` 형식은 모두 제네릭을 지원하므로 다른 형식으로 매개 변수화할 수 있습니다.

C#은 모든 형식의 1차원 및 다차원 배열을 지원합니다. 위에 나열된 형식과 달리, 배열 형식은 사용하기 전에 먼저 선언할 필요가 없습니다. 대신, 배열 형식은 형식 이름을 대괄호로 묶어 생성합니다. 예를 들어 `int[]`는`int`의 1차원 배열이고, `int[,]`는 `int`의 2차원 배열, `int[][]`는 `int`의 1차원 배열의 1차원 배열, 즉 "가변" 배열입니다.

nullable 형식에는 별도의 정의가 필요하지 않습니다. null을 허용하지 않는 형식 `T`의 경우, 대응되는 nullable 형식 `T?`가 있으며 이는 추가 값 `null`을 가질 수 있습니다. 예를 들어 `int?`는 32비트 정수 또는 `null` 값을 보유할 수 있는 형식이고, `string?`은 모든 `string` 또는 `null` 값을 보유할 수 있는 형식입니다.

C#의 형식 시스템은 모든 형식의 값이 `object`로 취급될 수 있도록 통합됩니다. C#의 모든 형식은 `object` 클래스 형식에서 직접 또는 간접적으로 파생되고 `object`는 모든 형식의 기본 클래스입니다. 참조 형식의 값은 `object`로 인식함으로써 간단히 개체로 처리됩니다. 값 형식의 값은 *boxing* 및 *unboxing 작업* 을 수행하여 개체로 처리됩니다. 다음 예제에서 `int` 값은 `object`로 변환되었다가 다시 `int`로 변환됩니다.

:::code language="csharp" source="./snippets/shared/Program.cs" ID="boxing" :::

값 형식의 값이 `object` 참조에 할당되면 값을 보유하기 위해 "box"가 할당됩니다. 이 상자는 참조 형식의 인스턴스이며 해당 상자에 값이 복사됩니다. 반대로 `object` 참조가 값 형식으로 캐스트될 때 참조된 `object`가 올바른 값 형식의 상자인지 확인합니다. 확인에 성공하면 상자의 값이 값 형식에 복사됩니다.

C# 통합 형식 시스템은 결과적으로 값 형식이 "요청 시" `object` 참조로 처리됨을 의미합니다. 통합 때문에 `object` 형식을 사용하는 범용 라이브러리는 참조 형식과 값 형식을 모두 포함하여 `object`에서 파생되는 모든 유형에 사용할 수 있습니다.

C#에는 필드, 배열 요소, 지역 변수 및 매개 변수를 포함하는 여러 종류의 *변수* 가 있습니다. 변수는 저장소 위치를 나타냅니다. 모든 변수에는 아래와 같이 해당 변수에 저장할 수 있는 값을 결정하는 유형이 있습니다.

- Null을 허용하지 않는 값 형식
  - 정확한 해당 형식의 값
- Null 허용 값 형식
  - `null` 값 또는 정확한 해당 형식의 값
- object
  - `null` 참조, 참조 형식의 개체에 대한 참조 또는 값 형식의 boxed 값에 대한 참조
- 클래스 형식
  - `null` 참조, 해당 클래스 형식의 인스턴스에 대한 참조 또는 해당 클래스 형식에서 파생된 클래스의 인스턴스에 대한 참조
- 인터페이스 유형
  - `null` 참조, 해당 인터페이스 형식을 구현하는 클래스 형식의 인스턴스에 대한 참조 또는 해당 인터페이스 형식을 구현하는 값 형식의 boxed 값에 대한 참조
- 배열 형식
  - `null` 참조, 해당 배열 형식의 인스턴스에 대한 참조 또는 호환되는 배열 형식의 인스턴스에 대한 참조
- 대리자 형식
  - `null` 참조 또는 호환되는 대리자 형식의 인스턴스에 대한 참조

## <a name="program-structure"></a>프로그램 구조

C#의 핵심 조직 개념은 [ **‘프로그램’**](../programming-guide/inside-a-program/index.md), [‘네임스페이스’](../programming-guide/namespaces/index.md), [‘형식’](../programming-guide/types/index.md), [‘멤버’](../programming-guide/classes-and-structs/members.md), [‘어셈블리’](../../standard/assembly/index.md)입니다.*_    프로그램은 멤버를 포함하고 네임스페이스로 구성될 수 있는 형식을 선언합니다. 클래스, 구조체 및 인터페이스는 형식의 예입니다. 필드, 메서드, 속성 및 이벤트는 멤버의 예입니다. C# 프로그램을 컴파일하면 실제로 어셈블리로 패키지됩니다. 어셈블리는 일반적으로 애플리케이션을 구현하는지 또는 *라이브러리**를 구현하는지에 따라 각각 파일 확장명 `.exe` 또는 `.dll`을 갖습니다.

간단한 예로, 다음 코드를 포함하는 어셈블리를 생각해 보세요.

:::code language="csharp" source="./snippets/shared/AcmeStack.cs":::

이 클래스의 정규화된 이름은 `Acme.Collections.Stack`입니다. 클래스에는 필드 `top`, 2개의 메서드 `Push` 및 `Pop`, 중첩된 클래스 `Entry` 등의 여러 멤버가 포함됩니다. `Entry` 클래스는 필드 `next` 및 필드 `data`, 생성자의 세 멤버가 포함됩니다. `Stack`은 제네릭 클래스입니다. 이는 사용 시 구체적인 형식으로 대체되는 `T` 형식 매개 변수 하나를 포함합니다.

> [!NOTE]
> 스택은 "FILO"(선입후출) 컬렉션입니다. 스택의 맨 위에 새 요소가 추가됩니다. 요소가 제거되면 스택의 맨 위에서 제거됩니다.

어셈블리에는 IL(중간 언어) 명령 형식의 실행 코드와 메타데이터 형식의 기호 정보가 포함됩니다. 어셈블리가 실행되기 전에, .NET 공용 언어 런타임의 JIT(Just-In-Time) 컴파일러가 어셈블리 안의 IL 코드를 해당 프로세서에 맞는 코드로 변환합니다.

어셈블리는 코드와 메타데이터를 모두 포함하는 기능의 자체 설명 단위이므로 C#에서는 `#include` 지시문과 헤더 파일이 필요하지 않습니다. 특정 어셈블리에 포함된 공용 형식 및 멤버는 프로그램을 컴파일할 때 해당 어셈블리를 참조하는 것만으로 C# 프로그램에서 사용 가능해집니다. 예를 들어 이 프로그램에서는 `acme.dll` 어셈블리의 `Acme.Collections.Stack` 클래스를 사용합니다.

:::code language="csharp" source="./snippets/shared/StackUsage.cs":::

이 프로그램을 컴파일하려면 이전 예제에 정의된 스택 클래스를 포함하는 어셈블리를 참조해야 합니다.

C# 프로그램은 여러 원본 파일에 저장될 수 있습니다. C# 프로그램을 컴파일하면 모든 원본 파일이 함께 처리되고 서로를 제약 없이 참조할 수 있습니다. 개념적으로 처리되기 전에 모든 원본 파일이 하나의 대량 파일에 연결된 것과 같습니다. 소수의 경우를 제외하고 선언 순서는 중요하지 않으므로 C#에서는 정방향 선언이 필요한 경우가 없습니다. C#은 소스 파일을 하나의 공용 형식만 선언하도록 제한하거나 소스 파일 이름이 소스 파일에 선언된 형식과 일치하도록 요구하지 않습니다.

이 둘러보기의 추가 문서에서는 이러한 조직 구성 요소에 대해 설명합니다.

>[!div class="step-by-step"]
>[다음](types.md)
