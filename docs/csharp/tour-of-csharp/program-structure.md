---
title: C# 프로그램 구조 - C# 언어 둘러보기
description: C# 프로그램의 기본 구성 요소에 대해 알아보기
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c09c11a4dd957b29b2adb7aaa8d68a50f30620b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156833"
---
# <a name="program-structure"></a><span data-ttu-id="01781-103">프로그램 구조</span><span class="sxs-lookup"><span data-stu-id="01781-103">Program Structure</span></span>

<span data-ttu-id="01781-104">C#의 핵심적인 조직 개념은 ***프로그램***, ***네임스페이스***, ***형식***, ***멤버*** 및 ***어셈블리***입니다.</span><span class="sxs-lookup"><span data-stu-id="01781-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="01781-105">C# 프로그램은 하나 이상의 소스 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01781-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="01781-106">프로그램은 멤버를 포함하고 네임스페이스로 구성될 수 있는 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="01781-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="01781-107">클래스와 인터페이스는 형식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="01781-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="01781-108">필드, 메서드, 속성 및 이벤트는 멤버의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="01781-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="01781-109">C# 프로그램을 컴파일하면 실제로 어셈블리로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="01781-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="01781-110">어셈블리는 일반적으로 ***애플리케이션***을 구현하는지 또는 ***라이브러리***를 구현하는지에 따라 각각 파일 확장명 `.exe` 또는 `.dll`을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="01781-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="01781-111">`dotnet new` 명령을 사용하여 이름이 *acme*인 라이브러리 프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01781-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```console
dotnet new classlib -o acme
```

<span data-ttu-id="01781-112">이 프로젝트에서 `Acme.Collections`라는 네임스페이스에 이름이 `Stack`인 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="01781-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="01781-113">이 클래스의 정규화된 이름은 `Acme.Collections.Stack`입니다.</span><span class="sxs-lookup"><span data-stu-id="01781-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="01781-114">클래스에는 필드 `top`, 2개의 메서드 `Push` 및 `Pop`, 중첩된 클래스 `Entry` 등의 여러 멤버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="01781-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="01781-115">`Entry` 클래스는 필드 `next` 및 필드 `data`, 생성자의 세 멤버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="01781-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="01781-116">다음 명령은</span><span class="sxs-lookup"><span data-stu-id="01781-116">The command:</span></span>

```console
dotnet build
```

<span data-ttu-id="01781-117">예제를 라이브러리(`Main` 진입점이 없는 코드)를 컴파일하고 `acme.dll`이라는 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="01781-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="01781-118">어셈블리에는 IL(중간 언어) 명령 형식의 실행 코드와 메타데이터 형식의 기호 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="01781-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="01781-119">어셈블리가 실행되기 전에, .NET 공용 언어 런타임의 JIT(Just-In-Time) 컴파일러가 어셈블리 안의 IL 코드를 해당 프로세서에 맞는 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="01781-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="01781-120">어셈블리는 코드와 메타데이터를 모두 포함하는 기능의 자체 설명 단위이므로 C#에서는 `#include` 지시문과 헤더 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01781-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="01781-121">특정 어셈블리에 포함된 공용 형식 및 멤버는 프로그램을 컴파일할 때 해당 어셈블리를 참조하는 것만으로 C# 프로그램에서 사용 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="01781-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="01781-122">예를 들어 이 프로그램에서는 `acme.dll` 어셈블리의 `Acme.Collections.Stack` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01781-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="01781-123">앞에 나온 프로그램 프로젝트의 *csproj* 파일은 C# 컴파일러에 대한 참조 노드를 포함해야 `acme.dll` 어셈블리에 있는 클래스에 대한 참조를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01781-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="01781-124">위와 같이 추가한 후에, `dotnet build`는 이름이 `example.exe`인 실행 가능한 어셈블리를 만들고, 이 어셈블리가 실행되면 다음과 같은 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01781-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="01781-125">C#은 프로그램의 소스 텍스트가 여러 소스 파일에 저장되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="01781-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="01781-126">다중 파일 C# 프로그램이 컴파일되면 모든 소스 파일이 함께 처리되고 소스 파일은 서로 자유롭게 참조될 수 있습니다. 개념적으로는 마치 모든 소스 파일이 처리되기 전에 하나의 큰 파일로 연결되는 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="01781-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="01781-127">소수의 경우를 제외하고 선언 순서는 중요하지 않으므로 C#에서는 정방향 선언이 필요한 경우가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01781-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="01781-128">C#은 소스 파일을 하나의 공용 형식만 선언하도록 제한하거나 소스 파일 이름이 소스 파일에 선언된 형식과 일치하도록 요구하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01781-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="01781-129">[이전](index.md)
>[다음](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="01781-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
