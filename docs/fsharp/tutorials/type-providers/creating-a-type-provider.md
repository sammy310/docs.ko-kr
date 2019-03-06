---
title: '자습서: 형식 공급자 만들기'
description: 나만의 사이트 생성 하는 방법을 알아봅니다 F# 형식 공급자에서 F# 기본 개념을 보여 주는 몇 가지 간단한 형식 공급자를 검사 하 여 3.0.
ms.date: 02/02/2019
ms.openlocfilehash: ec26f25ad39ca432d6ef11238268e1704bd9638b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371565"
---
# <a name="tutorial-create-a-type-provider"></a>자습서: 형식 공급자 만들기

형식 공급자 메커니즘은 F# 정보가 풍부한 프로그래밍에 대 한 지원의 중요 한 부분입니다. 이 자습서에서는 기본 개념을 보여 주는 몇 가지 간단한 형식 공급자의 개발을 안내 하 여 사용자 고유의 형식 공급자를 만드는 방법을 설명 합니다. 형식 공급자 메커니즘에 대 한 자세한 내용은 F#를 참조 하세요 [형식 공급자](index.md)합니다.

F# 에코 시스템 자주 사용 되는 인터넷 및 엔터프라이즈 데이터 서비스에 대 한 형식 공급자의 범위를 포함 합니다. 예를 들어:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) JSON, XML, CSV 및 HTML 문서 형식에 대 한 형식 공급자를 포함 합니다.

- [SQLProvider](https://fsprojects.github.io/SQLProvider/) 개체 매핑을 통해 SQL database에 대 한 강력한 형식의 액세스를 제공 하 고 F# 이러한 데이터 원본에 대 한 LINQ 쿼리 합니다.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) 컴파일 시간에 대 한 형식 공급자 집합을 확인 했습니다 T-SQL 포함 F#합니다.

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) 는 이전 집합 SQL, Entity Framework, OData, WSDL에 해당 하는 데이터의 서비스에 액세스 하기 위한.NET Framework 프로그래밍에만 사용에 대 한 형식 공급자입니다.

필요한 경우에 사용자 지정 형식 공급자를 만들 수 있습니다 하거나 다른 사람이 만든 형식 공급자를 참조할 수 있습니다. 예를 들어, 조직 점점 숫자로 명명 된 데이터 집합의 각 고유한 안정적인 데이터 스키마를 제공 하는 데이터 서비스가 있을 수 있습니다. 스키마를 읽고 프로그래머에 게 강력한 형식의 방식으로 현재 데이터 집합을 제공 하는 형식 공급자를 만들 수 있습니다.

## <a name="before-you-start"></a>시작하기 전에

안정적인 데이터 및 서비스 정보 공간에 삽입 하는 것에 대 한 형식 공급자 메커니즘은 주로는 F# 프로그래밍 환경입니다.

이 메커니즘 프로그램 논리와 관련이 있는 방식으로 프로그램 실행 중에 스키마 변경 내용은 공백을 삽입 하는 것에 대 한 설계 되지 않습니다. 또한 메커니즘 해당 도메인에 몇 가지 잘못 사용 하는 경우에 메타 프로그래밍 내 언어에 대 한 설계 되지 않습니다. 필요한 경우에이 메커니즘을 사용 해야 하 고 형식 공급자를 개발 매우 높은 값을 생성 하는 위치 합니다.

스키마를 사용할 수 없는 형식 공급자를 작성 하지 마십시오. 일반적인 (또는 기존의) 하는 경우 형식 공급자를 작성 하지 말아야 마찬가지로.NET 라이브러리는 충분 합니다.

시작 하기 전에 다음 질문 수 있습니다.:

- 정보 원본에 대 한 스키마 있습니까? 따라서 무엇 인지에 매핑 합니다 F# 및.NET 형식 시스템?

- 사용할 수 (동적으로 형식화 된) 기존 API를 시작 점으로 구현에 대 한?

- 조직에 게 쉽게 작성 하 고 유용한 형식 공급자의 충분 한 사용? 일반.NET 라이브러리는 요구 사항에 맞게?

- 스키마가 얼마나 변경 되나요?

- 코딩 하는 동안 변경 됩니까?

- 코딩 세션 간에 변경 됩니까?

- 프로그램 실행 중 변경 됩니까?

형식 공급자가 스키마 런타임에 및 컴파일된 코드의 수명 동안 안정적인 상황에 가장 적합 합니다.

## <a name="a-simple-type-provider"></a>단순 형식 공급자

이 샘플은 샘플에서는 비슷합니다 Samples.HelloWorldTypeProvider 합니다 `examples` 디렉터리를 [ F# 형식 공급자 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)합니다. 공급자 사용 가능를 사용 하 여 다음 코드와 같이 100 지워진된 형식을 포함 하는 "형식 공백을" F# 서명 구문 및 세부 정보를 제외한 모든 페이지에 대 한 생략 `Type1`합니다. 지워진된 형식에 대 한 자세한 내용은 참조 하세요. [세부 정보에 대 한 삭제 제공 형식](#details-about-erased-provided-types) 이 항목의에서 뒷부분에 있습니다.

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

형식 및 제공 하는 멤버 집합을 정적으로 알려지지는 note 합니다. 이 예제에서는 스키마에 의존 하는 형식을 제공 하는 공급자의 기능을 활용 하지 않습니다. 형식 공급자의 구현 코드를 다음에 설명 된 및 세부 정보는이 항목의 뒷부분에 나오는 섹션에 설명 되어 있습니다.

> [!WARNING]
> 이 코드와 온라인 샘플 간의 차이가 있을 수 있습니다.

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

이 공급자를 사용 하려면 Visual Studio의 별도 인스턴스를 열고, 만들기는 F# 스크립트를 추가한 다음 다음 코드 에서처럼 #r을 사용 하 여 스크립트에서 공급자에 대 한 참조:

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

찾은 후 아래에 있는 형식에 대 한는 `Samples.HelloWorldTypeProvider` 형식 공급자를 생성 하는 네임 스페이스입니다.

공급자를 다시 컴파일하기 전에 Visual Studio의 모든 인스턴스를 닫았는지 확인 하 고 F# 공급자 DLL을 사용 하는 대화형입니다. 그렇지 않으면 출력 DLL 잠깁니다 때문에 빌드 오류가 발생 합니다.

인쇄 문을 사용 하 여이 공급자를 디버깅 하려면 공급자를 사용 하 여 문제를 노출 하는 스크립트를 만들고 다음 코드를 사용 하 여 합니다.

```
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Visual Studio를 사용 하 여이 공급자를 디버깅 하려면 관리자 자격 증명을 사용 하 여 Visual Studio 용 개발자 명령 프롬프트를 열고 하 고 다음 명령을 실행:

```
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

대신 Visual Studio를 열고, 디버그 메뉴를 열고, 선택 `Debug/Attach to process…`, 및 다른 연결 `devenv` 스크립트를 편집 하는 프로세스입니다. 이 메서드를 사용 하 여 대화형으로 식을 (포함 된 완전 한 IntelliSense 및 기타 기능) 두 번째 인스턴스를 입력 하 여 형식 공급자에서 특정 논리를 쉽게 대상 수 있습니다.

내 코드만 생성 된 코드의 오류를 확인 하려면 디버깅을 비활성화할 수 있습니다. 사용 하도록 설정 하거나이 기능을 사용 하지 않도록 설정 하는 방법에 대 한 정보를 참조 하세요 [디버거로 코드 탐색](/visualstudio/debugger/navigating-through-code-with-the-debugger)합니다. 또한 첫째 예외를 열어 알림을 설정할 수도 있습니다는 `Debug` 메뉴를 선택한 다음 `Exceptions` 열려면 Ctrl + Alt + E 키를 선택 하거나를 `Exceptions` 대화 상자. 해당 대화 상자에서 아래 `Common Language Runtime Exceptions`를 선택 합니다 `Thrown` 확인란 합니다.

### <a name="implementation-of-the-type-provider"></a>형식 공급자의 구현

이 섹션에서는 형식 공급자 구현이 들어 있는 주 섹션을 안내합니다. 먼저, 자체 사용자 지정 형식 공급자에 대 한 형식 정의:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

이 형식은 public 이어야 하 고 사용 하 여 표시 해야 합니다 [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) 컴파일러를 때 별도 형식 공급자를 인식 하는 특성 F# 프로젝트 형식을 포함 하는 어셈블리를 참조 합니다. *config* 매개 변수는 선택적 이며, 있는 경우 형식 공급자 인스턴스는 한 상황에 맞는 구성 정보를 포함 합니다 F# 컴파일러를 만듭니다.

다음으로 구현 된 [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) 인터페이스입니다. 사용 하는 경우에 `TypeProviderForNamespaces` 에서 입력을 `ProvidedTypes` 기본 형식으로 API. 이 도우미 형식 네임 스페이스에 포함 된 각 직접 한정 된 수의 고정을 적극적으로 제공 되는 형식 제공 적극적으로 한정 된 컬렉션을 제공할 수 있습니다. 공급자를이 컨텍스트에서 *적극적으로* 필요 하거나 사용 하지 않더라도 형식을 생성 합니다.

```fsharp
inherit TypeProviderForNamespaces(config)
```

다음으로 제공 된 형식에 대 한 네임 스페이스를 지정 하는 개인 로컬 값을 정의 하 고 자체의 형식 공급자 어셈블리를 찾을. 이 어셈블리는 제공 되는 지워진 형식의 논리 부모 형식으로 나중에 사용 됩니다.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

다음으로 각 유형의 Type1 제공 하는 함수 만들기... Type100 합니다. 이 함수는이 항목의 뒷부분에서 자세히 설명 합니다.

```fsharp
let makeOneProvidedType (n:int) = …
```

다음으로, 100 제공 된 형식을 생성 합니다.

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

다음에 제공 된 네임 스페이스와 형식을 추가 합니다.

```fsharp
do this.AddNamespace(namespaceName, types)
```

마지막으로, 형식 공급자 DLL을 만드는 것을 표시 하는 어셈블리 특성을 추가 합니다.

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>한 형식 및 해당 멤버를 제공합니다.

`makeOneProvidedType` 함수 유형 중 하나를 제공 하는 실제 작업을 수행 합니다.

```fsharp
let makeOneProvidedType (n:int) =
…
```

이 단계에서는이 함수의 구현은 설명합니다. 먼저 제공된 된 형식을 만듭니다 (예를 들어, Type1, n = 1 또는 Type57, n = 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

다음 사항에 유의 해야 합니다.

- 이 제공 형식 지워집니다.  기본 형식 인지를 나타낼 수 있기 때문에 `obj`, 인스턴스 형식의 값으로 표시 됩니다 [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 에서 컴파일된 코드입니다.

- 중첩 되지 않은 형식에 지정 하면 어셈블리 및 네임 스페이스를 지정 해야 합니다. 지워진된 형식 어셈블리 자체의 형식 공급자 어셈블리 이어야 합니다.

그런 다음 형식으로 XML 문서를 추가 합니다. 이 설명서는 지연 되, 호스트 컴파일러에서 필요한 경우 주문형으로 계산 합니다.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

다음 형식으로 제공 된 정적 속성을 추가합니다.

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

이 속성을 가져오면 항상 문자열 "Hello!"로 평가 됩니다. `GetterCode` 속성에 대 한 사용는 F# 속성을 가져오는 데 필요한 호스트 컴파일러 생성 하는 코드를 나타내는 인용 합니다. 따옴표에 대 한 자세한 내용은 참조 하세요. [코드 인용 (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)합니다.

속성에 XML 문서를 추가 합니다.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

이제 제공된 된 형식으로 제공된 된 속성을 연결 합니다. 하나의 형식으로 제공 된 멤버를 연결 해야 합니다. 그렇지 않은 경우 멤버를 액세스할 수 있는 안 됩니다.

```fsharp
t.AddMember staticProp
```

이제 제공 된 매개 변수가 없는 생성자를 만듭니다.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

`InvokeCode` 생성자를 반환는 F# 생성자가 호출 될 때 호스트 컴파일러에서 생성 하는 코드를 나타내는 인용 합니다. 예를 들어, 다음 생성자를 사용할 수 있습니다.

```fsharp
new Type10()
```

제공 된 형식의 인스턴스는 "개체 데이터를" 기본 데이터를 사용 하 여 생성 됩니다. 따옴표 붙은 코드에는 변환할 [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 형식임의 지우기 이므로이 제공 된 형식 (제공된 된 형식을 선언 하는 경우 지정한)으로 합니다.

생성자에 XML 문서를 추가 하 고 제공된 된 형식으로 제공 된 생성자를 추가 합니다.

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

하나의 매개 변수를 사용 하는 두 번째 제공 된 생성자를 만듭니다.

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

`InvokeCode` 생성자 다시 반환 합니다.는 F# 메서드 호출에 대 한 호스트 컴파일러에서 생성 하는 코드를 나타내는 인용 합니다. 예를 들어, 다음 생성자를 사용할 수 있습니다.

```fsharp
new Type10("ten")
```

제공된 된 형식 인스턴스의 기본 데이터 "10"을 사용 하 여 생성 됩니다. 이미 했을 수 있는 여 `InvokeCode` 함수 인용을 반환 합니다. 이 함수에 대 한 입력은 목록 생성자는 매개 변수당 하나의 식입니다. 단일 매개 변수 값을 나타내는 식에서 사용할 수 있는 예제의 경우 `args.[0]`합니다. 생성자에 대 한 호출에 대 한 코드를 반환 값을 지워진된 형식 강제 변환 `obj`합니다. 제공 된 두 번째 생성자는 형식에 추가한 후에 제공 된 인스턴스 속성을 만듭니다.

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

이 속성은 표현 개체는 문자열의 길이 반환 합니다. `GetterCode` 속성이 반환을 F# 속성을 가져올 호스트 컴파일러 생성 하는 코드를 지정 하는 인용 합니다. 와 같은 `InvokeCode`, `GetterCode` 함수 인용을 반환 합니다. 호스트 컴파일러는 인수 목록 사용 하 여이 함수를 호출합니다. 인수를 사용 하 여 액세스할 수 있는 기반이 getter 호출 되 고, 인스턴스를 나타내는 단일 식만을 포함 하는 예제의 경우 `args.[0]`합니다. 구현의 `GetterCode` 지워진 형식을 결과 인용에 분할 한 다음 `obj`, 캐스트는 형식 문자열 인지 확인 하기 위해 컴파일러의 메커니즘을 충족 하는 데 사용 됩니다. 다음 부분인 `makeOneProvidedType` 하나의 매개 변수를 사용 하 여 인스턴스 메서드를 제공 합니다.

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

마지막으로 100 중첩 된 속성을 포함 하는 중첩 된 형식을 만듭니다. 이 폭넓은 중첩 형식과 해당 속성은 지연, 즉, 주문형 계산.

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p =
            ProvidedProperty(propertyName = "StaticProperty" + string i,
              propertyType = typeof<string>,
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () ->
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>지워진된 제공 된 형식에 대 한 세부 정보

이 섹션의 예제만 제공 *제공 된 형식 삭제*는 다음과 같은 경우에 특히 유용 합니다.

- 때 데이터와 메서드를 포함 하는 정보 공간에 대 한 공급자를 작성 하는 합니다.

- 때 정확한 런타임 형식 의미 체계 정보 공간이의 실제 사용에 대 한 중요 하지 않은 공급자를 작성 하는 합니다.

- 경우는 정보 공간을 너무 크고 아니라 기술적으로 가능 정보 공간에 대 한 실제.NET 형식을 생성 하는 상호 연결 된 공급자를 작성 하는 합니다.

이 예제에서는 제공 된 각 입력 형식 지워집니다 `obj`, 고 형식의 모든 사용 형식으로 표시 됩니다 `obj` 컴파일된 코드에서. 사실,이 예제에서 기본 개체는 문자열 이지만 형식으로 표시 됩니다 `System.Object` .NET에서 컴파일된 코드입니다. 형식 지우기의 모든 사용을 사용 하 여 명시적 boxing을 사용할 수 있습니다, unboxing, 캐스팅 및 손상에 지울 형식. 이 경우 개체를 사용 하는 경우 잘못 된 캐스팅 예외가 발생할 수 있습니다. 공급자 런타임 false 표현 으로부터 보호 하기 위해 개인 표현 형식 자체를 정의할 수 있습니다. 지워진된 형식에서 정의할 수 없습니다 F# 자체입니다. 제공 된 형식만 지워질 수 있습니다. 모두 실제 결과 이해 해야 하 고 형식 공급자에서 제공 하는 공급자에 지워진된 형식 지울 형식 중 하나를 사용 하 여 의미 체계. 지워진된 정수 형식을 실제.NET 형식이 없습니다. 따라서 정확 하 게 반영 된 형식에 대해 수행할 수 없습니다 하 고 런타임 캐스트 및 정확한 런타임 형식 의미 체계에 의존 하는 다른 기술을 사용 하는 경우에 지워진된 형식을 파괴할 수 있습니다. 지워진 형식의 subversion 런타임에 형식 캐스팅 예외가 자주 발생합니다.

### <a name="choosing-representations-for-erased-provided-types"></a>제공 된 형식 삭제에 대 한 표현을 선택

지워진 제공 된 형식의 사용을 표현이 없는 필요 합니다. 예를 들어, 지워진는 제공 형식은 정적 속성 및 멤버와 없는 생성자만 포함 될 수 있으며 메서드나 속성이 없는 형식의 인스턴스를 반환 합니다. 수에 도달 하면 지워진된는 인스턴스의 형식을 제공 하는 경우에 다음과 같은 질문을 고려해 야 합니다.

**제공 된 형식의 지우기 란?**

- 제공 된 형식의 지우기 형식 컴파일된.NET 코드에 표시 하는 방법입니다.

- 제공 된 지워진된 클래스 형식의 지우기 항상 첫 번째 비 지워진 기본 형식임 상속 체인의 형식.

- 제공 된 지워진된 인터페이스 형식의 지우기는 항상 `System.Object`합니다.

**제공 된 형식의 표현을 이란?**

- 지워진 제공 형식에 대 한 가능한 개체 집합을 표현 이라고 합니다. 이 문서의 예제에서는 지워진는 제공 된 모든 표현 형식 `Type1..Type100` 는 항상 문자열 개체입니다.

제공 된 형식의 모든 표현을 제공 된 형식의 지우기와 호환 되어야 합니다. (이 고, 그렇지 중 하나는 F# 컴파일러는 형식 공급자를 사용할 경우 오류가 나옴 또는 유효 하지 않은 확인할 수 없는.NET 코드가 생성 됩니다. 형식 공급자는 유효하지 않은 표현을 제공하는 코드를 반환하는 경우 사용할 수 없습니다.)

둘 다는 매우 흔히 다음 방법 중 하나를 사용 하 여 제공 된 개체에 대 한 표현을 선택할 수 있습니다.

- 기존.NET 형식에 대해 강력한 형식의 래퍼를 제공 하기만 하면 됩니다을 하는 경우 종종에 적합 한 해당 형식에 해당 형식에 지우기 표현, 또는 둘 다로 해당 형식의 인스턴스를 사용 합니다. 이 접근 방식은 대부분의 해당 형식에 기존 메서드는 계속 하는 경우 강력한 형식의 버전을 사용 하는 경우 적합 합니다.

- 기존.NET API에서 다른 API를 크게 만들려면 하려는 경우는 형식 지우기 및 제공 된 형식에 대 한 표현을 런타임 형식을 만드는 것이 좋습니다.

이 문서의 예제는 제공 된 개체의 표현으로 문자열을 사용합니다. 자주 표현에 대 한 다른 개체는 데 적합할 수 있습니다. 예를 들어 속성 모음으로 사전을 사용할 수 있습니다.

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

대신 하나 이상의 런타임 작업과 함께 표현을를 런타임에 사용할 형식 공급자에서 형식을 정의할 수 있습니다.

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

제공 된 멤버는이 개체 유형의 인스턴스를 생성한 다음 수 있습니다.

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

이 경우 (선택 사항)으로 사용할 수 있습니다이 형식은 형식 지우기로이 형식을 지정 하 여 합니다 `baseType` 생성할 때는 `ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>주요 요점

이전 섹션에는 다양 한 형식, 속성 및 메서드를 제공 하는 간단한 지우기 형식 공급자를 만드는 방법을 설명 합니다. 또한이 섹션에서는 형식 지우기, 등의 일부 이점이 지워진된 형식에서 형식 공급자를 제공 하는 단점의 개념을 설명 하 고 지워진 형식 표현을 설명 합니다.

## <a name="a-type-provider-that-uses-static-parameters"></a>정적 매개 변수를 사용 하는 형식 공급자

정적 데이터에서 형식 공급자를 매개 변수화 하는 기능 공급자는 로컬 또는 원격 데이터에 액세스할 필요 하지 않습니다 하는 경우에도 많은 흥미로운 시나리오를 수 있습니다. 이 섹션에서는 이러한 공급자를 결합 하는 기본 방법을 배웁니다.

### <a name="type-checked-regex-provider"></a>Regex 공급자를 확인 하는 입력

.NET을 래핑하는 정규식에 대 한 형식 공급자를 구현 한다고 가정해 보겠습니다 <xref:System.Text.RegularExpressions.Regex> 다음 컴파일 시간 보증을 제공 하는 인터페이스에서 라이브러리:

- 정규식 올바른지 여부를 확인 합니다.

- 정규식에는 그룹 이름에 기반한 일치 명명 된 속성을 제공 합니다.

이 섹션에서는 만들려면 형식 공급자를 사용 하는 방법을 보여 줍니다.는 `RegexTyped` 정규식 패턴에서 이러한 이점을 제공할 수 매개 변수화를 입력 합니다. 제공된 된 패턴을 유효 하지 않으면 및 명명 된 일치 하는 속성을 사용 하 여 액세스할 수 있도록 형식 공급자 패턴에서 그룹을 추출할 수 있습니다 하는 경우 컴파일러에서 오류를 보고 합니다. 형식 공급자를 디자인할 때 노출 된 API 표시 되는 방법을 고려해 야 하는 최종 사용자와.NET 코드에이 디자인은 변환 하는 방법입니다. 다음 예제에서는 이러한 API를 사용 하 여 영역 코드의 구성 요소를 얻는 방법을 보여 줍니다.

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

다음 예제에서는 형식 공급자에서 이러한 호출을 변환 하는 방법을 보여 줍니다.

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

다음 사항을 note 합니다.

- 표준 Regex 형식을 나타내는 매개 변수가 있는 `RegexTyped` 형식입니다.

- `RegexTyped` 생성자 패턴에 대 한 정적 형식 인수에 전달 Regex 생성자에 호출 됩니다.

- 결과 `Match` 메서드는 표준으로 표시 됩니다 <xref:System.Text.RegularExpressions.Match> 형식입니다.

- 각 명명 된 그룹에 제공 된 속성을 결과 일치할 경우 인덱서를 사용 하는 결과 속성에 액세스 `Groups` 컬렉션입니다.

다음 코드는 이러한 공급자를 구현 하는 논리의 핵심 하 고이 예제에서는 모든 제공된 된 형식 멤버의 추가 생략 합니다. 각 구성원을 추가 하는 방법에 대 한 내용은이 항목 뒷부분의 적절 한 섹션을 참조 합니다. 전체 코드에서 샘플을 다운로드 합니다 [ F# 3.0 샘플 팩](https://fsharp3sample.codeplex.com) Codeplex 웹 사이트입니다.

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

다음 사항을 note 합니다.

- 두 정적 매개 변수를 사용 하는 형식 공급자: 합니다 `pattern`는 반드시 및 `options`, (제공 되기 때문에 기본값을은)는는 선택 사항입니다.

- 정적 인수가 제공 후 정규식의 인스턴스를 만듭니다. 이 인스턴스 정규식 형식이 잘못 되어 사용자에 게이 오류는 보고 하는 경우 예외가 throw 됩니다.

- 내는 `DefineStaticParameters` 인수가 후 반환 되는 형식을 정의한 콜백입니다.

- 이 코드 설정 `HideObjectMethods` 간소화 된 IntelliSense 환경을 계속 되도록를 true로 합니다. 이 특성을 사용 하면 합니다 `Equals`, `GetHashCode`를 `Finalize`, 및 `GetType` 하지 않을 멤버 제공된 된 개체에 대 한 IntelliSense 목록에서.

- 사용할 `obj` 기본 형식의 수 있지만 메서드를 사용 하는 대로 `Regex` 다음 예와 같이이 형식의 런타임 표현 개체입니다.

- 에 대 한 호출을 `Regex` 생성자에서 throw를 <xref:System.ArgumentException> 때 정규식을 유효 하지 않습니다. 컴파일러는이 예외를 catch 하 고 컴파일 시간에 또는 Visual Studio 편집기에서 오류 메시지가 사용자에 게 보고. 이 예외는 정규식 응용 프로그램을 실행 하지 않고 유효성 검사를 사용 합니다.

의미 있는 메서드 또는 속성을 포함 하지 않으므로 위에 정의 된 형식을 아직 유용 하지. 먼저 추가 하는 정적 `IsMatch` 메서드:

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

이전 코드는 메서드를 정의 `IsMatch`를 입력으로 문자열을 받아서 반환 하는 `bool`합니다. 만 까다로운 부분은 사용 합니다 `args` 내에서 인수를 `InvokeCode` 정의 합니다. 이 예제에서는 `args` 은이 메서드에 대 한 인수를 나타내는 목록 인용입니다. 첫 번째 인수를 나타내는 메서드가 인스턴스 메서드인 경우는 `this` 인수입니다. 그러나 정적 메서드에 대 한 인수는 모든 메서드에 명시적 인수. 따옴표로 묶인된 값의 형식을 지정 된 반환 형식이 일치 해야 함을 참고 (이 예제의 경우 `bool`). 또한이 코드를 사용 하는 참고를 `AddXmlDoc` 메서드를 제공 된 메서드를 IntelliSense를 통해 제공할 수 있는 유용한 설명서도에 있는지 확인 합니다.

다음으로, 인스턴스 Match 메서드를 추가 합니다. 하지만이 메서드는 제공 된 값을 반환 해야 `Match` 을 입력 하 여 그룹을 강력한 형식의 방식으로 액세스할 수 있습니다. 먼저 선언 따라서는 `Match` 형식입니다. 이 형식은 정적 인수로 제공 된 패턴에 의존 하기 때문에이 형식 매개 변수가 있는 형식 정의 내에서 중첩 되어야 합니다.

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

각 그룹에 대 한 일치 항목 형식에 하나의 속성만을 추가합니다. 런타임 시 일치 하는 항목으로 표시 됩니다는 <xref:System.Text.RegularExpressions.Match> 값을 속성을 정의 하는 따옴표를 사용 해야 하므로 <xref:System.Text.RegularExpressions.Match.Groups> 인덱싱된 관련 그룹을 가져올 속성입니다.

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

제공된 된 속성에 XML 문서를 추가 하는 참고 다시 합니다. 경우 속성을 읽을 수 있는 참고도를 `GetterCode` 함수를 제공 하 고 하는 경우 속성을 쓸 수는 `SetterCode` 함수 제공 되므로 결과 속성이 읽기 전용입니다.

이 값을 반환 하는 인스턴스 메서드를 만들면 이제 `Match` 형식:

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

인스턴스 메서드를 만들기 때문에 `args.[0]` 나타냅니다는 `RegexTyped` 기반이 메서드가 호출 되는 인스턴스 및 `args.[1]` 입력된 인수입니다.

마지막으로 제공 된 형식의 인스턴스를 만들 수 있도록 생성자를 제공 합니다.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

생성자는 단순히 때문에 다시 boxed 개체는 표준.NET Regex 인스턴스 생성에 지웁니다 `obj` 제공 된 형식이 삭제 됩니다. 이러한 변경을 통해 항목의 앞부분에서 지정 된 샘플 API 사용에 예상 대로 작동 합니다. 다음 코드는 완전 하 고 최종는:

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a>주요 요점

이 섹션에서는 정적 매개 변수에서 작동 하는 형식 공급자를 만드는 방법을 설명 합니다. 공급자는 static 매개 변수를 확인 하 고 해당 값을 기반으로 하는 작업을 제공 합니다.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>로컬 데이터에서 지 원하는 형식 공급자

자주 형식 공급자 정적 매개 변수 뿐만 아니라 로컬 또는 원격 시스템에서 정보에 따라 Api를 제공할 수도 있습니다. 이 섹션에서는 로컬 데이터 파일과 같은 로컬 데이터를 기반으로 하는 형식 공급자를 설명 합니다.

### <a name="simple-csv-file-provider"></a>간단한 CSV 파일 공급자

간단한 예로, 형식 공급자를 쉼표로 구분 된 값 (CSV) 형식으로 과학적 데이터에 액세스 하기 위한 것이 좋습니다. 이 섹션에서는 CSV 파일에는 다음 표에서 같이 부동 소수점 데이터 뒤에 머리글 행을 포함 하는 것을 가정:

|거리 (미터)|시간 (초)|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

이 단원에서는 사용 하 여 행을 사용할 수 있는 형식을 제공 하는 방법을 보여 줍니다.는 `Distance` 형식의 속성 `float<meter>` 와 `Time` 형식의 속성 `float<second>`합니다. 간단히 하기 위해 다음과 같은 가정은 수행 됩니다.

- 헤더 이름 중 하나는 단위를 사용 하지 않는 형식은 "Name (단위)" 및 쉼표를 포함 하지 않습니다.

- 단위가으로 모든 International SI (시스템) 단위 합니다 [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames 모듈 (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) 모듈을 정의 합니다.

- 단위는 모든 단순 (예를 들어, 측정기) (예를 들어, 미터 초당) 복합 대신 합니다.

- 모든 열에 부동 소수점 데이터 포함 됩니다.

자세한 공급자 이러한 제한 사항은 완화 됩니다.

다시 첫 번째 단계는 API 표시 되는 방법을 고려 하는 것입니다. 이전 테이블의 콘텐츠(쉼표로 분리된 형식)를 사용하여 `info.csv` 파일을 지정한 경우 공급자의 사용자는 다음 예제와 비슷한 코드를 작성할 수 있어야 합니다.

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

이 경우 컴파일러는 다음 예제와 같은 것으로 이러한 호출을 변환 해야:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

최적의 변환 형식 공급자를 실제 정의 해야 합니다. `CsvFile` 형식 공급자 어셈블리의 형식입니다. 형식 공급자는 몇 가지 도우미 형식 및 메서드 중요 한 논리를 래핑할 종종 사용 합니다. 런타임 시 측정값 지워진 이므로 사용할 수 있습니다는 `float[]` 지워진된 행 형식으로 합니다. 컴파일러는 형식이 다른 측정값으로 다른 열을 처리 합니다. 예를 들어, 예제의 첫 번째 열은 형식이 `float<meter>`에 있고 두 번째 `float<second>`입니다. 그러나 지워진된 표현을 간단히 유지할 수 있습니다.

다음 코드에서는 구현의 핵심을 보여 줍니다.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

구현에 대해 다음 사항을 note 합니다.

- 오버 로드 된 생성자에는 원본 파일 또는 중 하나는 동일한 스키마를 읽을 수 있는 허용 합니다. 이 패턴 일반적인 경우 로컬 또는 원격 데이터 원본에 대 한 형식 공급자를 작성 하 고이 패턴에는 로컬 파일에서 원격 데이터에 대 한 템플릿으로 사용할 수 있습니다.

- 사용할 수는 [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) 상대 파일 이름을 확인 하는 형식 공급자 생성자에 전달 되는 값입니다.

- 사용할 수는 `AddDefinitionLocation` 제공 되는 속성의 위치를 정의 하는 방법입니다. 따라서 사용 하는 경우 `Go To Definition` 제공 된 속성 CSV 파일이 Visual Studio에서 열립니다.

- 사용할 수는 `ProvidedMeasureBuilder` SI 단위를 조회 하 고 관련 생성 형식 `float<_>` 형식입니다.

### <a name="key-lessons"></a>주요 요점

이 섹션에서는 데이터 원본 자체에 포함 된 간단한 스키마를 사용 하 여 로컬 데이터 원본에 대 한 형식 공급자를 만드는 방법을 설명 합니다.

## <a name="going-further"></a>계속 진행

다음 섹션에는 추가 연구에 대 한 제안이 포함 됩니다.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>지워진된 형식에 대해 컴파일된 코드 살펴보기

형식 공급자를 사용 내보내는 코드에 해당 하는 방법의 몇 가지 아이디어에 부여 하려면 다음 함수에서 사용 하 여 찾기는 `HelloWorldTypeProvider` 이 항목의 앞부분에 사용 되는 합니다.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Ildasm.exe를 사용 하 여 디컴파일된 결과 코드의 이미지는 다음과 같습니다.

```
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

형식의 모든 멘 션 하는 예제와 같이 `Type1` 하며 `InstanceProperty` 런타임 형식에 대 한 작업만 관련 종료 속성을 지워졌을입니다.

### <a name="design-and-naming-conventions-for-type-providers"></a>디자인 및 형식 공급자에 대 한 명명 규칙

형식 공급자를 작성할 때 다음과 같은 규칙을 확인 합니다.

**연결 프로토콜에 대 한 공급자** OData 또는 SQL 연결과 같은 데이터 및 서비스 연결 프로토콜에 대 한 대부분의 공급자 Dll의 이름에서 일반적으로 끝나야 `TypeProvider` 또는 `TypeProviders`합니다. 예를 들어 다음 문자열 유사한 DLL 이름을 사용 합니다.

```
  Fabrikam.Management.BasicTypeProviders.dll
```

제공 된 형식에 해당 네임 스페이스의 구성원이 며 구현 된 연결 프로토콜을 지정 해야 합니다.

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**일반 코딩에 대 한 유틸리티 공급자**합니다.  유틸리티 형식 공급자를 것과 같은 정규식에 대 한 형식 공급자를 기본 라이브러리의 일부가 다음 예제와 같이 할 수 있습니다.

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

이 경우 표준.NET 디자인 규칙에 따라 적절 한 시점에 제공된 된 형식 표시 됩니다.

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**단일 데이터 원본**합니다. 일부 형식 공급자는 단일 전용된 데이터 원본에 연결 하 고만 데이터를 제공 합니다. 이 경우 인덱스를 제거 하는 `TypeProvider` 접미사 및.NET 명명에 대 한 일반 규칙을 사용 합니다.

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

자세한 내용은 참조는 `GetConnection` 이 항목의 뒷부분에 설명 된 규칙을 디자인 합니다.

### <a name="design-patterns-for-type-providers"></a>형식 공급자에 대 한 디자인 패턴

다음 섹션에서는 형식 공급자를 작성할 때 사용할 수는 디자인 패턴에 설명 합니다.

#### <a name="the-getconnection-design-pattern"></a>GetConnection 디자인 패턴

대부분의 형식 공급자를 사용 하 여에 써야 합니다 `GetConnection` 다음 예와 같이 FSharp.Data.TypeProviders.dll에서 형식 공급자에서 사용 되는 패턴:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>원격 데이터 및 서비스에서 지 원하는 형식 공급자

원격 데이터 및 서비스에서 지 원하는 형식 공급자를 만들기 전에 다양 한 연결 된 프로그래밍에 내재 된 문제를 고려해 야 합니다. 이러한 문제에는 다음과 같은 고려 사항이 포함 됩니다.

- 스키마 매핑

- 선거 및 스키마 변경 시 무효화

- 스키마 캐싱

- 데이터 액세스 작업의 비동기 구현

- LINQ 쿼리를 포함 하 여 쿼리를 지원 합니다.

- 자격 증명 및 인증

이 항목에서는 이러한 문제를 추가로 탐색 하지 않습니다.

### <a name="additional-authoring-techniques"></a>추가 제작 방법

사용자 고유의 형식 공급자를 작성 하는 경우에 다음과 같은 추가 기술을 사용 하는 것이 좋습니다.

### <a name="creating-types-and-members-on-demand"></a>형식 및 멤버 주문형으로 만들기

ProvidedType API 버전의 AddMember 연기 했습니다.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

이러한 버전은 형식의 주문형으로 공간을 만들려면 사용 됩니다.

### <a name="providing-array-types-and-generic-type-instantiations"></a>배열 형식 및 제네릭 형식 인스턴스화를 제공합니다.

일반을 사용 하 여 제공 된 멤버 (시그니처 배열 형식, byref 형식 및 제네릭 형식의 인스턴스화를 포함 하는 데 사용) 할 `MakeArrayType`, `MakePointerType`, 및 `MakeGenericType` 의 모든 인스턴스에서 <xref:System.Type>등 `ProvidedTypeDefinitions`합니다.

> [!NOTE]
> 도우미를 사용 하 여 할 경우도 `ProvidedTypeBuilder.MakeGenericType`합니다.  참조 된 [형식 공급자 SDK 설명서](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) 대 한 자세한 내용은 합니다.

### <a name="providing-unit-of-measure-annotations"></a>측정값 주석의 단위를 제공합니다.

ProvidedTypes API 측정값 주석을 제공 하기 위한 도우미를 제공 합니다. 예를 들어 형식을 제공할 `float<kg>`, 다음 코드를 사용 합니다.

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  형식을 제공할 `Nullable<decimal<kg/m^2>>`, 다음 코드를 사용 합니다.

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>프로젝트 로컬 또는 로컬 스크립트 리소스에 액세스

형식 공급자의 각 인스턴스를 지정할 수는 `TypeProviderConfig` 생성 하는 동안 값입니다. 이 값은 공급자 (즉, 컴파일 또는 스크립트가 포함 된 디렉터리에 대 한 프로젝트 폴더), 참조 된 어셈블리의 목록 및 기타 정보에 대 한 "해결"폴더를 포함 합니다.

### <a name="invalidation"></a>무효화

공급자에 알리기 위해 무효화 신호를 발생 시킬 수 있습니다는 F# 언어 서비스 스키마를 가정 하는 변경 된 경우. 무효화 되는 경우 공급자는 Visual Studio에서 호스트 되는 경우는 한 번 다시 실행 됩니다. 이 신호를 공급자에 호스팅되는 경우 무시 됩니다 F# 대화형 또는 F# 컴파일러 (fsc.exe).

### <a name="caching-schema-information"></a>캐싱 스키마 정보

공급자는 스키마 정보에 대 한 액세스를 캐시 종종 해야 합니다. 정적 매개 변수 또는 사용자 데이터에 지정 된 파일 이름을 사용 하 여 캐시 된 데이터를 저장 되어야 합니다. 스키마 캐시의 예로 `LocalSchemaFile` 에서 형식 공급자에서 매개 변수는 `FSharp.Data.TypeProviders` 어셈블리입니다. 이러한 공급자의 구현에이 정적 매개 변수는 네트워크를 통해 데이터 원본에 액세스 하는 대신 지정된 된 로컬 파일에서 스키마 정보를 사용 하는 형식 공급자를 전달 합니다. 캐시 된 스키마 정보를 사용 하려면 설정 해야 static 매개 변수 `ForceUpdate` 에 `false`입니다. 온라인 및 오프 라인 데이터 액세스할 수 있도록 비슷한 기법을 사용할 수 있습니다.

### <a name="backing-assembly"></a>어셈블리를 백업합니다.

컴파일하는 경우는 `.dll` 또는 `.exe` 파일을 백업.dll 파일에 정적 생성 된 형식으로 결과 어셈블리에 링크 합니다. 이 링크는 최종 어셈블리로 백업 어셈블리에서 IL (Intermediate Language) 형식 정 및 관리 되는 모든 리소스를 복사 하 여 생성 됩니다. 사용 하는 경우 F# 대화형, 백업.dll 파일이 복사 되지 않습니다 및 대신에 직접 로드 되는 F# 대화형 프로세스입니다.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>예외 및 형식 공급자에서 진단

제공 된 형식에서 모든 멤버의 모든 사용 예외를 throw 할 수 있습니다. 모든 경우에 형식 공급자에서 예외를 throw 하는 경우 호스트 컴파일러 오류를 특성을 특정 형식 공급자입니다.

- 내부 컴파일러 오류에 예외 이어지지 않아야 하는 공급자를 입력 합니다.

- 형식 공급자는 경고를 보고할 수 없습니다.

- 형식 공급자에서 호스트 되는 경우는 F# 컴파일러는 F# 개발 환경 또는 F# 대화형으로 해당 공급자에서 모든 예외를 발견 합니다. Message 속성은 항상 오류 텍스트 및 스택 추적 없음이 표시 됩니다. 다음 예제에서는 예외를 throw 하려는 경우 throw 할 수 있습니다: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`합니다.

#### <a name="providing-generated-types"></a>생성 된 형식 제공

지금까지이 문서는 지워진된 형식을 제공 하는 방법을 설명 했습니다. 형식 공급자 메커니즘을 사용할 수도 있습니다 F# 을 제공 하기 위해 생성 된 형식으로 실제.NET 형식 정의 사용자 프로그램에 추가 된 합니다. 나타내야 할 생성 된 형식 정의 사용 하 여 제공 되는 형식입니다.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

일부인 ProvidedTypes-0.2 도우미 코드를 F# 3.0 버전에서는 제한적 으로만 생성 된 형식을 제공 하는 것에 대 한 지원. 다음 문은 생성 된 형식 정의 대해 true 여야 합니다.

- `isErased` 로 설정 되어야 합니다 `false`합니다.

- 생성 된 형식을 추가 해야를 새로 생성 된 `ProvidedAssembly()`, 생성 된 코드 조각에 대 한 컨테이너를 나타내는입니다.

- 공급자 어셈블리를 디스크에 일치 하는.dll 파일을 사용 하는 실제 백업.NET.dll 파일이 있어야 합니다.

## <a name="rules-and-limitations"></a>규칙 및 제한 사항

형식 공급자를 작성할 때는 다음 규칙 및 제한 사항을 염두에서에 둡니다.

### <a name="provided-types-must-be-reachable"></a>제공 된 형식에 연결할 수 있어야 합니다.

모든 제공 형식에 중첩 되지 않은 형식에서 도달할 수 있어야 합니다. 중첩 되지 않은 형식에 대 한 호출에 제공 됩니다는 `TypeProviderForNamespaces` 호출이 나 생성자 `AddNamespace`합니다. 예를 들어 공급자는 형식을 제공 하는 경우 `StaticClass.P : T`, T는 중첩 되지 않은 형식 또는 아래에 중첩된 하나가 있어야 합니다.

예를 들어 일부 공급자에는 정적 클래스와 같은 `DataTypes` 포함 하는 이러한 `T1, T2, T3, ...` 형식입니다. 이 고, 그렇지 오류 라고 하는 어셈블리에서 형식 T에 대 한 참조를 찾았지만 해당 어셈블리에서 형식을 찾을 수 없습니다. 와 함께이 오류가 나타나는 경우에 모든 하위 형식은 공급자 유형에 서에 연결할 수 있는지를 확인 합니다. 참고: 이러한 `T1, T2, T3...` 형식 이라고 합니다 *즉석에서* 형식입니다. 액세스할 수 있는 네임 스페이스 또는 부모 형식에 배치 해야 합니다.

### <a name="limitations-of-the-type-provider-mechanism"></a>형식 공급자 메커니즘은의 제한 사항

형식 공급자 메커니즘은 F# 다음과 같은 제한이 있습니다.

- 기본 인프라에서 형식 공급자에 대 한 F# 제네릭 형식 또는 제네릭 메서드를 제공 합니다. 제공을 지원 하지 않습니다.

- 메커니즘에는 정적 매개 변수를 사용 하 여 중첩 된 형식을 지원 하지 않습니다.

## <a name="development-tips"></a>개발 팁

개발 프로세스 중 다음 팁을를 유용할 수 있습니다.

### <a name="run-two-instances-of-visual-studio"></a>Visual Studio의 두 인스턴스를 실행 합니다.

한 인스턴스에서 형식 공급자를 개발 하 고 테스트 IDE는 형식 공급자를 다시 작성 하는 것을 방지 하는.dll 파일 잠금을 사용 하기 때문에 다른 공급자를 테스트 수입니다. 따라서 첫 번째 인스턴스를 공급자가 빌드되고 다음 다시 열어야 두 번째 인스턴스 공급자를 작성 한 후 하는 동안 Visual Studio의 두 번째 인스턴스를 닫을 해야 있습니다.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Fsc.exe의 호출을 사용 하 여 형식 공급자를 디버그

다음 도구를 사용 하 여 형식 공급자를 호출할 수 있습니다.

- fsc.exe (의 F# 명령줄 컴파일러)

- fsi.exe (의 F# Interactive 컴파일러)

- devenv.exe (Visual Studio)

자주 테스트 스크립트 파일 (예를 들어 script.fsx) fsc.exe를 사용 하 여 형식 공급자를 가장 쉽게 디버깅할 수 있습니다. 명령 프롬프트에서 디버거를 시작할 수 있습니다.

```
  devenv /debugexe fsc.exe script.fsx
```

  인쇄-stdout 로깅을 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

- [형식 공급자](index.md)
- [형식 공급자 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
