---
title: '자습서: 형식 공급자 만들기'
description: '기본 개념을 설명 하는 몇 가지 간단한 형식 공급자를 검사 하 여 F # 3.0에서 고유한 F # 형식 공급자를 만드는 방법에 대해 알아봅니다.'
ms.date: 11/04/2019
ms.openlocfilehash: 71225614ed983a76d35c214faa87bbad0fbb7d24
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810874"
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="14190-103">자습서: 형식 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="14190-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="14190-104">F #의 형식 공급자 메커니즘은 정보 기능이 풍부한 프로그래밍에 대 한 지원의 중요 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="14190-105">이 자습서에서는 기본 개념을 설명 하기 위해 몇 가지 간단한 형식 공급자를 개발 하는 과정을 통해 사용자 고유의 형식 공급자를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="14190-106">F #의 형식 공급자 메커니즘에 대 한 자세한 내용은 [형식 공급자](index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="14190-107">F # 에코 시스템에는 일반적으로 사용 되는 인터넷 및 엔터프라이즈 데이터 서비스에 대 한 형식 공급자 범위가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="14190-108">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="14190-108">For example:</span></span>

- <span data-ttu-id="14190-109">[Fsharp.core](https://fsharp.github.io/FSharp.Data/) 에는 JSON, XML, CSV 및 HTML 문서 형식에 대 한 형식 공급자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="14190-110">[Sqlprovider](https://fsprojects.github.io/SQLProvider/) 는 이러한 데이터 원본에 대 한 개체 매핑 및 F # LINQ 쿼리를 통해 SQL database에 대 한 강력한 형식의 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="14190-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/)에는 F#에서 컴파일 시간에 확인하여 포함되는 T-SQL에 대한 형식 공급자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="14190-112">[Fsharp.core 공급자](https://fsprojects.github.io/FSharp.Data.TypeProviders/) 는 SQL, Entity Framework, ODATA 및 WSDL Data services에 액세스 하기 위한 .NET Framework 프로그래밍에만 사용할 수 있는 이전 형식 공급자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="14190-113">필요한 경우 사용자 지정 형식 공급자를 만들거나 다른 사용자가 만든 형식 공급자를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="14190-114">예를 들어 조직에는 각각 자체의 안정적인 데이터 스키마를 포함 하는 많은 수의 명명 된 데이터 집합을 제공 하는 데이터 서비스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="14190-115">스키마를 읽고 강력한 형식의 방식으로 프로그래머에 게 현재 데이터 집합을 제공 하는 형식 공급자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="14190-116">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="14190-116">Before You Start</span></span>

<span data-ttu-id="14190-117">형식 공급자 메커니즘은 주로 안정적인 데이터 및 서비스 정보 공간을 F # 프로그래밍 환경으로 삽입 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="14190-118">이 메커니즘은 프로그램 논리와 관련 된 방식으로 프로그램 실행 중에 스키마가 변경 되는 정보 공간을 삽입 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="14190-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="14190-119">또한이 메커니즘은 도메인에 일부 유효한 사용이 포함 되어 있는 경우에도 언어 간 메타 프로그래밍을 위해 디자인 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="14190-120">필요한 경우에만이 메커니즘을 사용 하 고 형식 공급자의 개발에서 매우 높은 값을 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="14190-121">스키마를 사용할 수 없는 형식 공급자를 작성 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="14190-122">마찬가지로 일반적인 (또는 기존) .NET 라이브러리에서 충분 한 형식 공급자를 작성 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="14190-123">시작 하기 전에 다음 질문을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="14190-124">정보 소스에 대 한 스키마가 있나요?</span><span class="sxs-lookup"><span data-stu-id="14190-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="14190-125">그렇다면 F # 및 .NET 유형 시스템에 대 한 매핑은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="14190-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="14190-126">기존 (동적으로 형식화 된) API를 구현에 대 한 시작 지점으로 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="14190-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="14190-127">사용자와 조직에서 형식 공급자를 충분히 사용 하 여 it를 효율적으로 작성할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="14190-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="14190-128">정상적인 .NET 라이브러리가 사용자의 요구를 충족 하나요?</span><span class="sxs-lookup"><span data-stu-id="14190-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="14190-129">스키마가 얼마나 변경 되나요?</span><span class="sxs-lookup"><span data-stu-id="14190-129">How much will your schema change?</span></span>

- <span data-ttu-id="14190-130">코딩 중에 변경 됩니까?</span><span class="sxs-lookup"><span data-stu-id="14190-130">Will it change during coding?</span></span>

- <span data-ttu-id="14190-131">코딩 세션 간에 변경 됩니까?</span><span class="sxs-lookup"><span data-stu-id="14190-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="14190-132">프로그램 실행 중에 변경 됩니까?</span><span class="sxs-lookup"><span data-stu-id="14190-132">Will it change during program execution?</span></span>

<span data-ttu-id="14190-133">형식 공급자는 런타임에 그리고 컴파일된 코드의 수명 동안 안정적으로 작동 하는 상황에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="14190-134">단순 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="14190-134">A Simple Type Provider</span></span>

<span data-ttu-id="14190-135">이 샘플은 `examples` [F # 형식 공급자 SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)의 디렉터리에 있는 샘플과 유사한 HelloWorldTypeProvider입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="14190-136">이 공급자는 다음 코드와 같이 F # 서명 구문을 사용 하 고 모든를 제외 하 고 세부 정보를 생략 하는 것과 같이, 100의 지워진 형식을 포함 하는 "형식 공간"을 사용할 수 있도록 합니다 `Type1` .</span><span class="sxs-lookup"><span data-stu-id="14190-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="14190-137">지워진 형식에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 [지워진 제공 형식에 대 한 세부](#details-about-erased-provided-types) 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

<span data-ttu-id="14190-138">제공 된 형식 및 멤버 집합은 정적으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="14190-139">이 예제에서는 공급자의 기능을 활용 하 여 스키마에 종속 된 형식을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="14190-140">형식 공급자의 구현은 다음 코드에서 간략하게 설명 하 고 세부 정보는이 항목의 이후 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

> [!WARNING]
> <span data-ttu-id="14190-141">이 코드와 온라인 샘플 간에는 차이점이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-141">There may be differences between this code and the online samples.</span></span>

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

<span data-ttu-id="14190-142">이 공급자를 사용 하려면 별도의 Visual Studio 인스턴스를 열고 F # 스크립트를 만든 다음, 다음 코드에 표시 된 대로 #r를 사용 하 여 스크립트에서 공급자에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="14190-143">그런 다음 `Samples.HelloWorldTypeProvider` 형식 공급자가 생성 한 네임 스페이스에서 형식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="14190-144">공급자를 다시 컴파일하기 전에 공급자 DLL을 사용 하는 F# 대화형 Visual Studio의 모든 인스턴스를 닫았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="14190-145">그렇지 않으면 출력 DLL이 잠기므로 빌드 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="14190-146">Print 문을 사용 하 여이 공급자를 디버깅 하려면 공급자와 관련 된 문제를 노출 하는 스크립트를 만든 후 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="14190-147">Visual Studio를 사용 하 여이 공급자를 디버깅 하려면 관리자 자격 증명을 사용 하 여 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-147">To debug this provider by using Visual Studio, open the Developer Command Prompt for Visual Studio with administrative credentials, and run the following command:</span></span>

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="14190-148">또는 Visual Studio를 열고, 디버그 메뉴를 열고,를 선택 하 `Debug/Attach to process…` 고, 스크립트를 편집 하는 다른 프로세스에 연결 `devenv` 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="14190-149">이 메서드를 사용 하 여 두 번째 인스턴스 (전체 IntelliSense 및 기타 기능 사용)에 식을 대화형으로 입력 하 여 형식 공급자에서 특정 논리를 보다 쉽게 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="14190-150">내 코드만 디버깅을 사용 하지 않도록 설정 하 여 생성 된 코드에서 오류를 더 잘 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="14190-151">이 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [디버거를 사용 하 여 코드 탐색](/visualstudio/debugger/navigating-through-code-with-the-debugger)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="14190-152">또한 메뉴를 연 `Debug` 다음 `Exceptions` Ctrl + Alt + E 키를 선택 하 여 대화 상자를 열면 첫 번째 예외 catch를 설정할 수도 있습니다 `Exceptions` .</span><span class="sxs-lookup"><span data-stu-id="14190-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="14190-153">이 대화 상자의 아래에서 `Common Language Runtime Exceptions` 확인란을 선택 `Thrown` 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="14190-154">형식 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="14190-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="14190-155">이 섹션에서는 형식 공급자 구현의 주요 섹션을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="14190-156">먼저 사용자 지정 형식 공급자 자체에 대 한 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="14190-157">이 형식은 public 이어야 하며, 별도의 F # 프로젝트에서 해당 형식을 포함 하는 어셈블리를 참조할 때 컴파일러가 형식 공급자를 인식할 수 있도록 [typeprovider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderattribute.html) 특성으로 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-157">This type must be public, and you must mark it with the [TypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderattribute.html) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="14190-158">*Config* 매개 변수는 선택 사항이 며, 있는 경우 F # 컴파일러가 만드는 형식 공급자 인스턴스에 대 한 컨텍스트 구성 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="14190-159">다음으로 [ITypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-itypeprovider.html) 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-159">Next, you implement the [ITypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-itypeprovider.html) interface.</span></span> <span data-ttu-id="14190-160">이 경우 `TypeProviderForNamespaces` API의 형식을 `ProvidedTypes` 기본 형식으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="14190-161">이 도우미 형식은 적극적으로 제공 되는 네임 스페이스의 한정 된 컬렉션을 제공할 수 있습니다. 각 네임 스페이스는 고정 된 수의 고정 된 형식을 직접 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="14190-162">이 컨텍스트에서 공급자는 필요 하거나 사용 하지 않더라도 형식을 *적극적* 으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="14190-163">그런 다음 제공 된 형식에 대 한 네임 스페이스를 지정 하는 로컬 전용 값을 정의 하 고 형식 공급자 어셈블리 자체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="14190-164">이 어셈블리는 나중에 제공 된 지워진 형식의 논리적 부모 형식으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="14190-165">다음에는 각 형식 Type1을 제공 하는 함수를 만듭니다. Type100.</span><span class="sxs-lookup"><span data-stu-id="14190-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="14190-166">이 기능에 대해서는이 항목의 뒷부분에서 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="14190-167">다음으로 100 제공 유형을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="14190-168">다음으로 형식을 제공 된 네임 스페이스로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="14190-169">마지막으로, 형식 공급자 DLL을 만드는 중임을 나타내는 어셈블리 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="14190-170">한 형식 및 해당 멤버 제공</span><span class="sxs-lookup"><span data-stu-id="14190-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="14190-171">`makeOneProvidedType`함수는 형식 중 하나를 제공 하는 실제 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) =
…
```

<span data-ttu-id="14190-172">이 단계에서는이 함수를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="14190-173">먼저 제공 된 형식 (예: Type1, when n = 1, Type57, n = 57 인 경우)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14190-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="14190-174">다음 사항에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-174">You should note the following points:</span></span>

- <span data-ttu-id="14190-175">제공 된 형식이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="14190-175">This provided type is erased.</span></span>  <span data-ttu-id="14190-176">기본 형식이 임을 나타내므로 `obj` 인스턴스는 컴파일된 코드에서 [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) 형식의 값으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) in compiled code.</span></span>

- <span data-ttu-id="14190-177">중첩 되지 않은 형식을 지정 하는 경우 어셈블리와 네임 스페이스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="14190-178">지워진 형식의 경우 어셈블리는 형식 공급자 어셈블리 자체 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="14190-179">그런 다음 형식에 XML 문서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="14190-180">이 설명서는 지연 됩니다. 즉, 호스트 컴파일러에 필요한 경우에는 요청 시에 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="14190-181">다음에는 제공 된 정적 속성을 형식에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="14190-182">이 속성을 가져오면 항상 문자열 "Hello!"로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="14190-183">속성의는 `GetterCode` 호스트 컴파일러가 속성을 가져오기 위해 생성 하는 코드를 나타내는 F # 따옴표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="14190-184">인용구에 대 한 자세한 내용은 [코드 인용 (F #)](../../language-reference/code-quotations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-184">For more information about quotations, see [Code Quotations (F#)](../../language-reference/code-quotations.md).</span></span>

<span data-ttu-id="14190-185">속성에 XML 문서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="14190-186">이제 제공 된 속성을 제공 된 형식에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="14190-187">제공 된 멤버를 한 형식에만 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="14190-188">그렇지 않은 경우에는 멤버에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="14190-189">이제 매개 변수를 사용 하지 않는 제공 된 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14190-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="14190-190">생성자의는 `InvokeCode` 생성자가 호출 될 때 호스트 컴파일러가 생성 하는 코드를 나타내는 F # 따옴표를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="14190-191">예를 들어 다음 생성자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="14190-192">제공 된 형식의 인스턴스는 기본 데이터 "the object data"를 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="14190-193">따옴표 붙은 코드는 제공 된 형식을 선언할 때 지정한 대로이 형식이 제공 된 형식을 모두 지우기 때문에 [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) 로의 변환을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-193">The quoted code includes a conversion to [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="14190-194">생성자에 XML 문서를 추가 하 고 제공 된 형식에 제공 된 생성자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="14190-195">하나의 매개 변수를 사용 하는 제공 된 두 번째 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14190-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="14190-196">`InvokeCode`생성자에 대 한는 호스트 컴파일러가 메서드를 호출 하기 위해 생성 한 코드를 나타내는 F # 따옴표를 다시 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="14190-197">예를 들어 다음 생성자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="14190-198">제공 된 형식의 인스턴스는 기본 데이터 "10"을 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="14190-199">함수가 따옴표를 반환 한다는 것을 이미 알고 있을 수 있습니다 `InvokeCode` .</span><span class="sxs-lookup"><span data-stu-id="14190-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="14190-200">이 함수에 대 한 입력은 생성자 매개 변수 별로 하나씩 식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="14190-201">이 경우 단일 매개 변수 값을 나타내는 식은에서 사용할 수 있습니다 `args.[0]` .</span><span class="sxs-lookup"><span data-stu-id="14190-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="14190-202">생성자를 호출 하는 코드는 반환 값을 지워진 형식으로 강제 변환 합니다 `obj` .</span><span class="sxs-lookup"><span data-stu-id="14190-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="14190-203">제공 된 두 번째 생성자를 형식에 추가한 후에는 제공 된 인스턴스 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14190-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="14190-204">이 속성을 가져오면 표시 개체인 문자열의 길이가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="14190-205">`GetterCode`속성은 호스트 컴파일러가 속성을 얻기 위해 생성 하는 코드를 지정 하는 F # 따옴표를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="14190-206">와 같이 `InvokeCode` `GetterCode` 함수는 따옴표를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="14190-207">호스트 컴파일러는 인수 목록을 사용 하 여이 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="14190-208">이 경우 인수는를 사용 하 여 액세스할 수 있는 getter가 호출 되는 인스턴스를 나타내는 단일 식만 포함 합니다 `args.[0]` .</span><span class="sxs-lookup"><span data-stu-id="14190-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.</span></span> <span data-ttu-id="14190-209">`GetterCode`그런 다음의 구현은 지운 형식의 결과 따옴표로 스플라이스 `obj` , 캐스팅은 개체가 문자열인 형식을 확인 하는 컴파일러의 메커니즘을 충족 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-209">The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="14190-210">의 다음 부분에서는 `makeOneProvidedType` 하나의 매개 변수를 사용 하는 인스턴스 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

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

<span data-ttu-id="14190-211">마지막으로 100 중첩 된 속성을 포함 하는 중첩 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14190-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="14190-212">이 중첩 된 형식과 해당 속성의 생성은 지연 됩니다. 즉, 요청 시 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

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

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="14190-213">지워진 제공 유형에 대 한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="14190-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="14190-214">이 섹션의 예제에서는 다음과 같은 경우에 특히 유용한 *지워진 제공 형식만*제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="14190-215">데이터 및 메서드만 포함 하는 정보 공간에 대 한 공급자를 작성 하는 경우</span><span class="sxs-lookup"><span data-stu-id="14190-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="14190-216">정확한 런타임 형식 의미 체계가 중요 하지 않은 공급자를 작성 하는 경우 정보 공간을 실제로 사용 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="14190-217">정보 공간에 대 한 공급자를 작성 하는 경우 해당 정보 공간에 대 한 실제 .NET 형식을 생성 하는 것은 기술적으로는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="14190-218">이 예제에서 제공 된 각 형식은 형식으로 지워지고 `obj` 형식의 모든 사용은 컴파일된 코드에서 형식으로 표시 됩니다 `obj` .</span><span class="sxs-lookup"><span data-stu-id="14190-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="14190-219">실제로 이러한 예제의 기본 개체는 문자열 이지만 형식은 `System.Object` .net 컴파일 코드에서로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="14190-220">형식 지우기를 사용할 때와 마찬가지로 명시적 boxing, unboxing 및 캐스트를 사용 하 여 방해할 지워진 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="14190-221">이 경우 개체를 사용할 때 유효 하지 않은 캐스트 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="14190-222">공급자 런타임은 고유한 개인 표현 형식을 정의 하 여 가양성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="14190-223">삭제 한 형식은 F # 자체에서 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="14190-224">제공 된 유형만 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-224">Only provided types may be erased.</span></span> <span data-ttu-id="14190-225">형식 공급자에 대해 지워진 유형을 사용 하거나 지워진 유형을 제공 하는 공급자를 사용 하는 경우의 실제 및 의미 체계를 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="14190-226">지워진 유형에는 실제 .NET 유형이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="14190-227">따라서 형식에 대해 정확한 리플렉션을 수행할 수 없으며, 런타임 캐스트를 사용 하는 경우와 정확한 런타임 형식 의미 체계를 사용 하는 기타 기술을 사용 하는 경우에는 지워진 형식을 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="14190-228">지워진 형식의 Subversion은 런타임에 형식 캐스팅 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="14190-229">지워진 제공 형식에 대 한 표현 선택</span><span class="sxs-lookup"><span data-stu-id="14190-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="14190-230">지워진 제공 형식의 일부 사용에는 표현이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="14190-231">예를 들어, 지워진 제공 된 형식에는 정적 속성 및 멤버만 포함 되 고 생성자는 포함 되지 않을 수 있으며, 메서드나 속성은 형식의 인스턴스를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="14190-232">지워진 제공 된 유형의 인스턴스에 도달할 수 있는 경우 다음 질문을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="14190-233">**제공 된 형식의 지우기는 무엇 인가요?**</span><span class="sxs-lookup"><span data-stu-id="14190-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="14190-234">제공 된 형식을 지울 때 형식이 컴파일된 .NET 코드에 표시 되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="14190-235">제공 된 지워진 클래스 형식을 삭제 하는 것은 항상 형식의 상속 체인에서 삭제 되지 않은 첫 번째 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="14190-236">제공 된 지워진 인터페이스 형식은 항상 지워집니다 `System.Object` .</span><span class="sxs-lookup"><span data-stu-id="14190-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="14190-237">**제공 된 형식의 표현은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="14190-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="14190-238">지워진 제공 된 형식에 대해 가능한 개체 집합을 해당 표현 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="14190-239">이 문서의 예제에서 모든 지워진 제공 된 형식의 표현은 `Type1..Type100` 항상 문자열 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="14190-240">제공 된 형식의 모든 표현은 제공 된 형식의 지우기와 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="14190-241">그렇지 않으면 F # 컴파일러에서 형식 공급자 사용에 대 한 오류를 제공 하거나, 유효 하지 않은 비안정형 .NET 코드가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="14190-242">형식 공급자는 유효하지 않은 표현을 제공하는 코드를 반환하는 경우 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="14190-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="14190-243">다음 방법 중 하나를 사용 하 여 제공 된 개체에 대 한 표현을 선택할 수 있습니다 .이 두 가지 방법 모두 매우 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="14190-244">기존 .NET 형식에 대 한 강력한 형식의 래퍼를 제공 하는 경우 형식에서 해당 형식을 지우거 나, 해당 형식의 인스턴스를 표현으로 사용 하거나, 두 가지 방법을 모두 사용 하는 것이 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="14190-245">이 방법은 강력한 형식의 버전을 사용할 때 해당 형식에 대 한 대부분의 기존 메서드가 여전히 적합 한 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="14190-246">기존 .NET API와 크게 다른 API를 만들려는 경우 제공 된 형식에 대 한 형식 지우기 및 표현이 되는 런타임 형식을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="14190-247">이 문서의 예제에서는 문자열을 제공 된 개체의 표현으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="14190-248">다른 개체를 사용 하 여 표현 하는 것이 적합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="14190-249">예를 들어 사전을 속성 모음으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="14190-250">또는 형식 공급자에서 런타임에 사용 되는 형식을 정의 하 여 하나 이상의 런타임 작업과 함께 표현을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="14190-251">제공 된 멤버는이 개체 형식의 인스턴스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="14190-252">이 경우에는를 생성할 때이 형식을로 지정 하 여 형식 지우기로이 형식을 사용할 수 있습니다 (옵션) `baseType` `ProvidedTypeDefinition` .</span><span class="sxs-lookup"><span data-stu-id="14190-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="14190-253">주요 단원</span><span class="sxs-lookup"><span data-stu-id="14190-253">Key Lessons</span></span>

<span data-ttu-id="14190-254">이전 단원에서는 다양 한 형식, 속성 및 메서드를 제공 하는 간단한 지우기 형식 공급자를 만드는 방법을 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="14190-255">또한이 섹션에서는 형식 공급자에서 지워진 형식을 제공 하는 경우의 장점과 단점을 비롯 하 여 형식 지우기의 개념에 대해 설명 하 고, 지워진 형식의 표현에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="14190-256">정적 매개 변수를 사용 하는 형식 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="14190-257">공급자가 로컬 또는 원격 데이터에 액세스할 필요가 없는 경우에도 정적 데이터를 사용 하 여 형식 공급자를 매개 변수화 하는 기능이 많은 흥미로운 시나리오를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="14190-258">이 섹션에서는 이러한 공급자를 통합 하기 위한 몇 가지 기본 기술에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="14190-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="14190-259">선택 된 Regex 공급자 유형</span><span class="sxs-lookup"><span data-stu-id="14190-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="14190-260"><xref:System.Text.RegularExpressions.Regex>다음 컴파일 시간을 제공 하는 인터페이스에서 .net 라이브러리를 래핑하는 정규식에 대 한 형식 공급자를 구현 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="14190-261">정규식이 유효한 지 여부를 확인 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="14190-262">정규식의 그룹 이름을 기반으로 하는 일치 항목에 명명 된 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="14190-263">이 섹션에서는 형식 공급자를 사용 하 여 `RegexTyped` 이러한 혜택을 제공 하기 위해 정규식 패턴에서 매개 변수화 하는 형식을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14190-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="14190-264">제공 된 패턴이 유효 하지 않을 경우 컴파일러에서 오류를 보고 하 고, 형식 공급자가 패턴에서 그룹을 추출 하 여 일치 하는 명명 된 속성을 사용 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="14190-265">형식 공급자를 디자인할 때 노출 되는 API가 최종 사용자에 게 표시 되는 방법 및이 디자인을 .NET 코드로 변환 하는 방법을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="14190-266">다음 예제에서는 이러한 API를 사용 하 여 지역 코드의 구성 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14190-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="14190-267">다음 예제에서는 형식 공급자가 이러한 호출을 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14190-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="14190-268">다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-268">Note the following points:</span></span>

- <span data-ttu-id="14190-269">표준 Regex 형식은 매개 변수가 있는 `RegexTyped` 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14190-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="14190-270">`RegexTyped`생성자는 Regex 생성자를 호출 하 여 패턴에 대 한 정적 형식 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="14190-271">메서드의 결과는 `Match` 표준 형식으로 표현 됩니다 <xref:System.Text.RegularExpressions.Match> .</span><span class="sxs-lookup"><span data-stu-id="14190-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="14190-272">각 명명 된 그룹은 제공 된 속성을 생성 하 고 속성에 액세스 하면 일치 하는 컬렉션에 대해 인덱서가 사용 `Groups` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="14190-273">다음 코드는 이러한 공급자를 구현 하는 논리의 핵심 이며,이 예제에서는 제공 된 형식에 대 한 모든 멤버의 추가를 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="14190-274">추가 된 각 멤버에 대 한 자세한 내용은이 항목의 뒷부분에 있는 해당 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="14190-275">전체 코드를 보려면 CodePlex 웹 사이트의 [F # 3.0 샘플 팩](https://archive.codeplex.com/?p=fsharp3sample) 에서 샘플을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://archive.codeplex.com/?p=fsharp3sample) on the CodePlex website.</span></span>

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

<span data-ttu-id="14190-276">다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-276">Note the following points:</span></span>

- <span data-ttu-id="14190-277">형식 공급자는 두 개의 정적 매개 변수를 사용 합니다 .이 매개 변수는 `pattern` 필수 이며 `options` 기본값은 제공 되기 때문입니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="14190-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="14190-278">정적 인수를 제공한 후 정규식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14190-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="14190-279">Regex의 형식이 잘못 된 경우이 인스턴스는 예외를 throw 하 고이 오류는 사용자에 게 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="14190-280">콜백 내에서 `DefineStaticParameters` 인수를 제공한 후에 반환 되는 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="14190-281">이 코드 `HideObjectMethods` 를 true로 설정 하면 IntelliSense 환경이 간소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="14190-282">이 특성은 `Equals` 제공 된 `GetHashCode` `Finalize` `GetType` 개체에 대 한 IntelliSense 목록에서,, 및 멤버를 표시 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="14190-283">`obj`메서드의 기본 형식으로를 사용 하지만 `Regex` 다음 예제와 같이 개체를이 형식의 런타임 표현으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="14190-284">정규식에 대 한 호출은 `Regex` 정규식이 <xref:System.ArgumentException> 유효 하지 않을 때을 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="14190-285">컴파일러는이 예외를 catch 하 고 컴파일 타임 또는 Visual Studio 편집기에서 사용자에 게 오류 메시지를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="14190-286">이 예외를 사용 하면 응용 프로그램을 실행 하지 않고 정규식의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="14190-287">위에서 정의한 형식은 의미 있는 메서드나 속성을 포함 하지 않기 때문에 아직 유용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="14190-288">먼저 정적 메서드를 추가 합니다 `IsMatch` .</span><span class="sxs-lookup"><span data-stu-id="14190-288">First, add a static `IsMatch` method:</span></span>

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

<span data-ttu-id="14190-289">이전 코드는 `IsMatch` 문자열을 입력으로 사용 하 고를 반환 하는 메서드를 정의 합니다 `bool` .</span><span class="sxs-lookup"><span data-stu-id="14190-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="14190-290">유일한 까다로운 부분은 `args` 정의 내에서 인수를 사용 하는 것입니다 `InvokeCode` .</span><span class="sxs-lookup"><span data-stu-id="14190-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="14190-291">이 예제에서 `args` 는이 메서드에 대 한 인수를 나타내는 인용구의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="14190-292">메서드가 인스턴스 메서드인 경우 첫 번째 인수는 인수를 나타냅니다 `this` .</span><span class="sxs-lookup"><span data-stu-id="14190-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="14190-293">그러나 정적 메서드의 경우 인수는 모두 단순히 메서드에 대 한 명시적 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="14190-294">따옴표 붙은 값의 형식은 지정 된 반환 형식 (이 경우)과 일치 해야 합니다 `bool` .</span><span class="sxs-lookup"><span data-stu-id="14190-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="14190-295">또한이 코드에서는 메서드를 사용 하 여 `AddXmlDoc` 제공 된 메서드에 IntelliSense를 통해 제공할 수 있는 유용한 설명서가 있는지도 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="14190-296">다음으로, 인스턴스 일치 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-296">Next, add an instance Match method.</span></span> <span data-ttu-id="14190-297">그러나이 메서드는 지정 된 형식의 값을 반환 해야 `Match` 그룹에 강력한 형식의 방식으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="14190-298">따라서 먼저 `Match` 형식을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="14190-299">이 형식은 정적 인수로 제공 된 패턴에 따라 달라 지므로이 형식은 매개 변수가 있는 형식 정의 내에 중첩 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="14190-300">그런 다음 각 그룹의 일치 형식에 하나의 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="14190-301">런타임에 일치 항목은 값으로 표시 <xref:System.Text.RegularExpressions.Match> 되므로 속성을 정의 하는 따옴표는 인덱싱된 속성을 사용 하 여 <xref:System.Text.RegularExpressions.Match.Groups> 관련 그룹을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

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

<span data-ttu-id="14190-302">다시, 제공 된 속성에 XML 문서를 추가 하 고 있음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="14190-303">또한 함수를 제공 하는 경우 속성을 읽을 수 `GetterCode` 있으며 함수를 제공 하는 경우 속성을 쓸 수 `SetterCode` 있으므로 결과 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="14190-304">이제 다음 형식의 값을 반환 하는 인스턴스 메서드를 만들 수 있습니다 `Match` .</span><span class="sxs-lookup"><span data-stu-id="14190-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

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

<span data-ttu-id="14190-305">인스턴스 메서드를 만들기 때문에는 `args.[0]` 메서드가 호출 되는 인스턴스를 나타내고 `RegexTyped` `args.[1]` 는 입력 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="14190-306">마지막으로 제공 된 형식의 인스턴스를 만들 수 있도록 생성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="14190-307">생성자는 표준 .NET Regex 인스턴스를 만들 때만 삭제 하 고,는 제공 된 형식을 삭제 하기 때문에 개체에 다시 boxed 됩니다 `obj` .</span><span class="sxs-lookup"><span data-stu-id="14190-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="14190-308">이와 같이 변경 하면 항목에서 이전에 지정한 샘플 API 사용이 예상 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="14190-309">다음 코드는 전체 및 최종입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-309">The following code is complete and final:</span></span>

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

### <a name="key-lessons"></a><span data-ttu-id="14190-310">주요 단원</span><span class="sxs-lookup"><span data-stu-id="14190-310">Key Lessons</span></span>

<span data-ttu-id="14190-311">이 섹션에서는 정적 매개 변수에서 작동 하는 형식 공급자를 만드는 방법에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="14190-312">공급자는 정적 매개 변수를 확인 하 고 해당 값을 기반으로 작업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-312">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="14190-313">로컬 데이터로 지원 되는 형식 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="14190-314">정적 매개 변수 뿐만 아니라 로컬 또는 원격 시스템의 정보를 기반으로 Api를 제공 하기 위해 형식 공급자를 사용 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="14190-315">이 섹션에서는 로컬 데이터 파일과 같은 로컬 데이터를 기반으로 하는 형식 공급자에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-315">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="14190-316">간단한 CSV 파일 공급자</span><span class="sxs-lookup"><span data-stu-id="14190-316">Simple CSV File Provider</span></span>

<span data-ttu-id="14190-317">간단한 예로 쉼표로 구분 된 값 (CSV) 형식으로 과학적 데이터에 액세스 하는 형식 공급자를 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="14190-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="14190-318">이 섹션에서는 다음 표와 같이 CSV 파일에 헤더 행과 부동 소수점 데이터가 포함 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="14190-319">거리 (미터)</span><span class="sxs-lookup"><span data-stu-id="14190-319">Distance (meter)</span></span>|<span data-ttu-id="14190-320">시간 (초)</span><span class="sxs-lookup"><span data-stu-id="14190-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="14190-321">50.0</span><span class="sxs-lookup"><span data-stu-id="14190-321">50.0</span></span>|<span data-ttu-id="14190-322">3.7</span><span class="sxs-lookup"><span data-stu-id="14190-322">3.7</span></span>|
|<span data-ttu-id="14190-323">100.0</span><span class="sxs-lookup"><span data-stu-id="14190-323">100.0</span></span>|<span data-ttu-id="14190-324">5.2</span><span class="sxs-lookup"><span data-stu-id="14190-324">5.2</span></span>|
|<span data-ttu-id="14190-325">150.0</span><span class="sxs-lookup"><span data-stu-id="14190-325">150.0</span></span>|<span data-ttu-id="14190-326">6.4</span><span class="sxs-lookup"><span data-stu-id="14190-326">6.4</span></span>|

<span data-ttu-id="14190-327">이 섹션에서는 형식의 `Distance` 속성 `float<meter>` 및 `Time` 형식의 속성을 사용 하 여 행을 가져오는 데 사용할 수 있는 형식을 제공 하는 방법을 보여 줍니다 `float<second>` .</span><span class="sxs-lookup"><span data-stu-id="14190-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="14190-328">편의상 다음과 같은 가정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="14190-329">헤더 이름은 단위 이거나 "이름 (단위)" 형식이 며 쉼표를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="14190-330">단위는 [fsharp.core (F #)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitnames.html) 모듈이 정의 하는 모든 SI (System 국제) 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-330">Units are all System International (SI) units as the [FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitnames.html) module defines.</span></span>

- <span data-ttu-id="14190-331">단위는 복합이 아닌 모든 단순 (예: 미터) (예: 미터/초)입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="14190-332">모든 열은 부동 소수점 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-332">All columns contain floating point data.</span></span>

<span data-ttu-id="14190-333">더 완전 한 공급자는 이러한 제한을 완화 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="14190-334">첫 번째 단계는 API가 어떻게 보이는지를 고려 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="14190-335">이전 테이블의 콘텐츠(쉼표로 분리된 형식)를 사용하여 `info.csv` 파일을 지정한 경우 공급자의 사용자는 다음 예제와 비슷한 코드를 작성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="14190-336">이 경우 컴파일러는 이러한 호출을 다음 예제와 같은 항목으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="14190-337">최적의 변환에서는 형식 공급자가 형식 `CsvFile` 공급자의 어셈블리에서 실제 형식을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="14190-338">형식 공급자는 종종 몇 가지 도우미 형식 및 메서드를 사용 하 여 중요 한 논리를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="14190-339">측정값은 런타임에 지워집니다 `float[]` .를 행의 지워진 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="14190-340">컴파일러는 서로 다른 측정값 형식이 있는 것으로 다른 열을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="14190-341">예를 들어이 예제의 첫 번째 열에는 형식이 `float<meter>` 있고, 두 번째 열에는가 `float<second>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="14190-342">그러나 지워진 표현은 매우 간단 하 게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="14190-343">다음 코드는 구현의 핵심을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14190-343">The following code shows the core of the implementation.</span></span>

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

<span data-ttu-id="14190-344">구현에 대 한 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="14190-345">오버 로드 된 생성자는 원본 파일 또는 동일한 스키마를 가진 파일을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="14190-346">이 패턴은 로컬 또는 원격 데이터 원본에 대 한 형식 공급자를 작성할 때 일반적으로 사용 되며,이 패턴을 사용 하면 로컬 파일을 원격 데이터의 템플릿으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="14190-347">형식 공급자 생성자에 전달 된 [Typeproviderconfig](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderconfig.html) 값을 사용 하 여 상대 파일 이름을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-347">You can use the [TypeProviderConfig](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderconfig.html) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="14190-348">메서드를 사용 하 여 `AddDefinitionLocation` 제공 된 속성의 위치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="14190-349">따라서 제공 된 속성에서를 사용 하는 경우 `Go To Definition` CSV 파일은 Visual Studio에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="14190-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="14190-350">형식을 사용 하 여 `ProvidedMeasureBuilder` SI 단위를 조회 하 고 관련 형식을 생성할 수 있습니다 `float<_>` .</span><span class="sxs-lookup"><span data-stu-id="14190-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="14190-351">주요 단원</span><span class="sxs-lookup"><span data-stu-id="14190-351">Key Lessons</span></span>

<span data-ttu-id="14190-352">이 섹션에서는 데이터 원본 자체에 포함 된 간단한 스키마를 사용 하 여 로컬 데이터 원본에 대 한 형식 공급자를 만드는 방법에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="14190-353">더 나아가기</span><span class="sxs-lookup"><span data-stu-id="14190-353">Going Further</span></span>

<span data-ttu-id="14190-354">다음 섹션에는 추가 연구에 대 한 제안이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-354">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="14190-355">컴파일된 형식에 대 한 컴파일된 코드 살펴보기</span><span class="sxs-lookup"><span data-stu-id="14190-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="14190-356">형식 공급자를 사용 하는 방법에 대 한 자세한 내용은 `HelloWorldTypeProvider` 이 항목의 앞부분에서 사용 된를 사용 하 여 다음 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="14190-357">ildasm.exe를 사용 하 여 결과 코드 디컴파일된 이미지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

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

<span data-ttu-id="14190-358">예제에 나와 있는 것 처럼 형식 및 속성의 모든 멘 션이 `Type1` `InstanceProperty` 삭제 되어 관련 된 런타임 형식에 대 한 작업만 남게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="14190-359">형식 공급자의 디자인 및 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="14190-359">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="14190-360">형식 공급자를 제작할 때 다음 규칙을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="14190-361">**연결 프로토콜에 대 한 공급자** 일반적으로 데이터 및 서비스 연결 프로토콜에 대 한 대부분의 공급자 Dll 이름 (예: OData 또는 SQL 연결)은 또는로 끝나야 합니다 `TypeProvider` `TypeProviders` .</span><span class="sxs-lookup"><span data-stu-id="14190-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="14190-362">예를 들어 다음 문자열과 유사한 DLL 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-362">For example, use a DLL name that resembles the following string:</span></span>

`Fabrikam.Management.BasicTypeProviders.dll`

<span data-ttu-id="14190-363">제공 된 형식이 해당 네임 스페이스의 멤버 인지 확인 하 고 구현 된 연결 프로토콜을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="14190-364">**일반적인 코딩을 위한 유틸리티 공급자**입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="14190-365">정규식의 경우와 같은 유틸리티 유형 공급자의 경우 다음 예제와 같이 형식 공급자가 기본 라이브러리의 일부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="14190-366">이 경우 제공 된 형식이 일반적인 .NET 디자인 규칙에 따라 적절 한 지점에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="14190-367">**Singleton 데이터 원본**입니다.</span><span class="sxs-lookup"><span data-stu-id="14190-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="14190-368">일부 형식 공급자는 단일 전용 데이터 원본에 연결 하 고 데이터만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="14190-369">이 경우 접미사를 삭제 `TypeProvider` 하 고 .net 명명에 대 한 일반 규칙을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="14190-370">자세한 내용은 `GetConnection` 이 항목의 뒷부분에서 설명 하는 디자인 규칙을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="14190-371">형식 공급자의 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="14190-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="14190-372">다음 섹션에서는 형식 공급자를 제작할 때 사용할 수 있는 디자인 패턴에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-372">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="14190-373">GetConnection 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="14190-373">The GetConnection Design Pattern</span></span>

<span data-ttu-id="14190-374">`GetConnection`다음 예제와 같이 FSharp.Data.TypeProviders.dll의 형식 공급자가 사용 하는 패턴을 사용 하도록 대부분의 형식 공급자를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="14190-375">원격 데이터 및 서비스에서 지원 되는 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="14190-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="14190-376">원격 데이터와 서비스에서 지원 되는 형식 공급자를 만들기 전에 연결 된 프로그래밍에 내재 된 다양 한 문제를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="14190-377">이러한 문제에는 다음 사항이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="14190-378">스키마 매핑</span><span class="sxs-lookup"><span data-stu-id="14190-378">schema mapping</span></span>

- <span data-ttu-id="14190-379">스키마가 변경 된 상태에서 선거의 및 무효화</span><span class="sxs-lookup"><span data-stu-id="14190-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="14190-380">스키마 캐싱</span><span class="sxs-lookup"><span data-stu-id="14190-380">schema caching</span></span>

- <span data-ttu-id="14190-381">데이터 액세스 작업의 비동기 구현</span><span class="sxs-lookup"><span data-stu-id="14190-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="14190-382">LINQ 쿼리를 비롯 한 지원 쿼리</span><span class="sxs-lookup"><span data-stu-id="14190-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="14190-383">자격 증명 및 인증</span><span class="sxs-lookup"><span data-stu-id="14190-383">credentials and authentication</span></span>

<span data-ttu-id="14190-384">이 항목에서는 이러한 문제를 더 자세히 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="14190-385">추가 제작 기술</span><span class="sxs-lookup"><span data-stu-id="14190-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="14190-386">사용자 고유의 형식 공급자를 작성 하는 경우 다음과 같은 추가 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="14190-387">요청 시 형식 및 멤버 만들기</span><span class="sxs-lookup"><span data-stu-id="14190-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="14190-388">프로 비전 된 유형 API는 지연 된 버전의 AddMember를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="14190-389">이러한 버전은 형식의 주문형 공간을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="14190-390">배열 형식 및 제네릭 형식 인스턴스화 제공</span><span class="sxs-lookup"><span data-stu-id="14190-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="14190-391">을 포함 하 여 `MakeArrayType` `MakePointerType` `MakeGenericType` 의 모든 인스턴스에서 일반, 및를 <xref:System.Type> 사용 하 여 제공 된 멤버 (시그니처에 배열 형식, byref 형식 및 제네릭 형식의 인스턴스화 포함)를 만듭니다 `ProvidedTypeDefinitions` .</span><span class="sxs-lookup"><span data-stu-id="14190-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="14190-392">에서 도우미를 사용 해야 하는 경우도 있습니다 `ProvidedTypeBuilder.MakeGenericType` .</span><span class="sxs-lookup"><span data-stu-id="14190-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="14190-393">자세한 내용은 [형식 공급자 SDK 설명서](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14190-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="14190-394">측정 단위 주석 제공</span><span class="sxs-lookup"><span data-stu-id="14190-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="14190-395">프로 비전 된 형식 API는 측정값 주석을 제공 하는 도우미를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="14190-396">예를 들어 형식을 제공 하려면 `float<kg>` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="14190-397">형식을 제공 하려면 `Nullable<decimal<kg/m^2>>` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="14190-398">프로젝트 로컬 또는 스크립트 로컬 리소스 액세스</span><span class="sxs-lookup"><span data-stu-id="14190-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="14190-399">형식 공급자의 각 인스턴스에는 생성 중에 값을 지정할 수 있습니다 `TypeProviderConfig` .</span><span class="sxs-lookup"><span data-stu-id="14190-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="14190-400">이 값에는 공급자에 대 한 "해결 폴더" (즉, 컴파일에 대 한 프로젝트 폴더 또는 스크립트가 포함 된 디렉터리), 참조 된 어셈블리 목록 및 기타 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="14190-401">무효화</span><span class="sxs-lookup"><span data-stu-id="14190-401">Invalidation</span></span>

<span data-ttu-id="14190-402">공급자는 무효화 신호를 발생 시켜 스키마 가정이 변경 되었을 수 있음을 F # 언어 서비스에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="14190-403">무효화가 발생 하면 Visual Studio에서 공급자가 호스트 되는 경우 typecheck가 다시 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="14190-404">공급자가 F# 대화형 또는 F # 컴파일러 (fsc.exe)에서 호스트 되는 경우이 신호는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="14190-405">스키마 정보 캐싱</span><span class="sxs-lookup"><span data-stu-id="14190-405">Caching Schema Information</span></span>

<span data-ttu-id="14190-406">공급자는 종종 스키마 정보에 대 한 액세스를 캐시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="14190-407">정적 매개 변수 또는 사용자 데이터로 지정 된 파일 이름을 사용 하 여 캐시 된 데이터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="14190-408">스키마 캐싱의 예는 `LocalSchemaFile` 어셈블리의 형식 공급자에 있는 매개 변수입니다 `FSharp.Data.TypeProviders` .</span><span class="sxs-lookup"><span data-stu-id="14190-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="14190-409">이러한 공급자의 구현에서이 정적 매개 변수는 네트워크를 통해 데이터 원본에 액세스 하는 대신 지정 된 로컬 파일의 스키마 정보를 사용 하도록 형식 공급자에 게 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="14190-410">캐시 된 스키마 정보를 사용 하려면 정적 매개 변수도로 설정 해야 `ForceUpdate` 합니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="14190-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="14190-411">유사한 기술을 사용 하 여 온라인 및 오프 라인 데이터 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="14190-412">어셈블리 지원</span><span class="sxs-lookup"><span data-stu-id="14190-412">Backing Assembly</span></span>

<span data-ttu-id="14190-413">또는 파일을 컴파일할 `.dll` 때 `.exe` 생성 된 형식에 대 한 지원 .dll 파일은 결과 어셈블리에 정적으로 링크 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="14190-414">이 링크는 IL (중간 언어) 형식 정의와 지원 어셈블리에서 관리 되는 모든 리소스를 최종 어셈블리에 복사 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14190-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="14190-415">F# 대화형 사용 하는 경우에는 지원 .dll 파일이 복사 되지 않고 대신 F# 대화형 프로세스로 직접 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="14190-416">형식 공급자의 예외 및 진단</span><span class="sxs-lookup"><span data-stu-id="14190-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="14190-417">제공 된 형식의 모든 멤버를 사용 하면 예외가 throw 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="14190-418">모든 경우에서 형식 공급자가 예외를 throw 하는 경우 호스트 컴파일러는 오류를 특정 형식 공급자에 게 특성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="14190-419">형식 공급자 예외는 내부 컴파일러 오류가 발생 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="14190-420">형식 공급자는 경고를 보고할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="14190-421">형식 공급자가 F # 컴파일러, F # 개발 환경 또는 F# 대화형에서 호스트 되는 경우 해당 공급자의 모든 예외가 catch 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="14190-422">메시지 속성은 항상 오류 텍스트 이며 스택 추적이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="14190-423">예외를 throw 할 경우 `System.NotSupportedException` , `System.IO.IOException` , `System.Exception` 와 같은 예를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="14190-424">생성 된 형식 제공</span><span class="sxs-lookup"><span data-stu-id="14190-424">Providing Generated Types</span></span>

<span data-ttu-id="14190-425">지금까지이 문서에서는 지워진 형식을 제공 하는 방법에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="14190-426">F #에서 형식 공급자 메커니즘을 사용 하 여 생성 된 형식을 제공할 수도 있습니다 .이 형식은 사용자의 프로그램에 실제 .NET 형식 정의로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="14190-427">형식 정의를 사용 하 여 생성 된 제공 형식을 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="14190-428">F # 3.0 릴리스에 포함 된 프로 비전 된 유형-0.2 도우미 코드는 생성 된 유형 제공을 제한적 으로만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="14190-429">다음 문은 생성 된 형식 정의에 대해 true 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="14190-430">`isErased`은 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="14190-431">생성 된 형식은 `ProvidedAssembly()` 생성 된 코드 조각에 대 한 컨테이너를 나타내는 새로 생성 된에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="14190-432">공급자에는 디스크에 일치 하는 .dll 파일과 함께 실제 지원 .NET .dll 파일이 있는 어셈블리가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="14190-433">규칙 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="14190-433">Rules and Limitations</span></span>

<span data-ttu-id="14190-434">형식 공급자를 작성 하는 경우에는 다음 규칙 및 제한 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-434">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="14190-435">제공 된 형식에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-435">Provided types must be reachable</span></span>

<span data-ttu-id="14190-436">제공 된 모든 형식은 중첩 되지 않은 형식에서 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="14190-437">중첩 되지 않은 형식은 생성자에 대 한 호출 `TypeProviderForNamespaces` 또는에 대 한 호출에서 제공 됩니다 `AddNamespace` .</span><span class="sxs-lookup"><span data-stu-id="14190-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="14190-438">예를 들어 공급자가 형식을 제공 하는 경우 `StaticClass.P : T` T가 중첩 되지 않은 형식 이거나 중첩 된 형식 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="14190-439">예를 들어, 일부 공급자는 `DataTypes` 이러한 형식을 포함 하는와 같은 정적 클래스를 포함 `T1, T2, T3, ...` 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="14190-440">그렇지 않으면 어셈블리 A의 T 형식에 대 한 참조를 찾았지만 해당 어셈블리에서 형식을 찾을 수 없다는 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14190-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="14190-441">이 오류가 표시 되 면 공급자 형식에서 모든 하위 형식에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="14190-442">참고: 이러한 `T1, T2, T3...` 형식은 *즉석* 형식 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="14190-443">이러한 항목은 액세스 가능한 네임 스페이스 또는 부모 형식에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="14190-444">유형 공급자 메커니즘의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="14190-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="14190-445">F #의 형식 공급자 메커니즘에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="14190-446">F #에서 형식 공급자의 기본 인프라는 제공 된 제네릭 형식 또는 제공 된 제네릭 메서드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="14190-447">메커니즘은 정적 매개 변수를 포함 하는 중첩 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="14190-448">개발 팁</span><span class="sxs-lookup"><span data-stu-id="14190-448">Development Tips</span></span>

<span data-ttu-id="14190-449">개발 프로세스 중에 다음 팁을 유용 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-449">You might find the following tips helpful during the development process:</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="14190-450">Visual Studio의 두 인스턴스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-450">Run two instances of Visual Studio</span></span>

<span data-ttu-id="14190-451">테스트 IDE는 형식 공급자가 다시 작성 되지 않도록 방지 하는 .dll 파일에 대 한 잠금을 사용 하기 때문에 한 인스턴스에서 형식 공급자를 개발 하 고 다른 공급자에서 공급자를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="14190-452">따라서 공급자가 첫 번째 인스턴스에서 빌드되는 동안 Visual Studio의 두 번째 인스턴스를 닫은 다음 공급자가 작성 된 후에 두 번째 인스턴스를 다시 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14190-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="14190-453">fsc.exe 호출을 사용 하 여 형식 공급자 디버그</span><span class="sxs-lookup"><span data-stu-id="14190-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="14190-454">다음 도구를 사용 하 여 형식 공급자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="14190-455">fsc.exe (F # 명령줄 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="14190-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="14190-456">fsi.exe (F# 대화형 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="14190-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="14190-457">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="14190-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="14190-458">테스트 스크립트 파일 (예: .fsx)에서 fsc.exe를 사용 하면 형식 공급자를 가장 쉽게 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="14190-459">명령 프롬프트에서 디버거를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-459">You can launch a debugger from a command prompt.</span></span>

```console
devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="14190-460">인쇄 stdout 로깅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14190-460">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="14190-461">추가 정보</span><span class="sxs-lookup"><span data-stu-id="14190-461">See also</span></span>

- [<span data-ttu-id="14190-462">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="14190-462">Type Providers</span></span>](index.md)
- [<span data-ttu-id="14190-463">형식 공급자 SDK</span><span class="sxs-lookup"><span data-stu-id="14190-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
