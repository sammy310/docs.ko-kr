---
title: '자습서: 형식 공급자 만들기'
description: 기본 개념을 설명하기 위해 몇 가지 간단한 형식 공급자를 검사하여 F# 3.0에서 고유한 F# 형식 공급자를 만드는 방법을 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 3b8145d4c2d8bf96b6dcf66de02e9f2d83927d74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186114"
---
# <a name="tutorial-create-a-type-provider"></a>자습서: 형식 공급자 만들기

F#의 형식 공급자 메커니즘은 풍부한 정보 프로그래밍에 대한 지원의 중요한 부분입니다. 이 자습서에서는 기본 개념을 설명하기 위해 몇 가지 간단한 형식 공급자의 개발을 안내하여 고유한 형식 공급자를 만드는 방법을 설명합니다. F#의 형식 공급자 메커니즘에 대한 자세한 내용은 [형식 공급자](index.md)를 참조하십시오.

F# 생태계에는 일반적으로 사용되는 인터넷 및 엔터프라이즈 데이터 서비스에 대한 다양한 형식 공급자가 포함되어 있습니다. 다음은 그 예입니다.

- [FSharp.Data에는](https://fsharp.github.io/FSharp.Data/) JSON, XML, CSV 및 HTML 문서 형식에 대한 형식 공급자가 포함됩니다.

- [SQLProvider는](https://fsprojects.github.io/SQLProvider/) 개체 매핑 및 이러한 데이터 원본에 대한 F# LINQ 쿼리를 통해 SQL 데이터베이스에 대한 강력한 형식의 액세스를 제공합니다.

- [FSharp.Data.SqlClient는](https://fsprojects.github.io/FSharp.Data.SqlClient/) F#에 T-SQL의 컴파일 타임 확인 포함을 위한 형식 공급자 집합을 가지고 있습니다.

- [FSharp.Data.TypeProviders는](https://fsprojects.github.io/FSharp.Data.TypeProviders/) SQL, 엔터티 프레임워크, OData 및 WSDL 데이터 서비스에 액세스하기 위한 .NET 프레임워크 프로그래밍에서만 사용할 수 있는 이전 형식 공급자 집합입니다.

필요한 경우 사용자 지정 형식 공급자를 만들거나 다른 사용자가 만든 형식 공급자를 참조할 수 있습니다. 예를 들어 조직에는 각각 고유한 안정적인 데이터 스키마가 있는 명명된 데이터 집합의 수가 늘어나는 데이터 서비스를 사용할 수 있습니다. 스키마를 읽고 현재 데이터 집합을 강력하게 입력한 방식으로 프로그래머에게 제공하는 형식 공급자를 만들 수 있습니다.

## <a name="before-you-start"></a>시작하기 전에

형식 공급자 메커니즘은 주로 안정적인 데이터 및 서비스 정보 공간을 F# 프로그래밍 환경으로 주입하도록 설계되었습니다.

이 메커니즘은 프로그램 논리와 관련된 방식으로 프로그램 실행 중에 스키마가 변경되는 정보 공간을 삽입하기 위해 설계되지 않았습니다. 또한 해당 도메인에 유효한 용도가 포함되어 있더라도 언어 내 메타 프로그래밍을 위해 메커니즘이 설계되지 않았습니다. 필요한 경우에만 이 메커니즘을 사용해야 하며 형식 공급자의 개발로 매우 높은 가치를 산출하는 경우에만 사용해야 합니다.

스키마를 사용할 수 없는 형식 공급자를 작성하지 않아야 합니다. 마찬가지로 일반(또는 기존)의 .NET 라이브러리로 충분할 수 있는 형식 공급자를 작성하지 않아야 합니다.

시작하기 전에 다음 질문을 할 수 있다.

- 정보 소스에 대한 스키마가 있습니까? 그렇다면 F# 및 .NET 형식 시스템에 매핑하는 것은 무엇입니까?

- 기존(동적으로 입력된) API를 구현의 시작점으로 사용할 수 있습니까?

- 사용자와 조직에서 형식 공급자를 충분히 사용하여 작성을 가치 있게 만들 수 있습니까? 일반 .NET 라이브러리가 사용자의 요구를 충족합니까?

- 스키마는 얼마만큼 변경될 것인가?

- 코딩 중에 변경될 까요?

- 코딩 세션 간에 변경될 까요?

- 프로그램 실행 중에 변경합니까?

형식 공급자는 스키마가 런타임 및 컴파일된 코드의 수명 동안 안정적인 상황에 가장 적합합니다.

## <a name="a-simple-type-provider"></a>간단한 형식 공급자

이 샘플은 샘플입니다.HelloWorldTypeProvider는 `examples` [F# 형식 공급자 SDK의](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)디렉터리에 있는 샘플과 유사합니다. 공급자는 F# 서명 구문을 사용하고 을 제외한 `Type1`모든 세부 정보를 생략하여 다음 코드에서 보여 주는 것처럼 100개의 지워진 형식을 포함하는 "형식 공간"을 사용할 수 있습니다. 지워진 형식에 대한 자세한 내용은 이 항목의 후반부에서 [지워진 제공된 형식에 대한 세부 정보를 참조하세요.](#details-about-erased-provided-types)

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

제공된 형식 및 멤버 집합은 정적으로 알려져 있습니다. 이 예제는 스키마에 종속된 형식을 제공하는 공급자의 기능을 활용하지 않습니다. 형식 공급자의 구현은 다음 코드에 설명되어 있으며 자세한 내용은 이 항목의 이후 섹션에서 다룹니다.

> [!WARNING]
> 이 코드와 온라인 샘플 간에 차이가 있을 수 있습니다.

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

이 공급자를 사용 하려면 Visual Studio의 별도 인스턴스를 열고 F# 스크립트를 만든 다음 다음 코드와 같이 #r 사용 하 여 스크립트에서 공급자에 대 한 참조를 추가 합니다.

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

그런 다음 형식 공급자가 생성한 `Samples.HelloWorldTypeProvider` 네임스페이스 아래에 있는 형식을 찾습니다.

공급자를 다시 컴파일하기 전에 공급자 DLL을 사용하는 Visual Studio 및 F# 대화형의 모든 인스턴스를 닫았는지 확인합니다. 그렇지 않으면 출력 DLL이 잠겨 있기 때문에 빌드 오류가 발생합니다.

print 문을 사용하여 이 공급자를 디버깅하려면 공급자에 문제를 노출하는 스크립트를 만들고 다음 코드를 사용합니다.

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Visual Studio를 사용하여 이 공급자를 디버깅하려면 관리 자격 증명을 사용하여 Visual Studio용 개발자 명령 프롬프트를 열고 다음 명령을 실행합니다.

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

또는 Visual Studio를 열고 디버그 메뉴를 열고 `Debug/Attach to process…`을 선택하고 `devenv` 스크립트를 편집하는 다른 프로세스에 연결합니다. 이 메서드를 사용 하 여 두 번째 인스턴스에 대화식으로 입력 (전체 IntelliSense 및 기타 기능)를 사용 하 여 형식 공급자에서 특정 논리를 보다 쉽게 대상으로 지정할 수 있습니다.

내 코드 디버깅을 사용하지 않도록 설정하여 생성된 코드의 오류를 더 잘 식별할 수 있습니다. 이 기능을 사용하거나 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [디버거를 사용하여 코드 탐색을](/visualstudio/debugger/navigating-through-code-with-the-debugger)참조하십시오. 또한 `Debug` 메뉴를 연 다음 Ctrl+Alt+E 키를 `Exceptions` 선택하거나 선택하여 대화 상자를 열어 첫 `Exceptions` 번째 예외 catch를 설정할 수도 있습니다. 해당 대화 상자에서 `Common Language Runtime Exceptions`에서 확인란을 선택합니다. `Thrown`

### <a name="implementation-of-the-type-provider"></a>형식 공급자 구현

이 섹션에서는 형식 공급자 구현의 주요 섹션을 안내합니다. 먼저 사용자 지정 형식 공급자 자체에 대 한 형식을 정의 합니다.

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

이 형식은 공용이어야 하며 별도의 F# 프로젝트가 형식을 포함하는 어셈블리를 참조할 때 컴파일러가 형식 공급자를 인식할 수 있도록 [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) 특성으로 표시해야 합니다. *구성* 매개 변수는 선택 사항이며, 있는 경우 F# 컴파일러가 만드는 형식 공급자 인스턴스에 대한 컨텍스트 구성 정보가 포함되어 있습니다.

다음으로 [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) 인터페이스를 구현합니다. 이 경우 API의 `TypeProviderForNamespaces` `ProvidedTypes` 형식을 기본 유형으로 사용합니다. 이 도우미 유형은 간절히 제공한 이름 영역의 유한 한 컬렉션을 제공할 수 있으며, 각 키드에는 유한한 수의 고정된 형식이 직접 포함되어 있습니다. 이 컨텍스트에서 공급자는 필요 하거나 사용 하지 않는 경우에 *형식을 열심히* 생성 합니다.

```fsharp
inherit TypeProviderForNamespaces(config)
```

그런 다음 제공된 형식의 네임스페이스를 지정하는 로컬 개인 값을 정의하고 형식 공급자 어셈블리 자체를 찾습니다. 이 어셈블리는 나중에 제공된 지워진 형식의 논리적 부모 유형으로 사용됩니다.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

다음으로, 각 Type1을 제공하는 함수를 만듭니다... Type100. 이 함수는 이 항목의 후반부에서 자세히 설명합니다.

```fsharp
let makeOneProvidedType (n:int) = …
```

다음으로 제공된 100개의 형식을 생성합니다.

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

다음으로 형식을 제공된 네임스페이스로 추가합니다.

```fsharp
do this.AddNamespace(namespaceName, types)
```

마지막으로 형식 공급자 DLL을 만들고 있음을 나타내는 어셈블리 특성을 추가합니다.

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>한 가지 유형과 그 구성원 제공

함수는 `makeOneProvidedType` 형식 중 하나를 제공하는 실제 작업을 수행합니다.

```fsharp
let makeOneProvidedType (n:int) =
…
```

이 단계에서는 이 함수의 구현에 대해 설명합니다. 먼저 제공된 형식(예: Type1, n = 1, Type57, n = 57)을 만듭니다.

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

다음 사항을 기록해야 합니다.

- 제공된 형식이 지워집니다.  기본 형식이 `obj`있음을 나타내기 때문에 인스턴스는 컴파일된 코드에서 [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 형식의 값으로 표시됩니다.

- 중첩되지 않은 형식을 지정할 때 어셈블리 및 네임스페이스를 지정해야 합니다. 지워진 형식의 경우 어셈블리는 형식 공급자 어셈블리 자체여야 합니다.

다음으로 형식에 XML 설명서를 추가합니다. 이 문서는 호스트 컴파일러가 필요한 경우 주문형으로 계산되는 지연됩니다.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

다음으로 형식에 제공된 정적 속성을 추가합니다.

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

이 속성을 가져오는 것은 항상 문자열 "Hello!"로 평가됩니다. for `GetterCode` 속성은 호스트 컴파일러가 속성을 얻기 위해 생성하는 코드를 나타내는 F# 따옴표를 사용합니다. 견적에 대한 자세한 내용은 [코드 견적(F#)을](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)참조하십시오.

속성에 XML 설명서를 추가합니다.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

이제 제공된 속성을 제공된 형식에 연결합니다. 제공된 멤버를 하나의 형식에만 연결해야 합니다. 그렇지 않으면 멤버에 액세스할 수 없습니다.

```fsharp
t.AddMember staticProp
```

이제 매개 변수를 수행하지 않는 제공된 생성자만들기가 됩니다.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

for `InvokeCode` 생성자는 생성자가 호출될 때 호스트 컴파일러가 생성하는 코드를 나타내는 F# 따옴표를 반환합니다. 예를 들어 다음 생성자다음을 사용할 수 있습니다.

```fsharp
new Type10()
```

제공된 형식의 인스턴스는 기본 데이터 "개체 데이터"로 만들어집니다. 인용된 코드에는 해당 형식이 제공된 형식을 선언할 때 지정한 대로 이 제공된 형식의 지우기이므로 [obj로의](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 변환이 포함됩니다.

생성자에 XML 설명서를 추가하고 제공된 생성기를 제공된 형식에 추가합니다.

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

하나의 매개 변수를 취하는 두 번째 제공된 생성자 만들기:

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

for `InvokeCode` 생성자는 메서드 호출에 대해 호스트 컴파일러가 생성한 코드를 나타내는 F# 따옴표를 다시 반환합니다. 예를 들어 다음 생성자다음을 사용할 수 있습니다.

```fsharp
new Type10("ten")
```

제공된 형식의 인스턴스는 기본 데이터 "10"으로 만들어집니다. 함수가 견적을 `InvokeCode` 반환한다는 것을 이미 알아차렸을 수 있습니다. 이 함수에 대한 입력은 생성자 매개 변수당 하나씩 식 목록입니다. 이 경우 단일 매개 변수 값을 나타내는 식을 `args.[0]`에서 사용할 수 있습니다. 생성자 호출코드는 지워진 형식에 `obj`반환 값을 강제 변환합니다. 형식에 두 번째 제공 된 생성기를 추가 한 후 제공 된 인스턴스 속성을 만듭니다.

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

이 속성을 가져오는 것은 표현 객체인 문자열의 길이를 반환합니다. 속성은 `GetterCode` 호스트 컴파일러가 속성을 가져오는 데 생성하는 코드를 지정하는 F# 견적을 반환합니다. 마찬가지로 `InvokeCode`함수는 `GetterCode` 견적을 반환합니다. 호스트 컴파일러는 인수 목록으로 이 함수를 호출합니다. 이 경우 인수에는 getter가 호출되는 인스턴스를 나타내는 단일 표현식만 포함되며, 이 `args.[0]`식을 사용하여 액세스할 수 있습니다. `GetterCode` 그런 다음 지워진 형식에서 `obj`결과 따옴표로 스플라이스를 구현하고 캐스트는 개체가 문자열인 형식을 검사하기 위한 컴파일러 메커니즘을 충족하는 데 사용됩니다. 다음 `makeOneProvidedType` 부분에서는 하나의 매개 변수를 사용하여 인스턴스 메서드를 제공합니다.

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

마지막으로 100개의 중첩 된 속성을 포함 하는 중첩 된 형식을 만듭니다. 이 중첩 된 형식및 해당 속성의 생성은 요청시 계산되는 지연됩니다.

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>지워진 제공된 유형에 대한 세부 정보

이 섹션의 예제에서는 *지워진 제공된 형식만*제공하므로 다음 상황에서 특히 유용합니다.

- 데이터와 메서드만 포함하는 정보 공간에 대한 공급자를 작성할 때

- 정확한 런타임 유형 의미체계가 정보 공간을 실용화하는 데 중요하지 않은 공급자를 작성하는 경우

- 너무 크고 상호 연결된 정보 공간에 대한 공급자를 작성하는 경우 정보 공간에 대한 실제 .NET 형식을 기술적으로 생성할 수 없습니다.

이 예제에서는 제공된 각 형식이 `obj`형식에 지워지고 형식의 모든 `obj` 용도가 컴파일된 코드의 유형으로 나타납니다. 실제로 이러한 예제의 기본 개체는 문자열이지만 형식은 .NET `System.Object` 컴파일된 코드와 같이 나타납니다. 형식 지우기의 모든 사용과 마찬가지로 명시적 boxing, 언박싱 및 캐스팅을 사용하여 삭제된 형식을 전복할 수 있습니다. 이 경우 개체를 사용할 때 유효하지 않은 캐스트 예외가 발생할 수 있습니다. 공급자 런타임은 잘못된 표현으로부터 보호하기 위해 자체 개인 표현 유형을 정의할 수 있습니다. F# 자체에서는 지워진 형식을 정의할 수 없습니다. 제공된 형식만 지울 수 있습니다. 형식 공급자 또는 지워진 형식을 제공하는 공급자에 대해 지워진 형식을 사용하는 것이 실용적이고 의미 체계적인 결과를 이해해야 합니다. 지워진 형식에는 실제 .NET 형식이 없습니다. 따라서 형식에 대한 정확한 리플렉션을 수행할 수 없으며 런타임 캐스트 및 정확한 런타임 형식 의미체계를 사용하는 기타 기술을 사용하는 경우 삭제된 형식을 전복할 수 있습니다. 지워진 형식의 전복은 런타임에 형식 캐스트 예외를 초래하는 경우가 많습니다.

### <a name="choosing-representations-for-erased-provided-types"></a>지워진 제공된 형식에 대한 표현 선택

지워진 제공된 형식의 일부 사용의 경우 표현이 필요하지 않습니다. 예를 들어 지워진 제공된 형식에는 정적 속성과 멤버만 포함될 수 있으며 생성자는 없으며 메서드나 속성은 형식의 인스턴스를 반환하지 않습니다. 지워진 제공된 유형의 인스턴스에 도달할 수 있는 경우 다음 질문을 고려해야 합니다.

**제공된 형식의 삭제는 무엇입니까?**

- 제공된 형식의 삭제는 컴파일된 .NET 코드에 형식이 표시되는 방식입니다.

- 제공된 지워진 클래스 형식의 지우기는 항상 형식의 상속 체인에서 지워지지 않은 첫 번째 기본 형식입니다.

- 제공된 지워진 인터페이스 형식의 지우기는 항상 `System.Object`.

**제공된 형식의 표현은 무엇입니까?**

- 지워진 제공된 형식에 대해 가능한 개체 집합을 해당 표현이라고 합니다. 이 문서의 예제에서 지워진 제공된 모든 형식의 `Type1..Type100` 표현은 항상 문자열 개체입니다.

제공된 형식의 모든 표현은 제공된 형식의 지우기와 호환되어야 합니다. 그렇지 않으면 F# 컴파일러가 형식 공급자사용에 대한 오류를 제공하거나 유효하지 않은 확인할 수 없는 .NET 코드가 생성됩니다. 형식 공급자는 유효하지 않은 표현을 제공하는 코드를 반환하는 경우 사용할 수 없습니다.)

제공된 개체에 대한 표현을 선택할 수 있습니다.

- 기존 .NET 형식에 대해 강력한 형식의 래퍼를 제공하는 경우 형식이 해당 형식으로 지워지거나 해당 형식의 인스턴스를 표현으로 사용하거나 둘 다로 사용하는 것이 좋습니다. 이 방법은 강력한 형식의 버전을 사용할 때 해당 형식의 대부분의 기존 메서드가 여전히 의미가 있는 경우에 적합합니다.

- 기존 .NET API와 크게 다른 API를 만들려면 제공된 형식에 대한 형식 지우기 및 표현이 되는 런타임 형식을 만드는 것이 좋습니다.

이 문서의 예제에서는 제공된 개체의 표현으로 문자열을 사용합니다. 표현에 다른 개체를 사용하는 것이 적절할 수 있습니다. 예를 들어 사전을 속성 백으로 사용할 수 있습니다.

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

또는 하나 이상의 런타임 작업과 함께 표현을 형성하는 데 런타임에 사용되는 형식 공급자의 형식을 정의할 수 있습니다.

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

제공된 멤버는 다음 개체 형식의 인스턴스를 생성할 수 있습니다.

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

이 경우 (선택적으로) 이 형식을 다음을 생성할 `baseType` `ProvidedTypeDefinition`때로 지정하여 이 형식을 형식 지우기로 사용할 수 있습니다.

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>주요 교훈

이전 섹션에서는 다양한 형식, 속성 및 메서드를 제공하는 간단한 지워지는 형식 공급자를 만드는 방법을 설명했습니다. 이 섹션에서는 형식 공급자에서 지워진 형식을 제공하는 몇 가지 장점과 단점을 포함하여 형식 지우기의 개념을 설명하고 지워진 형식의 표현에 대해설명했습니다.

## <a name="a-type-provider-that-uses-static-parameters"></a>정적 매개 변수를 사용하는 형식 공급자

정적 데이터로 형식 공급자를 매개 변수화하는 기능을 사용하면 공급자가 로컬 또는 원격 데이터에 액세스할 필요가 없는 경우에도 많은 흥미로운 시나리오를 사용할 수 있습니다. 이 섹션에서는 이러한 공급자를 함께 배치하는 몇 가지 기본 기술을 배웁니다.

### <a name="type-checked-regex-provider"></a>확인된 정규표현기 공급자 유형

다음과 같은 컴파일 타임 보장을 제공하는 인터페이스에서 .NET <xref:System.Text.RegularExpressions.Regex> 라이브러리를 래핑하는 정규식에 대한 형식 공급자를 구현하려고 한다고 가정해 보세요.

- 정규식이 유효한지 여부를 확인합니다.

- 정규식의 모든 그룹 이름을 기반으로 하는 일치 항목에서 명명된 속성을 제공합니다.

이 섹션에서는 형식 공급자를 사용하여 `RegexTyped` 정규식 패턴이 매개 변수화하여 이러한 이점을 제공하는 형식을 만드는 방법을 보여 주며 있습니다. 컴파일러는 제공된 패턴이 유효하지 않은 경우 오류를 보고하고 형식 공급자는 일치 할 때 명명 된 속성을 사용하여 그룹에 액세스 할 수 있도록 패턴에서 그룹을 추출 할 수 있습니다. 형식 공급자를 디자인할 때는 노출된 API가 최종 사용자에게 어떻게 보이는지, 이 디자인이 .NET 코드로 변환되는 방식을 고려해야 합니다. 다음 예제에서는 이러한 API를 사용하여 지역 코드의 구성 요소를 얻는 방법을 보여 주며 있습니다.

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

다음 예제에서는 형식 공급자가 이러한 호출을 변환하는 방법을 보여 주어집니다.

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

다음 사항에 유의하세요.

- 표준 정규식 유형은 매개 `RegexTyped` 변수화된 형식을 나타냅니다.

- `RegexTyped` 생성자는 정규표현기 생성기를 호출하여 패턴에 대한 정적 형식 인수를 전달합니다.

- `Match` 메서드의 결과는 표준 <xref:System.Text.RegularExpressions.Match> 유형으로 표시됩니다.

- 명명된 각 그룹은 제공된 속성을 생성하고 속성에 액세스하면 일치 의 `Groups` 컬렉션에 인덱서가 사용됩니다.

다음 코드는 이러한 공급자를 구현하는 논리의 핵심이며 이 예제에서는 제공된 형식에 대한 모든 멤버의 추가를 생략합니다. 추가된 각 멤버에 대한 자세한 내용은 이 항목의 후반부에서 해당 섹션을 참조하십시오. 전체 코드의 경우 CodePlex 웹 사이트에서 [F# 3.0 샘플 팩에서](https://archive.codeplex.com/?p=fsharp3sample) 샘플을 다운로드하십시오.

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

다음 사항에 유의하세요.

- 형식 공급자는 기본값이 제공되므로 `pattern`필수 인 및 `options`선택적 의 .) 라는 두 개의 정적 매개 변수를 사용합니다.

- 정적 인수가 제공된 후 정규식의 인스턴스를 만듭니다. 이 인스턴스는 정규기가 잘못된 경우 예외를 발생시키고 이 오류는 사용자에게 보고됩니다.

- `DefineStaticParameters` 콜백 내에서 인수가 제공된 후 반환되는 형식을 정의합니다.

- 이 코드는 IntelliSense 환경이 간소화된 상태로 유지되도록 true로 설정합니다. `HideObjectMethods` 이 특성으로 `Equals` `GetHashCode`인해 `Finalize`에서 `GetType` 및 멤버가 제공된 개체에 대한 IntelliSense 목록에서 억제됩니다.

- 메서드의 `obj` 기본 유형으로 사용 하지만 다음 예제에서 `Regex` 볼 수 있듯이 이 형식의 런타임 표현으로 개체를 사용 합니다.

- `Regex` 생성자 호출은 정규식이 <xref:System.ArgumentException> 유효하지 않은 경우 를 throw합니다. 컴파일러는 이 예외를 catch하고 컴파일 타임또는 Visual Studio 편집기에서 사용자에게 오류 메시지를 보고합니다. 이 예외를 사용하면 응용 프로그램을 실행하지 않고도 정규식의 유효성을 검사할 수 있습니다.

위에 정의된 형식은 의미 있는 메서드 나 속성을 포함 하지 않기 때문에 아직 유용 하지 않습니다. 먼저 정적 `IsMatch` 메서드를 추가합니다.

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

이전 코드는 문자열을 `IsMatch`입력으로 사용하여 을 반환하는 `bool`메서드를 정의합니다. 유일한 까다로운 부분은 정의 내에서 `args` 인수를 `InvokeCode` 사용하는 것입니다. 이 예제에서는 `args` 이 메서드에 대한 인수를 나타내는 견적 목록입니다. 메서드가 인스턴스 메서드인 경우 첫 번째 `this` 인수는 인수를 나타냅니다. 그러나 정적 메서드의 경우 인수는 모두 메서드에 대한 명시적 인수일 뿐입니다. 인용된 값의 형식은 지정된 반환 형식(이 `bool`경우)과 일치해야 합니다. 또한 이 코드는 `AddXmlDoc` 메서드를 사용하여 제공된 메서드에도 IntelliSense를 통해 제공할 수 있는 유용한 설명서도 있는지 확인합니다.

다음으로 인스턴스 일치 메서드를 추가합니다. 그러나 이 메서드는 그룹에 강력한 `Match` 형식의 방식으로 액세스할 수 있도록 제공 된 형식의 값을 반환 해야 합니다. 따라서 먼저 형식을 `Match` 선언합니다. 이 형식은 정적 인수로 제공된 패턴에 따라 달라지므로 이 형식은 매개 변수화된 형식 정의 내에 중첩되어야 합니다.

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

그런 다음 각 그룹에 대해 일치 유형에 하나의 속성을 추가합니다. 런타임에서 일치는 <xref:System.Text.RegularExpressions.Match> 값으로 표시되므로 속성을 정의하는 따옴표는 <xref:System.Text.RegularExpressions.Match.Groups> 인덱싱된 속성을 사용하여 관련 그룹을 얻어야 합니다.

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

다시 말하지만 제공된 속성에 XML 설명서를 추가합니다. 또한 `GetterCode` 함수가 제공되는 경우 속성을 읽을 수 있으며 `SetterCode` 함수가 제공된 경우 속성을 작성할 수 있으므로 결과 속성만 읽을 수 있습니다.

이제 이 `Match` 유형의 값을 반환하는 인스턴스 메서드를 만들 수 있습니다.

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

인스턴스 메서드를 만들기 때문에 `args.[0]` 메서드가 `RegexTyped` 호출되는 인스턴스를 나타내며 `args.[1]` 입력 인수입니다.

마지막으로 제공된 형식의 인스턴스를 만들 수 있도록 생성자 제공합니다.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

생성자는 제공된 형식의 지우기때문에 `obj` 개체에 다시 boxed되는 표준 .NET Regex 인스턴스를 만들기 위해 지웁니까 됩니다. 이 변경 사항으로 항목의 앞에 지정한 샘플 API 사용이 예상대로 작동합니다. 다음 코드는 완전하고 최종입니다.

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

### <a name="key-lessons"></a>주요 교훈

이 섹션에서는 정적 매개 변수에서 작동하는 형식 공급자를 만드는 방법을 설명합니다. 공급자는 정적 매개 변수를 검사하고 해당 값에 따라 작업을 제공합니다.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>로컬 데이터로 백업되는 형식 공급자

정적 매개 변수뿐만 아니라 로컬 또는 원격 시스템의 정보도 기반으로 형식 공급자가 API를 표시하는 경우가 많습니다. 이 섹션에서는 로컬 데이터 파일과 같은 로컬 데이터를 기반으로 하는 형식 공급자에 대해 설명합니다.

### <a name="simple-csv-file-provider"></a>간단한 CSV 파일 공급자

간단한 예로, CSV(쉼표 분리값) 형식으로 과학 데이터에 액세스하기 위한 형식 공급자를 고려합니다. 이 섹션에서는 CSV 파일에 다음 표와 같이 헤더 행 다음에 부동 지점 데이터가 포함되어 있다고 가정합니다.

|거리(미터)|시간(두 번째)|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

`Distance` 이 섹션에서는 형식의 `float<meter>` 속성과 형식의 `Time` `float<second>`속성을 사용하여 행을 얻는 데 사용할 수 있는 형식을 제공하는 방법을 보여 주며 있습니다. 간단히 하기 위해 다음과 같은 가정이 만들어집니다.

- 헤더 이름은 단위가 없거나 "이름(단위)" 양식이 있으며 쉼표를 포함하지 않습니다.

- 단위는 [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames 모듈(F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) 모듈이 정의하는 대로 모든 시스템 국제(SI) 단위입니다.

- 단위는 모두 복합(예: 미터/초)이 아닌 단순(예: 미터)입니다.

- 모든 열에는 부동 점 데이터가 포함됩니다.

보다 완전한 공급자는 이러한 제한을 완화할 것입니다.

다시 첫 번째 단계는 API의 모양을 고려하는 것입니다. 이전 테이블의 콘텐츠(쉼표로 분리된 형식)를 사용하여 `info.csv` 파일을 지정한 경우 공급자의 사용자는 다음 예제와 비슷한 코드를 작성할 수 있어야 합니다.

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

이 경우 컴파일러는 이러한 호출을 다음 예제와 같은 것으로 변환해야 합니다.

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

최적의 변환을 위해서는 형식 공급자가 `CsvFile` 형식 공급자의 어셈블리에서 실제 형식을 정의해야 합니다. 형식 공급자는 종종 몇 가지 도우미 형식 및 메서드를 사용하여 중요한 논리를 래핑합니다. 측정값은 런타임에 지워지므로 `float[]` 행에 대해 지워진 유형으로 사용할 수 있습니다. 컴파일러는 다른 열을 다른 측정값 형식을 갖는 것으로 처리합니다. 예를 들어, 이 예제의 첫 `float<meter>`번째 열에는 `float<second>`type 이 있고 두 번째 열에는 . 그러나 지워진 표현은 매우 간단하게 유지될 수 있습니다.

다음 코드는 구현의 핵심을 보여 주며, 구현의 핵심을 보여 주시고 있습니다.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

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

구현에 대한 다음 사항을 참고하십시오.

- 오버로드된 생성자는 원본 파일 또는 동일한 스키마가 있는 파일을 읽을 수 있습니다. 이 패턴은 로컬 또는 원격 데이터 원본에 대한 형식 공급자를 작성할 때 일반적이며 이 패턴을 사용하면 로컬 파일을 원격 데이터의 템플릿으로 사용할 수 있습니다.

- 형식 공급자 생성자에게 전달되는 [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) 값을 사용하여 상대 파일 이름을 확인할 수 있습니다.

- 메서드를 `AddDefinitionLocation` 사용하여 제공된 속성의 위치를 정의할 수 있습니다. 따라서 제공된 속성에서 사용하는 `Go To Definition` 경우 CSV 파일은 Visual Studio에서 열립니다.

- 이 `ProvidedMeasureBuilder` 형식을 사용하여 SI 단위를 조회하고 관련 `float<_>` 형식을 생성할 수 있습니다.

### <a name="key-lessons"></a>주요 교훈

이 섹션에서는 데이터 원본 자체에 포함된 간단한 스키마를 사용하여 로컬 데이터 원본에 대한 형식 공급자를 만드는 방법을 설명했습니다.

## <a name="going-further"></a>더 나아가기

다음 섹션에는 추가 학습을 위한 제안사항이 포함되어 있습니다.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>지워진 형식에 대한 컴파일된 코드 살펴보기

형식 공급자의 사용이 내보낸 코드에 어떻게 해당하는지 에 대한 몇 가지 아이디어를 제공하려면 이 `HelloWorldTypeProvider` 항목의 앞에서 사용된 함수를 사용하여 다음 함수를 살펴봅니다.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

다음은 ildasm.exe를 사용하여 디컴파일된 결과 코드의 이미지입니다.

```il
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

예제에서 볼 수 있듯이 형식 `Type1` 및 `InstanceProperty` 속성에 대한 모든 언급이 지워져 관련 런타임 형식에 대한 작업만 남습니다.

### <a name="design-and-naming-conventions-for-type-providers"></a>유형 공급자를 위한 디자인 및 명명 규칙

형식 공급자를 작성할 때 다음 규칙을 준수합니다.

**연결 프로토콜 공급자** 일반적으로 OData 또는 SQL 연결과 같은 데이터 및 서비스 연결 프로토콜에 대한 대부분의 `TypeProvider` 공급자 `TypeProviders`DLL의 이름은 또는 에 끝나야 합니다. 예를 들어 다음 문자열과 유사한 DLL 이름을 사용합니다.

`Fabrikam.Management.BasicTypeProviders.dll`

제공된 형식이 해당 네임스페이스의 멤버인지 확인하고 구현한 연결 프로토콜을 나타냅니다.

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**일반 코딩을 위한 유틸리티 공급자**.  정규식과 같은 유틸리티 형식 공급자의 경우 형식 공급자는 다음 예제와 같이 기본 라이브러리의 일부일 수 있습니다.

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

이 경우 제공된 형식은 일반 .NET 디자인 규칙에 따라 적절한 지점에 표시됩니다.

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**싱글톤 데이터 소스**. 일부 형식 공급자는 단일 전용 데이터 원본에 연결하고 데이터만 제공합니다. 이 경우 접미사를 `TypeProvider` 삭제하고 .NET 명명에 대한 일반 규칙을 사용해야 합니다.

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

자세한 내용은 이 `GetConnection` 항목의 후반부에서 설명하는 디자인 규칙을 참조하십시오.

### <a name="design-patterns-for-type-providers"></a>유형 공급자를 위한 디자인 패턴

다음 섹션에서는 형식 공급자를 작성할 때 사용할 수 있는 디자인 패턴에 대해 설명합니다.

#### <a name="the-getconnection-design-pattern"></a>GetConnection 디자인 패턴

다음 예제와 같이 FSharp.Data.TypeProviders.dll의 형식 공급자가 사용하는 `GetConnection` 패턴을 사용하도록 대부분의 형식 공급자를 작성해야 합니다.

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>원격 데이터 및 서비스로 지원되는 유형 공급자

원격 데이터 및 서비스가 지원하는 형식 공급자를 만들기 전에 연결된 프로그래밍에 내재된 다양한 문제를 고려해야 합니다. 이러한 문제에는 다음과 같은 고려 사항이 포함됩니다.

- 스키마 매핑

- 스키마 변경이 있는 경우 의 생수 및 무효화

- 스키마 캐싱

- 데이터 액세스 작업의 비동기 구현

- LINQ 쿼리를 포함한 지원 쿼리

- 자격 증명 및 인증

이 항목에서는 이러한 문제를 더 자세히 살펴보지 않습니다.

### <a name="additional-authoring-techniques"></a>추가 작성 기술

사용자 고유의 형식 공급자를 작성할 때 다음과 같은 추가 기술을 사용할 수 있습니다.

### <a name="creating-types-and-members-on-demand"></a>주문형 및 멤버 만들기

ProvidedType API에 AddMember 버전이 지연되었습니다.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

이러한 버전은 형식의 주문형 공간을 만드는 데 사용됩니다.

### <a name="providing-array-types-and-generic-type-instantiations"></a>배열 형식 및 일반 형식 인스턴스화 제공

을 포함하여 `MakeArrayType` `MakePointerType` `MakeGenericType` <xref:System.Type> `ProvidedTypeDefinitions`의 모든 인스턴스에서 정상 을 사용하여 제공된 멤버(시그니처에 배열 형식, byref 형식 및 제네릭 형식의 인스턴스화 포함)를 만듭니다.

> [!NOTE]
> 경우에 따라 `ProvidedTypeBuilder.MakeGenericType`에서 도우미를 사용해야 할 수도 있습니다.  자세한 내용은 [유형 공급자 SDK 설명서를](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) 참조하십시오.

### <a name="providing-unit-of-measure-annotations"></a>측정 주석 단위 제공

ProvidedType API는 측정 주석을 제공하기 위한 도우미를 제공합니다. 예를 들어 형식을 `float<kg>`제공하려면 다음 코드를 사용합니다.

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  형식을 `Nullable<decimal<kg/m^2>>`제공하려면 다음 코드를 사용합니다.

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>프로젝트 로컬 또는 스크립트 로컬 리소스 액세스

형식 공급자의 각 인스턴스는 `TypeProviderConfig` 구성 하는 동안 값을 지정할 수 있습니다. 이 값에는 공급자에 대한 "확인 폴더"(즉, 컴파일용 프로젝트 폴더 또는 스크립트가 포함된 디렉터리), 참조된 어셈블리 목록 및 기타 정보가 포함됩니다.

### <a name="invalidation"></a>무효화

공급자는 F# 언어 서비스에 스키마 가정이 변경되었을 수 있음을 알리기 위해 무효화 신호를 발생시킬 수 있습니다. 무효화가 발생하면 공급자가 Visual Studio에서 호스팅되는 경우 형식 검사가 다시 수행됩니다. 공급자가 F# 대화형 또는 F# 컴파일러(fsc.exe)에서 호스팅될 때 이 신호는 무시됩니다.

### <a name="caching-schema-information"></a>캐싱 스키마 정보

공급자는 종종 스키마 정보에 대한 액세스를 캐시해야 합니다. 캐시된 데이터는 정적 매개 변수 또는 사용자 데이터로 지정된 파일 이름을 사용하여 저장해야 합니다. 스키마 캐싱의 예는 `LocalSchemaFile` 어셈블리의 형식 `FSharp.Data.TypeProviders` 공급자의 매개 변수입니다. 이러한 공급자의 구현에서 이 정적 매개 변수는 형식을 공급자가 네트워크를 통해 데이터 원본에 액세스하는 대신 지정된 로컬 파일에서 스키마 정보를 사용하도록 지시합니다. 캐시된 스키마 정보를 사용하려면 정적 매개 `ForceUpdate` 변수도 `false`로 설정해야 합니다. 유사한 기술을 사용하여 온라인 및 오프라인 데이터 액세스를 활성화할 수 있습니다.

### <a name="backing-assembly"></a>백업 어셈블리

`.dll` 또는 `.exe` 파일을 컴파일할 때 생성된 형식에 대한 백업 .dll 파일이 결과 어셈블리에 정적으로 연결됩니다. 이 링크는 중간 언어(IL) 형식 정의 및 백업 어셈블리에서 최종 어셈블리로 관리되는 리소스를 복사하여 만들어집니다. F# 대화형을 사용하면 백업 .dll 파일이 복사되지 않고 대신 F# 대화형 프로세스에 직접 로드됩니다.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>형식 공급자의 예외 및 진단

제공된 형식의 모든 멤버를 모두 사용하여 예외가 발생할 수 있습니다. 모든 경우에 형식 공급자가 예외를 throw하는 경우 호스트 컴파일러는 오류를 특정 형식 공급자에 특성화합니다.

- 형식 공급자 예외는 내부 컴파일러 오류를 발생해서는 안 됩니다.

- 형식 공급자는 경고를 보고할 수 없습니다.

- 형식 공급자가 F# 컴파일러, F# 개발 환경 또는 F# 대화형에서 호스팅되는 경우 해당 공급자의 모든 예외가 catch됩니다. Message 속성은 항상 오류 텍스트이며 스택 추적이 나타나지 않습니다. 예외를 throw하려는 경우 다음과 같은 예제를 throw할 `System.NotSupportedException`수 `System.IO.IOException` `System.Exception`있습니다.

#### <a name="providing-generated-types"></a>생성된 유형 제공

지금까지 이 문서에서는 지워진 형식을 제공하는 방법을 설명했습니다. F#의 형식 공급자 메커니즘을 사용하여 생성된 형식을 제공할 수 있으며, 이 형식은 사용자의 프로그램에 실제 .NET 형식 정의로 추가됩니다. 형식 정의를 사용하여 생성된 제공된 형식을 참조해야 합니다.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

F# 3.0 릴리스의 일부인 ProvidedType-0.2 도우미 코드는 생성된 형식을 제공하기 위한 제한된 지원만 있습니다. 생성된 형식 정의에 대해 다음 문은 true여야 합니다.

- `isErased`은 `false`로 설정해야 합니다.

- 생성된 코드 조각에 대한 컨테이너를 나타내는 새로 생성된 `ProvidedAssembly()`형식에 생성된 형식을 추가해야 합니다.

- 공급자는 디스크에 일치하는 .dll 파일이 있는 실제 백업 .NET .dll 파일이 있는 어셈블리가 있어야 합니다.

## <a name="rules-and-limitations"></a>규칙 및 제한 사항

형식 공급자를 작성할 때는 다음 규칙과 제한 사항에 유의하십시오.

### <a name="provided-types-must-be-reachable"></a>제공된 유형에 연결할 수 있어야 합니다.

제공된 모든 형식은 중첩되지 않은 형식에서 연결할 수 있어야 합니다. 중첩되지 않은 형식은 `TypeProviderForNamespaces` 생성자 호출 또는 에 대한 `AddNamespace`호출에서 제공됩니다. 예를 들어 공급자가 형식을 `StaticClass.P : T`제공하는 경우 T가 중첩되지 않은 형식이거나 중첩된 형식인지 확인해야 합니다.

예를 들어 일부 공급자에는 이러한 `DataTypes` `T1, T2, T3, ...` 형식을 포함하는 정적 클래스가 있습니다. 그렇지 않으면 어셈블리 A의 T 형식에 대한 참조가 발견되었지만 해당 어셈블리에서 형식을 찾을 수 없다는 오류가 나타납니다. 이 오류가 나타나면 공급자 형식에서 모든 하위 유형에 도달할 수 있는지 확인합니다. 참고: `T1, T2, T3...` 이러한 형식을 *즉석* 에서 유형이라고 합니다. 액세스 가능한 네임스페이스 또는 상위 형식에 넣어야 합니다.

### <a name="limitations-of-the-type-provider-mechanism"></a>형식 공급자 메커니즘의 제한 사항

F#의 형식 공급자 메커니즘에는 다음과 같은 제한 사항이 있습니다.

- F#의 형식 공급자에 대한 기본 인프라는 제공된 제네릭 형식 또는 제공된 제네릭 메서드를 지원하지 않습니다.

- 메커니즘은 정적 매개 변수를 사용 하 고 중첩 된 형식을 지원 하지 않습니다.

## <a name="development-tips"></a>개발 팁

개발 과정에서 다음과 같은 유용한 팁을 찾을 수 있습니다.

### <a name="run-two-instances-of-visual-studio"></a>비주얼 스튜디오의 두 인스턴스 실행

테스트 IDE가 type 공급자를 다시 빌드하지 못하도록 하는 .dll 파일에 대한 잠금을 수행하므로 한 인스턴스에서 형식 공급자를 개발하고 다른 인스턴스에서 공급자를 테스트할 수 있습니다. 따라서 공급자가 첫 번째 인스턴스에 빌드되는 동안 Visual Studio의 두 번째 인스턴스를 닫은 다음 공급자가 빌드된 후 두 번째 인스턴스를 다시 열어야 합니다.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>fsc.exe 호출을 사용하여 유형 공급자를 디버그

다음 도구를 사용하여 형식 공급자를 호출할 수 있습니다.

- fsc.exe(F# 명령줄 컴파일러)

- fsi.exe (F# 인터랙티브 컴파일러)

- devenv.exe (비주얼 스튜디오)

테스트 스크립트 파일(예: script.fsx)에서 fsc.exe를 사용하여 형식 공급자를 가장 쉽게 디버깅할 수 있습니다. 명령 프롬프트에서 디버거를 시작할 수 있습니다.

```console
devenv /debugexe fsc.exe script.fsx
```

  인쇄-stdout 로깅을 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [형식 공급자](index.md)
- [형식 공급자 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
