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
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="acf90-103">자습서: 형식 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="acf90-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="acf90-104">F#의 형식 공급자 메커니즘은 풍부한 정보 프로그래밍에 대한 지원의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="acf90-105">이 자습서에서는 기본 개념을 설명하기 위해 몇 가지 간단한 형식 공급자의 개발을 안내하여 고유한 형식 공급자를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="acf90-106">F#의 형식 공급자 메커니즘에 대한 자세한 내용은 [형식 공급자](index.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="acf90-107">F# 생태계에는 일반적으로 사용되는 인터넷 및 엔터프라이즈 데이터 서비스에 대한 다양한 형식 공급자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="acf90-108">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-108">For example:</span></span>

- <span data-ttu-id="acf90-109">[FSharp.Data에는](https://fsharp.github.io/FSharp.Data/) JSON, XML, CSV 및 HTML 문서 형식에 대한 형식 공급자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="acf90-110">[SQLProvider는](https://fsprojects.github.io/SQLProvider/) 개체 매핑 및 이러한 데이터 원본에 대한 F# LINQ 쿼리를 통해 SQL 데이터베이스에 대한 강력한 형식의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="acf90-111">[FSharp.Data.SqlClient는](https://fsprojects.github.io/FSharp.Data.SqlClient/) F#에 T-SQL의 컴파일 타임 확인 포함을 위한 형식 공급자 집합을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="acf90-112">[FSharp.Data.TypeProviders는](https://fsprojects.github.io/FSharp.Data.TypeProviders/) SQL, 엔터티 프레임워크, OData 및 WSDL 데이터 서비스에 액세스하기 위한 .NET 프레임워크 프로그래밍에서만 사용할 수 있는 이전 형식 공급자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="acf90-113">필요한 경우 사용자 지정 형식 공급자를 만들거나 다른 사용자가 만든 형식 공급자를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="acf90-114">예를 들어 조직에는 각각 고유한 안정적인 데이터 스키마가 있는 명명된 데이터 집합의 수가 늘어나는 데이터 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="acf90-115">스키마를 읽고 현재 데이터 집합을 강력하게 입력한 방식으로 프로그래머에게 제공하는 형식 공급자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="acf90-116">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="acf90-116">Before You Start</span></span>

<span data-ttu-id="acf90-117">형식 공급자 메커니즘은 주로 안정적인 데이터 및 서비스 정보 공간을 F# 프로그래밍 환경으로 주입하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="acf90-118">이 메커니즘은 프로그램 논리와 관련된 방식으로 프로그램 실행 중에 스키마가 변경되는 정보 공간을 삽입하기 위해 설계되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="acf90-119">또한 해당 도메인에 유효한 용도가 포함되어 있더라도 언어 내 메타 프로그래밍을 위해 메커니즘이 설계되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="acf90-120">필요한 경우에만 이 메커니즘을 사용해야 하며 형식 공급자의 개발로 매우 높은 가치를 산출하는 경우에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="acf90-121">스키마를 사용할 수 없는 형식 공급자를 작성하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="acf90-122">마찬가지로 일반(또는 기존)의 .NET 라이브러리로 충분할 수 있는 형식 공급자를 작성하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="acf90-123">시작하기 전에 다음 질문을 할 수 있다.</span><span class="sxs-lookup"><span data-stu-id="acf90-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="acf90-124">정보 소스에 대한 스키마가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="acf90-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="acf90-125">그렇다면 F# 및 .NET 형식 시스템에 매핑하는 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="acf90-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="acf90-126">기존(동적으로 입력된) API를 구현의 시작점으로 사용할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="acf90-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="acf90-127">사용자와 조직에서 형식 공급자를 충분히 사용하여 작성을 가치 있게 만들 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="acf90-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="acf90-128">일반 .NET 라이브러리가 사용자의 요구를 충족합니까?</span><span class="sxs-lookup"><span data-stu-id="acf90-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="acf90-129">스키마는 얼마만큼 변경될 것인가?</span><span class="sxs-lookup"><span data-stu-id="acf90-129">How much will your schema change?</span></span>

- <span data-ttu-id="acf90-130">코딩 중에 변경될 까요?</span><span class="sxs-lookup"><span data-stu-id="acf90-130">Will it change during coding?</span></span>

- <span data-ttu-id="acf90-131">코딩 세션 간에 변경될 까요?</span><span class="sxs-lookup"><span data-stu-id="acf90-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="acf90-132">프로그램 실행 중에 변경합니까?</span><span class="sxs-lookup"><span data-stu-id="acf90-132">Will it change during program execution?</span></span>

<span data-ttu-id="acf90-133">형식 공급자는 스키마가 런타임 및 컴파일된 코드의 수명 동안 안정적인 상황에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="acf90-134">간단한 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="acf90-134">A Simple Type Provider</span></span>

<span data-ttu-id="acf90-135">이 샘플은 샘플입니다.HelloWorldTypeProvider는 `examples` [F# 형식 공급자 SDK의](https://github.com/fsprojects/FSharp.TypeProviders.SDK/)디렉터리에 있는 샘플과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="acf90-136">공급자는 F# 서명 구문을 사용하고 을 제외한 `Type1`모든 세부 정보를 생략하여 다음 코드에서 보여 주는 것처럼 100개의 지워진 형식을 포함하는 "형식 공간"을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="acf90-137">지워진 형식에 대한 자세한 내용은 이 항목의 후반부에서 [지워진 제공된 형식에 대한 세부 정보를 참조하세요.](#details-about-erased-provided-types)</span><span class="sxs-lookup"><span data-stu-id="acf90-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

<span data-ttu-id="acf90-138">제공된 형식 및 멤버 집합은 정적으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="acf90-139">이 예제는 스키마에 종속된 형식을 제공하는 공급자의 기능을 활용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="acf90-140">형식 공급자의 구현은 다음 코드에 설명되어 있으며 자세한 내용은 이 항목의 이후 섹션에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

> [!WARNING]
> <span data-ttu-id="acf90-141">이 코드와 온라인 샘플 간에 차이가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-141">There may be differences between this code and the online samples.</span></span>

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

<span data-ttu-id="acf90-142">이 공급자를 사용 하려면 Visual Studio의 별도 인스턴스를 열고 F# 스크립트를 만든 다음 다음 코드와 같이 #r 사용 하 여 스크립트에서 공급자에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="acf90-143">그런 다음 형식 공급자가 생성한 `Samples.HelloWorldTypeProvider` 네임스페이스 아래에 있는 형식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="acf90-144">공급자를 다시 컴파일하기 전에 공급자 DLL을 사용하는 Visual Studio 및 F# 대화형의 모든 인스턴스를 닫았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="acf90-145">그렇지 않으면 출력 DLL이 잠겨 있기 때문에 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="acf90-146">print 문을 사용하여 이 공급자를 디버깅하려면 공급자에 문제를 노출하는 스크립트를 만들고 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="acf90-147">Visual Studio를 사용하여 이 공급자를 디버깅하려면 관리 자격 증명을 사용하여 Visual Studio용 개발자 명령 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-147">To debug this provider by using Visual Studio, open the Developer Command Prompt for Visual Studio with administrative credentials, and run the following command:</span></span>

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="acf90-148">또는 Visual Studio를 열고 디버그 메뉴를 열고 `Debug/Attach to process…`을 선택하고 `devenv` 스크립트를 편집하는 다른 프로세스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="acf90-149">이 메서드를 사용 하 여 두 번째 인스턴스에 대화식으로 입력 (전체 IntelliSense 및 기타 기능)를 사용 하 여 형식 공급자에서 특정 논리를 보다 쉽게 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="acf90-150">내 코드 디버깅을 사용하지 않도록 설정하여 생성된 코드의 오류를 더 잘 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="acf90-151">이 기능을 사용하거나 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [디버거를 사용하여 코드 탐색을](/visualstudio/debugger/navigating-through-code-with-the-debugger)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="acf90-152">또한 `Debug` 메뉴를 연 다음 Ctrl+Alt+E 키를 `Exceptions` 선택하거나 선택하여 대화 상자를 열어 첫 `Exceptions` 번째 예외 catch를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="acf90-153">해당 대화 상자에서 `Common Language Runtime Exceptions`에서 확인란을 선택합니다. `Thrown`</span><span class="sxs-lookup"><span data-stu-id="acf90-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="acf90-154">형식 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="acf90-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="acf90-155">이 섹션에서는 형식 공급자 구현의 주요 섹션을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="acf90-156">먼저 사용자 지정 형식 공급자 자체에 대 한 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="acf90-157">이 형식은 공용이어야 하며 별도의 F# 프로젝트가 형식을 포함하는 어셈블리를 참조할 때 컴파일러가 형식 공급자를 인식할 수 있도록 [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) 특성으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-157">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="acf90-158">*구성* 매개 변수는 선택 사항이며, 있는 경우 F# 컴파일러가 만드는 형식 공급자 인스턴스에 대한 컨텍스트 구성 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="acf90-159">다음으로 [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-159">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="acf90-160">이 경우 API의 `TypeProviderForNamespaces` `ProvidedTypes` 형식을 기본 유형으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="acf90-161">이 도우미 유형은 간절히 제공한 이름 영역의 유한 한 컬렉션을 제공할 수 있으며, 각 키드에는 유한한 수의 고정된 형식이 직접 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="acf90-162">이 컨텍스트에서 공급자는 필요 하거나 사용 하지 않는 경우에 *형식을 열심히* 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="acf90-163">그런 다음 제공된 형식의 네임스페이스를 지정하는 로컬 개인 값을 정의하고 형식 공급자 어셈블리 자체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="acf90-164">이 어셈블리는 나중에 제공된 지워진 형식의 논리적 부모 유형으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="acf90-165">다음으로, 각 Type1을 제공하는 함수를 만듭니다... Type100.</span><span class="sxs-lookup"><span data-stu-id="acf90-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="acf90-166">이 함수는 이 항목의 후반부에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="acf90-167">다음으로 제공된 100개의 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="acf90-168">다음으로 형식을 제공된 네임스페이스로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="acf90-169">마지막으로 형식 공급자 DLL을 만들고 있음을 나타내는 어셈블리 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="acf90-170">한 가지 유형과 그 구성원 제공</span><span class="sxs-lookup"><span data-stu-id="acf90-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="acf90-171">함수는 `makeOneProvidedType` 형식 중 하나를 제공하는 실제 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) =
…
```

<span data-ttu-id="acf90-172">이 단계에서는 이 함수의 구현에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="acf90-173">먼저 제공된 형식(예: Type1, n = 1, Type57, n = 57)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="acf90-174">다음 사항을 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-174">You should note the following points:</span></span>

- <span data-ttu-id="acf90-175">제공된 형식이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-175">This provided type is erased.</span></span>  <span data-ttu-id="acf90-176">기본 형식이 `obj`있음을 나타내기 때문에 인스턴스는 컴파일된 코드에서 [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 형식의 값으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="acf90-177">중첩되지 않은 형식을 지정할 때 어셈블리 및 네임스페이스를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="acf90-178">지워진 형식의 경우 어셈블리는 형식 공급자 어셈블리 자체여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="acf90-179">다음으로 형식에 XML 설명서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="acf90-180">이 문서는 호스트 컴파일러가 필요한 경우 주문형으로 계산되는 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="acf90-181">다음으로 형식에 제공된 정적 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="acf90-182">이 속성을 가져오는 것은 항상 문자열 "Hello!"로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="acf90-183">for `GetterCode` 속성은 호스트 컴파일러가 속성을 얻기 위해 생성하는 코드를 나타내는 F# 따옴표를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="acf90-184">견적에 대한 자세한 내용은 [코드 견적(F#)을](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-184">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="acf90-185">속성에 XML 설명서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="acf90-186">이제 제공된 속성을 제공된 형식에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="acf90-187">제공된 멤버를 하나의 형식에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="acf90-188">그렇지 않으면 멤버에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="acf90-189">이제 매개 변수를 수행하지 않는 제공된 생성자만들기가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="acf90-190">for `InvokeCode` 생성자는 생성자가 호출될 때 호스트 컴파일러가 생성하는 코드를 나타내는 F# 따옴표를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="acf90-191">예를 들어 다음 생성자다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="acf90-192">제공된 형식의 인스턴스는 기본 데이터 "개체 데이터"로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="acf90-193">인용된 코드에는 해당 형식이 제공된 형식을 선언할 때 지정한 대로 이 제공된 형식의 지우기이므로 [obj로의](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) 변환이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-193">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="acf90-194">생성자에 XML 설명서를 추가하고 제공된 생성기를 제공된 형식에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="acf90-195">하나의 매개 변수를 취하는 두 번째 제공된 생성자 만들기:</span><span class="sxs-lookup"><span data-stu-id="acf90-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="acf90-196">for `InvokeCode` 생성자는 메서드 호출에 대해 호스트 컴파일러가 생성한 코드를 나타내는 F# 따옴표를 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="acf90-197">예를 들어 다음 생성자다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="acf90-198">제공된 형식의 인스턴스는 기본 데이터 "10"으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="acf90-199">함수가 견적을 `InvokeCode` 반환한다는 것을 이미 알아차렸을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="acf90-200">이 함수에 대한 입력은 생성자 매개 변수당 하나씩 식 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="acf90-201">이 경우 단일 매개 변수 값을 나타내는 식을 `args.[0]`에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="acf90-202">생성자 호출코드는 지워진 형식에 `obj`반환 값을 강제 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="acf90-203">형식에 두 번째 제공 된 생성기를 추가 한 후 제공 된 인스턴스 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="acf90-204">이 속성을 가져오는 것은 표현 객체인 문자열의 길이를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="acf90-205">속성은 `GetterCode` 호스트 컴파일러가 속성을 가져오는 데 생성하는 코드를 지정하는 F# 견적을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="acf90-206">마찬가지로 `InvokeCode`함수는 `GetterCode` 견적을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="acf90-207">호스트 컴파일러는 인수 목록으로 이 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="acf90-208">이 경우 인수에는 getter가 호출되는 인스턴스를 나타내는 단일 표현식만 포함되며, 이 `args.[0]`식을 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.</span></span> <span data-ttu-id="acf90-209">`GetterCode` 그런 다음 지워진 형식에서 `obj`결과 따옴표로 스플라이스를 구현하고 캐스트는 개체가 문자열인 형식을 검사하기 위한 컴파일러 메커니즘을 충족하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-209">The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="acf90-210">다음 `makeOneProvidedType` 부분에서는 하나의 매개 변수를 사용하여 인스턴스 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

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

<span data-ttu-id="acf90-211">마지막으로 100개의 중첩 된 속성을 포함 하는 중첩 된 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="acf90-212">이 중첩 된 형식및 해당 속성의 생성은 요청시 계산되는 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

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

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="acf90-213">지워진 제공된 유형에 대한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="acf90-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="acf90-214">이 섹션의 예제에서는 *지워진 제공된 형식만*제공하므로 다음 상황에서 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="acf90-215">데이터와 메서드만 포함하는 정보 공간에 대한 공급자를 작성할 때</span><span class="sxs-lookup"><span data-stu-id="acf90-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="acf90-216">정확한 런타임 유형 의미체계가 정보 공간을 실용화하는 데 중요하지 않은 공급자를 작성하는 경우</span><span class="sxs-lookup"><span data-stu-id="acf90-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="acf90-217">너무 크고 상호 연결된 정보 공간에 대한 공급자를 작성하는 경우 정보 공간에 대한 실제 .NET 형식을 기술적으로 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="acf90-218">이 예제에서는 제공된 각 형식이 `obj`형식에 지워지고 형식의 모든 `obj` 용도가 컴파일된 코드의 유형으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="acf90-219">실제로 이러한 예제의 기본 개체는 문자열이지만 형식은 .NET `System.Object` 컴파일된 코드와 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="acf90-220">형식 지우기의 모든 사용과 마찬가지로 명시적 boxing, 언박싱 및 캐스팅을 사용하여 삭제된 형식을 전복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="acf90-221">이 경우 개체를 사용할 때 유효하지 않은 캐스트 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="acf90-222">공급자 런타임은 잘못된 표현으로부터 보호하기 위해 자체 개인 표현 유형을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="acf90-223">F# 자체에서는 지워진 형식을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="acf90-224">제공된 형식만 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-224">Only provided types may be erased.</span></span> <span data-ttu-id="acf90-225">형식 공급자 또는 지워진 형식을 제공하는 공급자에 대해 지워진 형식을 사용하는 것이 실용적이고 의미 체계적인 결과를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="acf90-226">지워진 형식에는 실제 .NET 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="acf90-227">따라서 형식에 대한 정확한 리플렉션을 수행할 수 없으며 런타임 캐스트 및 정확한 런타임 형식 의미체계를 사용하는 기타 기술을 사용하는 경우 삭제된 형식을 전복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="acf90-228">지워진 형식의 전복은 런타임에 형식 캐스트 예외를 초래하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="acf90-229">지워진 제공된 형식에 대한 표현 선택</span><span class="sxs-lookup"><span data-stu-id="acf90-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="acf90-230">지워진 제공된 형식의 일부 사용의 경우 표현이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="acf90-231">예를 들어 지워진 제공된 형식에는 정적 속성과 멤버만 포함될 수 있으며 생성자는 없으며 메서드나 속성은 형식의 인스턴스를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="acf90-232">지워진 제공된 유형의 인스턴스에 도달할 수 있는 경우 다음 질문을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="acf90-233">**제공된 형식의 삭제는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="acf90-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="acf90-234">제공된 형식의 삭제는 컴파일된 .NET 코드에 형식이 표시되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="acf90-235">제공된 지워진 클래스 형식의 지우기는 항상 형식의 상속 체인에서 지워지지 않은 첫 번째 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="acf90-236">제공된 지워진 인터페이스 형식의 지우기는 항상 `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="acf90-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="acf90-237">**제공된 형식의 표현은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="acf90-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="acf90-238">지워진 제공된 형식에 대해 가능한 개체 집합을 해당 표현이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="acf90-239">이 문서의 예제에서 지워진 제공된 모든 형식의 `Type1..Type100` 표현은 항상 문자열 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="acf90-240">제공된 형식의 모든 표현은 제공된 형식의 지우기와 호환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="acf90-241">그렇지 않으면 F# 컴파일러가 형식 공급자사용에 대한 오류를 제공하거나 유효하지 않은 확인할 수 없는 .NET 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="acf90-242">형식 공급자는 유효하지 않은 표현을 제공하는 코드를 반환하는 경우 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="acf90-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="acf90-243">제공된 개체에 대한 표현을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="acf90-244">기존 .NET 형식에 대해 강력한 형식의 래퍼를 제공하는 경우 형식이 해당 형식으로 지워지거나 해당 형식의 인스턴스를 표현으로 사용하거나 둘 다로 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="acf90-245">이 방법은 강력한 형식의 버전을 사용할 때 해당 형식의 대부분의 기존 메서드가 여전히 의미가 있는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="acf90-246">기존 .NET API와 크게 다른 API를 만들려면 제공된 형식에 대한 형식 지우기 및 표현이 되는 런타임 형식을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="acf90-247">이 문서의 예제에서는 제공된 개체의 표현으로 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="acf90-248">표현에 다른 개체를 사용하는 것이 적절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="acf90-249">예를 들어 사전을 속성 백으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="acf90-250">또는 하나 이상의 런타임 작업과 함께 표현을 형성하는 데 런타임에 사용되는 형식 공급자의 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="acf90-251">제공된 멤버는 다음 개체 형식의 인스턴스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="acf90-252">이 경우 (선택적으로) 이 형식을 다음을 생성할 `baseType` `ProvidedTypeDefinition`때로 지정하여 이 형식을 형식 지우기로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="acf90-253">주요 교훈</span><span class="sxs-lookup"><span data-stu-id="acf90-253">Key Lessons</span></span>

<span data-ttu-id="acf90-254">이전 섹션에서는 다양한 형식, 속성 및 메서드를 제공하는 간단한 지워지는 형식 공급자를 만드는 방법을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="acf90-255">이 섹션에서는 형식 공급자에서 지워진 형식을 제공하는 몇 가지 장점과 단점을 포함하여 형식 지우기의 개념을 설명하고 지워진 형식의 표현에 대해설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="acf90-256">정적 매개 변수를 사용하는 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="acf90-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="acf90-257">정적 데이터로 형식 공급자를 매개 변수화하는 기능을 사용하면 공급자가 로컬 또는 원격 데이터에 액세스할 필요가 없는 경우에도 많은 흥미로운 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="acf90-258">이 섹션에서는 이러한 공급자를 함께 배치하는 몇 가지 기본 기술을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="acf90-259">확인된 정규표현기 공급자 유형</span><span class="sxs-lookup"><span data-stu-id="acf90-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="acf90-260">다음과 같은 컴파일 타임 보장을 제공하는 인터페이스에서 .NET <xref:System.Text.RegularExpressions.Regex> 라이브러리를 래핑하는 정규식에 대한 형식 공급자를 구현하려고 한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="acf90-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="acf90-261">정규식이 유효한지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="acf90-262">정규식의 모든 그룹 이름을 기반으로 하는 일치 항목에서 명명된 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="acf90-263">이 섹션에서는 형식 공급자를 사용하여 `RegexTyped` 정규식 패턴이 매개 변수화하여 이러한 이점을 제공하는 형식을 만드는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="acf90-264">컴파일러는 제공된 패턴이 유효하지 않은 경우 오류를 보고하고 형식 공급자는 일치 할 때 명명 된 속성을 사용하여 그룹에 액세스 할 수 있도록 패턴에서 그룹을 추출 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="acf90-265">형식 공급자를 디자인할 때는 노출된 API가 최종 사용자에게 어떻게 보이는지, 이 디자인이 .NET 코드로 변환되는 방식을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="acf90-266">다음 예제에서는 이러한 API를 사용하여 지역 코드의 구성 요소를 얻는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="acf90-267">다음 예제에서는 형식 공급자가 이러한 호출을 변환하는 방법을 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="acf90-268">다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="acf90-268">Note the following points:</span></span>

- <span data-ttu-id="acf90-269">표준 정규식 유형은 매개 `RegexTyped` 변수화된 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="acf90-270">`RegexTyped` 생성자는 정규표현기 생성기를 호출하여 패턴에 대한 정적 형식 인수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="acf90-271">`Match` 메서드의 결과는 표준 <xref:System.Text.RegularExpressions.Match> 유형으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="acf90-272">명명된 각 그룹은 제공된 속성을 생성하고 속성에 액세스하면 일치 의 `Groups` 컬렉션에 인덱서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="acf90-273">다음 코드는 이러한 공급자를 구현하는 논리의 핵심이며 이 예제에서는 제공된 형식에 대한 모든 멤버의 추가를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="acf90-274">추가된 각 멤버에 대한 자세한 내용은 이 항목의 후반부에서 해당 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="acf90-275">전체 코드의 경우 CodePlex 웹 사이트에서 [F# 3.0 샘플 팩에서](https://archive.codeplex.com/?p=fsharp3sample) 샘플을 다운로드하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://archive.codeplex.com/?p=fsharp3sample) on the CodePlex website.</span></span>

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

<span data-ttu-id="acf90-276">다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="acf90-276">Note the following points:</span></span>

- <span data-ttu-id="acf90-277">형식 공급자는 기본값이 제공되므로 `pattern`필수 인 및 `options`선택적 의 .) 라는 두 개의 정적 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="acf90-278">정적 인수가 제공된 후 정규식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="acf90-279">이 인스턴스는 정규기가 잘못된 경우 예외를 발생시키고 이 오류는 사용자에게 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="acf90-280">`DefineStaticParameters` 콜백 내에서 인수가 제공된 후 반환되는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="acf90-281">이 코드는 IntelliSense 환경이 간소화된 상태로 유지되도록 true로 설정합니다. `HideObjectMethods`</span><span class="sxs-lookup"><span data-stu-id="acf90-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="acf90-282">이 특성으로 `Equals` `GetHashCode`인해 `Finalize`에서 `GetType` 및 멤버가 제공된 개체에 대한 IntelliSense 목록에서 억제됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="acf90-283">메서드의 `obj` 기본 유형으로 사용 하지만 다음 예제에서 `Regex` 볼 수 있듯이 이 형식의 런타임 표현으로 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="acf90-284">`Regex` 생성자 호출은 정규식이 <xref:System.ArgumentException> 유효하지 않은 경우 를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="acf90-285">컴파일러는 이 예외를 catch하고 컴파일 타임또는 Visual Studio 편집기에서 사용자에게 오류 메시지를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="acf90-286">이 예외를 사용하면 응용 프로그램을 실행하지 않고도 정규식의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="acf90-287">위에 정의된 형식은 의미 있는 메서드 나 속성을 포함 하지 않기 때문에 아직 유용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="acf90-288">먼저 정적 `IsMatch` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-288">First, add a static `IsMatch` method:</span></span>

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

<span data-ttu-id="acf90-289">이전 코드는 문자열을 `IsMatch`입력으로 사용하여 을 반환하는 `bool`메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="acf90-290">유일한 까다로운 부분은 정의 내에서 `args` 인수를 `InvokeCode` 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="acf90-291">이 예제에서는 `args` 이 메서드에 대한 인수를 나타내는 견적 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="acf90-292">메서드가 인스턴스 메서드인 경우 첫 번째 `this` 인수는 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="acf90-293">그러나 정적 메서드의 경우 인수는 모두 메서드에 대한 명시적 인수일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="acf90-294">인용된 값의 형식은 지정된 반환 형식(이 `bool`경우)과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="acf90-295">또한 이 코드는 `AddXmlDoc` 메서드를 사용하여 제공된 메서드에도 IntelliSense를 통해 제공할 수 있는 유용한 설명서도 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="acf90-296">다음으로 인스턴스 일치 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-296">Next, add an instance Match method.</span></span> <span data-ttu-id="acf90-297">그러나 이 메서드는 그룹에 강력한 `Match` 형식의 방식으로 액세스할 수 있도록 제공 된 형식의 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="acf90-298">따라서 먼저 형식을 `Match` 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="acf90-299">이 형식은 정적 인수로 제공된 패턴에 따라 달라지므로 이 형식은 매개 변수화된 형식 정의 내에 중첩되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="acf90-300">그런 다음 각 그룹에 대해 일치 유형에 하나의 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="acf90-301">런타임에서 일치는 <xref:System.Text.RegularExpressions.Match> 값으로 표시되므로 속성을 정의하는 따옴표는 <xref:System.Text.RegularExpressions.Match.Groups> 인덱싱된 속성을 사용하여 관련 그룹을 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

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

<span data-ttu-id="acf90-302">다시 말하지만 제공된 속성에 XML 설명서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="acf90-303">또한 `GetterCode` 함수가 제공되는 경우 속성을 읽을 수 있으며 `SetterCode` 함수가 제공된 경우 속성을 작성할 수 있으므로 결과 속성만 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="acf90-304">이제 이 `Match` 유형의 값을 반환하는 인스턴스 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

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

<span data-ttu-id="acf90-305">인스턴스 메서드를 만들기 때문에 `args.[0]` 메서드가 `RegexTyped` 호출되는 인스턴스를 나타내며 `args.[1]` 입력 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="acf90-306">마지막으로 제공된 형식의 인스턴스를 만들 수 있도록 생성자 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="acf90-307">생성자는 제공된 형식의 지우기때문에 `obj` 개체에 다시 boxed되는 표준 .NET Regex 인스턴스를 만들기 위해 지웁니까 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="acf90-308">이 변경 사항으로 항목의 앞에 지정한 샘플 API 사용이 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="acf90-309">다음 코드는 완전하고 최종입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-309">The following code is complete and final:</span></span>

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

### <a name="key-lessons"></a><span data-ttu-id="acf90-310">주요 교훈</span><span class="sxs-lookup"><span data-stu-id="acf90-310">Key Lessons</span></span>

<span data-ttu-id="acf90-311">이 섹션에서는 정적 매개 변수에서 작동하는 형식 공급자를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="acf90-312">공급자는 정적 매개 변수를 검사하고 해당 값에 따라 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-312">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="acf90-313">로컬 데이터로 백업되는 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="acf90-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="acf90-314">정적 매개 변수뿐만 아니라 로컬 또는 원격 시스템의 정보도 기반으로 형식 공급자가 API를 표시하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="acf90-315">이 섹션에서는 로컬 데이터 파일과 같은 로컬 데이터를 기반으로 하는 형식 공급자에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-315">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="acf90-316">간단한 CSV 파일 공급자</span><span class="sxs-lookup"><span data-stu-id="acf90-316">Simple CSV File Provider</span></span>

<span data-ttu-id="acf90-317">간단한 예로, CSV(쉼표 분리값) 형식으로 과학 데이터에 액세스하기 위한 형식 공급자를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="acf90-318">이 섹션에서는 CSV 파일에 다음 표와 같이 헤더 행 다음에 부동 지점 데이터가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="acf90-319">거리(미터)</span><span class="sxs-lookup"><span data-stu-id="acf90-319">Distance (meter)</span></span>|<span data-ttu-id="acf90-320">시간(두 번째)</span><span class="sxs-lookup"><span data-stu-id="acf90-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="acf90-321">50.0</span><span class="sxs-lookup"><span data-stu-id="acf90-321">50.0</span></span>|<span data-ttu-id="acf90-322">3.7</span><span class="sxs-lookup"><span data-stu-id="acf90-322">3.7</span></span>|
|<span data-ttu-id="acf90-323">100.0</span><span class="sxs-lookup"><span data-stu-id="acf90-323">100.0</span></span>|<span data-ttu-id="acf90-324">5.2</span><span class="sxs-lookup"><span data-stu-id="acf90-324">5.2</span></span>|
|<span data-ttu-id="acf90-325">150.0</span><span class="sxs-lookup"><span data-stu-id="acf90-325">150.0</span></span>|<span data-ttu-id="acf90-326">6.4</span><span class="sxs-lookup"><span data-stu-id="acf90-326">6.4</span></span>|

<span data-ttu-id="acf90-327">`Distance` 이 섹션에서는 형식의 `float<meter>` 속성과 형식의 `Time` `float<second>`속성을 사용하여 행을 얻는 데 사용할 수 있는 형식을 제공하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="acf90-328">간단히 하기 위해 다음과 같은 가정이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="acf90-329">헤더 이름은 단위가 없거나 "이름(단위)" 양식이 있으며 쉼표를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="acf90-330">단위는 [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames 모듈(F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) 모듈이 정의하는 대로 모든 시스템 국제(SI) 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-330">Units are all System International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="acf90-331">단위는 모두 복합(예: 미터/초)이 아닌 단순(예: 미터)입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="acf90-332">모든 열에는 부동 점 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-332">All columns contain floating point data.</span></span>

<span data-ttu-id="acf90-333">보다 완전한 공급자는 이러한 제한을 완화할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="acf90-334">다시 첫 번째 단계는 API의 모양을 고려하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="acf90-335">이전 테이블의 콘텐츠(쉼표로 분리된 형식)를 사용하여 `info.csv` 파일을 지정한 경우 공급자의 사용자는 다음 예제와 비슷한 코드를 작성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="acf90-336">이 경우 컴파일러는 이러한 호출을 다음 예제와 같은 것으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="acf90-337">최적의 변환을 위해서는 형식 공급자가 `CsvFile` 형식 공급자의 어셈블리에서 실제 형식을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="acf90-338">형식 공급자는 종종 몇 가지 도우미 형식 및 메서드를 사용하여 중요한 논리를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="acf90-339">측정값은 런타임에 지워지므로 `float[]` 행에 대해 지워진 유형으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="acf90-340">컴파일러는 다른 열을 다른 측정값 형식을 갖는 것으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="acf90-341">예를 들어, 이 예제의 첫 `float<meter>`번째 열에는 `float<second>`type 이 있고 두 번째 열에는 .</span><span class="sxs-lookup"><span data-stu-id="acf90-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="acf90-342">그러나 지워진 표현은 매우 간단하게 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="acf90-343">다음 코드는 구현의 핵심을 보여 주며, 구현의 핵심을 보여 주시고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-343">The following code shows the core of the implementation.</span></span>

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

<span data-ttu-id="acf90-344">구현에 대한 다음 사항을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="acf90-345">오버로드된 생성자는 원본 파일 또는 동일한 스키마가 있는 파일을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="acf90-346">이 패턴은 로컬 또는 원격 데이터 원본에 대한 형식 공급자를 작성할 때 일반적이며 이 패턴을 사용하면 로컬 파일을 원격 데이터의 템플릿으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="acf90-347">형식 공급자 생성자에게 전달되는 [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) 값을 사용하여 상대 파일 이름을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-347">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="acf90-348">메서드를 `AddDefinitionLocation` 사용하여 제공된 속성의 위치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="acf90-349">따라서 제공된 속성에서 사용하는 `Go To Definition` 경우 CSV 파일은 Visual Studio에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="acf90-350">이 `ProvidedMeasureBuilder` 형식을 사용하여 SI 단위를 조회하고 관련 `float<_>` 형식을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="acf90-351">주요 교훈</span><span class="sxs-lookup"><span data-stu-id="acf90-351">Key Lessons</span></span>

<span data-ttu-id="acf90-352">이 섹션에서는 데이터 원본 자체에 포함된 간단한 스키마를 사용하여 로컬 데이터 원본에 대한 형식 공급자를 만드는 방법을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="acf90-353">더 나아가기</span><span class="sxs-lookup"><span data-stu-id="acf90-353">Going Further</span></span>

<span data-ttu-id="acf90-354">다음 섹션에는 추가 학습을 위한 제안사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-354">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="acf90-355">지워진 형식에 대한 컴파일된 코드 살펴보기</span><span class="sxs-lookup"><span data-stu-id="acf90-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="acf90-356">형식 공급자의 사용이 내보낸 코드에 어떻게 해당하는지 에 대한 몇 가지 아이디어를 제공하려면 이 `HelloWorldTypeProvider` 항목의 앞에서 사용된 함수를 사용하여 다음 함수를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="acf90-357">다음은 ildasm.exe를 사용하여 디컴파일된 결과 코드의 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

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

<span data-ttu-id="acf90-358">예제에서 볼 수 있듯이 형식 `Type1` 및 `InstanceProperty` 속성에 대한 모든 언급이 지워져 관련 런타임 형식에 대한 작업만 남습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="acf90-359">유형 공급자를 위한 디자인 및 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="acf90-359">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="acf90-360">형식 공급자를 작성할 때 다음 규칙을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="acf90-361">**연결 프로토콜 공급자** 일반적으로 OData 또는 SQL 연결과 같은 데이터 및 서비스 연결 프로토콜에 대한 대부분의 `TypeProvider` 공급자 `TypeProviders`DLL의 이름은 또는 에 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="acf90-362">예를 들어 다음 문자열과 유사한 DLL 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-362">For example, use a DLL name that resembles the following string:</span></span>

`Fabrikam.Management.BasicTypeProviders.dll`

<span data-ttu-id="acf90-363">제공된 형식이 해당 네임스페이스의 멤버인지 확인하고 구현한 연결 프로토콜을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="acf90-364">**일반 코딩을 위한 유틸리티 공급자**.</span><span class="sxs-lookup"><span data-stu-id="acf90-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="acf90-365">정규식과 같은 유틸리티 형식 공급자의 경우 형식 공급자는 다음 예제와 같이 기본 라이브러리의 일부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="acf90-366">이 경우 제공된 형식은 일반 .NET 디자인 규칙에 따라 적절한 지점에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="acf90-367">**싱글톤 데이터 소스**.</span><span class="sxs-lookup"><span data-stu-id="acf90-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="acf90-368">일부 형식 공급자는 단일 전용 데이터 원본에 연결하고 데이터만 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="acf90-369">이 경우 접미사를 `TypeProvider` 삭제하고 .NET 명명에 대한 일반 규칙을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="acf90-370">자세한 내용은 이 `GetConnection` 항목의 후반부에서 설명하는 디자인 규칙을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="acf90-371">유형 공급자를 위한 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="acf90-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="acf90-372">다음 섹션에서는 형식 공급자를 작성할 때 사용할 수 있는 디자인 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-372">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="acf90-373">GetConnection 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="acf90-373">The GetConnection Design Pattern</span></span>

<span data-ttu-id="acf90-374">다음 예제와 같이 FSharp.Data.TypeProviders.dll의 형식 공급자가 사용하는 `GetConnection` 패턴을 사용하도록 대부분의 형식 공급자를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="acf90-375">원격 데이터 및 서비스로 지원되는 유형 공급자</span><span class="sxs-lookup"><span data-stu-id="acf90-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="acf90-376">원격 데이터 및 서비스가 지원하는 형식 공급자를 만들기 전에 연결된 프로그래밍에 내재된 다양한 문제를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="acf90-377">이러한 문제에는 다음과 같은 고려 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="acf90-378">스키마 매핑</span><span class="sxs-lookup"><span data-stu-id="acf90-378">schema mapping</span></span>

- <span data-ttu-id="acf90-379">스키마 변경이 있는 경우 의 생수 및 무효화</span><span class="sxs-lookup"><span data-stu-id="acf90-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="acf90-380">스키마 캐싱</span><span class="sxs-lookup"><span data-stu-id="acf90-380">schema caching</span></span>

- <span data-ttu-id="acf90-381">데이터 액세스 작업의 비동기 구현</span><span class="sxs-lookup"><span data-stu-id="acf90-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="acf90-382">LINQ 쿼리를 포함한 지원 쿼리</span><span class="sxs-lookup"><span data-stu-id="acf90-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="acf90-383">자격 증명 및 인증</span><span class="sxs-lookup"><span data-stu-id="acf90-383">credentials and authentication</span></span>

<span data-ttu-id="acf90-384">이 항목에서는 이러한 문제를 더 자세히 살펴보지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="acf90-385">추가 작성 기술</span><span class="sxs-lookup"><span data-stu-id="acf90-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="acf90-386">사용자 고유의 형식 공급자를 작성할 때 다음과 같은 추가 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="acf90-387">주문형 및 멤버 만들기</span><span class="sxs-lookup"><span data-stu-id="acf90-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="acf90-388">ProvidedType API에 AddMember 버전이 지연되었습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="acf90-389">이러한 버전은 형식의 주문형 공간을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="acf90-390">배열 형식 및 일반 형식 인스턴스화 제공</span><span class="sxs-lookup"><span data-stu-id="acf90-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="acf90-391">을 포함하여 `MakeArrayType` `MakePointerType` `MakeGenericType` <xref:System.Type> `ProvidedTypeDefinitions`의 모든 인스턴스에서 정상 을 사용하여 제공된 멤버(시그니처에 배열 형식, byref 형식 및 제네릭 형식의 인스턴스화 포함)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="acf90-392">경우에 따라 `ProvidedTypeBuilder.MakeGenericType`에서 도우미를 사용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="acf90-393">자세한 내용은 [유형 공급자 SDK 설명서를](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="acf90-394">측정 주석 단위 제공</span><span class="sxs-lookup"><span data-stu-id="acf90-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="acf90-395">ProvidedType API는 측정 주석을 제공하기 위한 도우미를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="acf90-396">예를 들어 형식을 `float<kg>`제공하려면 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="acf90-397">형식을 `Nullable<decimal<kg/m^2>>`제공하려면 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="acf90-398">프로젝트 로컬 또는 스크립트 로컬 리소스 액세스</span><span class="sxs-lookup"><span data-stu-id="acf90-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="acf90-399">형식 공급자의 각 인스턴스는 `TypeProviderConfig` 구성 하는 동안 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="acf90-400">이 값에는 공급자에 대한 "확인 폴더"(즉, 컴파일용 프로젝트 폴더 또는 스크립트가 포함된 디렉터리), 참조된 어셈블리 목록 및 기타 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="acf90-401">무효화</span><span class="sxs-lookup"><span data-stu-id="acf90-401">Invalidation</span></span>

<span data-ttu-id="acf90-402">공급자는 F# 언어 서비스에 스키마 가정이 변경되었을 수 있음을 알리기 위해 무효화 신호를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="acf90-403">무효화가 발생하면 공급자가 Visual Studio에서 호스팅되는 경우 형식 검사가 다시 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="acf90-404">공급자가 F# 대화형 또는 F# 컴파일러(fsc.exe)에서 호스팅될 때 이 신호는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="acf90-405">캐싱 스키마 정보</span><span class="sxs-lookup"><span data-stu-id="acf90-405">Caching Schema Information</span></span>

<span data-ttu-id="acf90-406">공급자는 종종 스키마 정보에 대한 액세스를 캐시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="acf90-407">캐시된 데이터는 정적 매개 변수 또는 사용자 데이터로 지정된 파일 이름을 사용하여 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="acf90-408">스키마 캐싱의 예는 `LocalSchemaFile` 어셈블리의 형식 `FSharp.Data.TypeProviders` 공급자의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="acf90-409">이러한 공급자의 구현에서 이 정적 매개 변수는 형식을 공급자가 네트워크를 통해 데이터 원본에 액세스하는 대신 지정된 로컬 파일에서 스키마 정보를 사용하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="acf90-410">캐시된 스키마 정보를 사용하려면 정적 매개 `ForceUpdate` 변수도 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="acf90-411">유사한 기술을 사용하여 온라인 및 오프라인 데이터 액세스를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="acf90-412">백업 어셈블리</span><span class="sxs-lookup"><span data-stu-id="acf90-412">Backing Assembly</span></span>

<span data-ttu-id="acf90-413">`.dll` 또는 `.exe` 파일을 컴파일할 때 생성된 형식에 대한 백업 .dll 파일이 결과 어셈블리에 정적으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="acf90-414">이 링크는 중간 언어(IL) 형식 정의 및 백업 어셈블리에서 최종 어셈블리로 관리되는 리소스를 복사하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="acf90-415">F# 대화형을 사용하면 백업 .dll 파일이 복사되지 않고 대신 F# 대화형 프로세스에 직접 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="acf90-416">형식 공급자의 예외 및 진단</span><span class="sxs-lookup"><span data-stu-id="acf90-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="acf90-417">제공된 형식의 모든 멤버를 모두 사용하여 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="acf90-418">모든 경우에 형식 공급자가 예외를 throw하는 경우 호스트 컴파일러는 오류를 특정 형식 공급자에 특성화합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="acf90-419">형식 공급자 예외는 내부 컴파일러 오류를 발생해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="acf90-420">형식 공급자는 경고를 보고할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="acf90-421">형식 공급자가 F# 컴파일러, F# 개발 환경 또는 F# 대화형에서 호스팅되는 경우 해당 공급자의 모든 예외가 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="acf90-422">Message 속성은 항상 오류 텍스트이며 스택 추적이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="acf90-423">예외를 throw하려는 경우 다음과 같은 예제를 throw할 `System.NotSupportedException`수 `System.IO.IOException` `System.Exception`있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="acf90-424">생성된 유형 제공</span><span class="sxs-lookup"><span data-stu-id="acf90-424">Providing Generated Types</span></span>

<span data-ttu-id="acf90-425">지금까지 이 문서에서는 지워진 형식을 제공하는 방법을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="acf90-426">F#의 형식 공급자 메커니즘을 사용하여 생성된 형식을 제공할 수 있으며, 이 형식은 사용자의 프로그램에 실제 .NET 형식 정의로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="acf90-427">형식 정의를 사용하여 생성된 제공된 형식을 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="acf90-428">F# 3.0 릴리스의 일부인 ProvidedType-0.2 도우미 코드는 생성된 형식을 제공하기 위한 제한된 지원만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="acf90-429">생성된 형식 정의에 대해 다음 문은 true여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="acf90-430">`isErased`은 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="acf90-431">생성된 코드 조각에 대한 컨테이너를 나타내는 새로 생성된 `ProvidedAssembly()`형식에 생성된 형식을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="acf90-432">공급자는 디스크에 일치하는 .dll 파일이 있는 실제 백업 .NET .dll 파일이 있는 어셈블리가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="acf90-433">규칙 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="acf90-433">Rules and Limitations</span></span>

<span data-ttu-id="acf90-434">형식 공급자를 작성할 때는 다음 규칙과 제한 사항에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="acf90-434">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="acf90-435">제공된 유형에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-435">Provided types must be reachable</span></span>

<span data-ttu-id="acf90-436">제공된 모든 형식은 중첩되지 않은 형식에서 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="acf90-437">중첩되지 않은 형식은 `TypeProviderForNamespaces` 생성자 호출 또는 에 대한 `AddNamespace`호출에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="acf90-438">예를 들어 공급자가 형식을 `StaticClass.P : T`제공하는 경우 T가 중첩되지 않은 형식이거나 중첩된 형식인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="acf90-439">예를 들어 일부 공급자에는 이러한 `DataTypes` `T1, T2, T3, ...` 형식을 포함하는 정적 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="acf90-440">그렇지 않으면 어셈블리 A의 T 형식에 대한 참조가 발견되었지만 해당 어셈블리에서 형식을 찾을 수 없다는 오류가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="acf90-441">이 오류가 나타나면 공급자 형식에서 모든 하위 유형에 도달할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="acf90-442">참고: `T1, T2, T3...` 이러한 형식을 *즉석* 에서 유형이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="acf90-443">액세스 가능한 네임스페이스 또는 상위 형식에 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="acf90-444">형식 공급자 메커니즘의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="acf90-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="acf90-445">F#의 형식 공급자 메커니즘에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="acf90-446">F#의 형식 공급자에 대한 기본 인프라는 제공된 제네릭 형식 또는 제공된 제네릭 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="acf90-447">메커니즘은 정적 매개 변수를 사용 하 고 중첩 된 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="acf90-448">개발 팁</span><span class="sxs-lookup"><span data-stu-id="acf90-448">Development Tips</span></span>

<span data-ttu-id="acf90-449">개발 과정에서 다음과 같은 유용한 팁을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-449">You might find the following tips helpful during the development process:</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="acf90-450">비주얼 스튜디오의 두 인스턴스 실행</span><span class="sxs-lookup"><span data-stu-id="acf90-450">Run two instances of Visual Studio</span></span>

<span data-ttu-id="acf90-451">테스트 IDE가 type 공급자를 다시 빌드하지 못하도록 하는 .dll 파일에 대한 잠금을 수행하므로 한 인스턴스에서 형식 공급자를 개발하고 다른 인스턴스에서 공급자를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="acf90-452">따라서 공급자가 첫 번째 인스턴스에 빌드되는 동안 Visual Studio의 두 번째 인스턴스를 닫은 다음 공급자가 빌드된 후 두 번째 인스턴스를 다시 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="acf90-453">fsc.exe 호출을 사용하여 유형 공급자를 디버그</span><span class="sxs-lookup"><span data-stu-id="acf90-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="acf90-454">다음 도구를 사용하여 형식 공급자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="acf90-455">fsc.exe(F# 명령줄 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="acf90-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="acf90-456">fsi.exe (F# 인터랙티브 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="acf90-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="acf90-457">devenv.exe (비주얼 스튜디오)</span><span class="sxs-lookup"><span data-stu-id="acf90-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="acf90-458">테스트 스크립트 파일(예: script.fsx)에서 fsc.exe를 사용하여 형식 공급자를 가장 쉽게 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="acf90-459">명령 프롬프트에서 디버거를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-459">You can launch a debugger from a command prompt.</span></span>

```console
devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="acf90-460">인쇄-stdout 로깅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf90-460">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="acf90-461">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acf90-461">See also</span></span>

- [<span data-ttu-id="acf90-462">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="acf90-462">Type Providers</span></span>](index.md)
- [<span data-ttu-id="acf90-463">형식 공급자 SDK</span><span class="sxs-lookup"><span data-stu-id="acf90-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
