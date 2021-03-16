---
title: .NET에서 종속성 주입 사용
description: .NET 애플리케이션에서 종속성 주입을 사용하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 11/13/2020
ms.topic: tutorial
no-loc:
- Transient
- Scoped
- Singleton
- Example
ms.openlocfilehash: d6654d5d1c8f7959e96998c18a1790cce46ebf41
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102402158"
---
# <a name="tutorial-use-dependency-injection-in-net"></a><span data-ttu-id="ed14a-103">자습서: .NET에서 종속성 주입 사용</span><span class="sxs-lookup"><span data-stu-id="ed14a-103">Tutorial: Use dependency injection in .NET</span></span>

<span data-ttu-id="ed14a-104">이 자습서에서는 [.NET에서 DI(종속성 주입)](dependency-injection.md)를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-104">This tutorial shows how to use [dependency injection (DI) in .NET](dependency-injection.md).</span></span> <span data-ttu-id="ed14a-105">‘Microsoft 확장’에서 DI는 <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>에서 서비스가 추가 및 구성되는 주요 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-105">With *Microsoft Extensions*, DI is a first-class citizen where services are added and configured in an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="ed14a-106"><xref:Microsoft.Extensions.Hosting.IHost> 인터페이스는 등록된 모든 서비스의 컨테이너 역할을 하는 <xref:System.IServiceProvider> 인스턴스를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-106">The <xref:Microsoft.Extensions.Hosting.IHost> interface exposes the <xref:System.IServiceProvider> instance, which acts as a container of all the registered services.</span></span>

<span data-ttu-id="ed14a-107">이 자습서에서는 다음 작업 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="ed14a-108">종속성 주입을 사용하는 .NET 콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="ed14a-108">Create a .NET console app that uses dependency injection</span></span>
> - <span data-ttu-id="ed14a-109">[제네릭 호스트](generic-host.md) 빌드 및 구성</span><span class="sxs-lookup"><span data-stu-id="ed14a-109">Build and configure a [Generic Host](generic-host.md)</span></span>
> - <span data-ttu-id="ed14a-110">여러 인터페이스 및 해당 구현 작성</span><span class="sxs-lookup"><span data-stu-id="ed14a-110">Write several interfaces and corresponding implementations</span></span>
> - <span data-ttu-id="ed14a-111">DI를 위해 서비스 수명 및 범위 지정 사용</span><span class="sxs-lookup"><span data-stu-id="ed14a-111">Use service lifetime and scoping for DI</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed14a-112">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed14a-112">Prerequisites</span></span>

- <span data-ttu-id="ed14a-113">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) 이상</span><span class="sxs-lookup"><span data-stu-id="ed14a-113">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) or later.</span></span>
- <span data-ttu-id="ed14a-114">새 .NET 애플리케이션 만들기 및 NuGet 패키지 설치에 관한 지식</span><span class="sxs-lookup"><span data-stu-id="ed14a-114">Familiarity with creating new .NET applications and installing NuGet packages.</span></span>

## <a name="create-a-new-console-application"></a><span data-ttu-id="ed14a-115">새 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="ed14a-115">Create a new console application</span></span>

<span data-ttu-id="ed14a-116">[dotnet new](../tools/dotnet-new.md) 명령 또는 IDE 새 프로젝트 마법사를 사용하여 **ConsoleDI.Example** 라는 새 .NET 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-116">Using either the [dotnet new](../tools/dotnet-new.md) command or an IDE new project wizard, create a new .NET console application named **ConsoleDI.Example**.</span></span> <span data-ttu-id="ed14a-117">[Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet 패키지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-117">Add the [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet package to the project.</span></span>

## <a name="add-interfaces"></a><span data-ttu-id="ed14a-118">인터페이스 추가</span><span class="sxs-lookup"><span data-stu-id="ed14a-118">Add interfaces</span></span>

<span data-ttu-id="ed14a-119">프로젝트 루트 디렉터리에 다음 인터페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-119">Add the following interfaces to the project root directory:</span></span>

<span data-ttu-id="ed14a-120">*IOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="ed14a-120">*IOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

<span data-ttu-id="ed14a-121">`IOperation` 인터페이스는 단일 `OperationId` 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-121">The `IOperation` interface defines a single `OperationId` property.</span></span>

<span data-ttu-id="ed14a-122">*ITransientOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="ed14a-122">*ITransientOperation.cs*</span></span>

<span data-ttu-id="ed14a-123">:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::</span><span class="sxs-lookup"><span data-stu-id="ed14a-123">:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::</span></span>

<span data-ttu-id="ed14a-124">*IScopedOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="ed14a-124">*IScopedOperation.cs*</span></span>

<span data-ttu-id="ed14a-125">:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::</span><span class="sxs-lookup"><span data-stu-id="ed14a-125">:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::</span></span>

<span data-ttu-id="ed14a-126">*ISingletonOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="ed14a-126">*ISingletonOperation.cs*</span></span>

<span data-ttu-id="ed14a-127">:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::</span><span class="sxs-lookup"><span data-stu-id="ed14a-127">:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::</span></span>

<span data-ttu-id="ed14a-128">`IOperation`의 모든 하위 인터페이스는 의도한 서비스 수명에 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-128">All of the subinterfaces of `IOperation` name their intended service lifetime.</span></span> <span data-ttu-id="ed14a-129">예: “Transient” 또는 “Singleton”.</span><span class="sxs-lookup"><span data-stu-id="ed14a-129">For example, "Transient" or "Singleton".</span></span>

## <a name="add-default-implementation"></a><span data-ttu-id="ed14a-130">기본 구현 추가</span><span class="sxs-lookup"><span data-stu-id="ed14a-130">Add default implementation</span></span>

<span data-ttu-id="ed14a-131">다양한 작업에 대해 다음 기본 구현을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-131">Add the following default implementation for the various operations:</span></span>

<span data-ttu-id="ed14a-132">*DefaultOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="ed14a-132">*DefaultOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

<span data-ttu-id="ed14a-133">`DefaultOperation`은 명명된 모든 마커 인터페이스를 구현하고 새 GUID(Globally Unique identifier)의 마지막 4개 문자로 `OperationId` 속성을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-133">The `DefaultOperation` implements all of the named marker interfaces and initializes the `OperationId` property to the last four characters of a new globally unique identifier (GUID).</span></span>

## <a name="add-service-that-requires-di"></a><span data-ttu-id="ed14a-134">DI가 필요한 서비스 추가</span><span class="sxs-lookup"><span data-stu-id="ed14a-134">Add service that requires DI</span></span>

<span data-ttu-id="ed14a-135">콘솔 앱에 서비스 역할을 하는 다음 작업 로거 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-135">Add the following operation logger object, which acts as a service to the console app:</span></span>

<span data-ttu-id="ed14a-136">*OperationLogger.cs*</span><span class="sxs-lookup"><span data-stu-id="ed14a-136">*OperationLogger.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

<span data-ttu-id="ed14a-137">`OperationLogger`는 앞에서 언급한 각 마커 인터페이스인 `ITransientOperation`, `IScopedOperation`, `ISingletonOperation`이 필요한 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-137">The `OperationLogger` defines a constructor that requires each of the aforementioned marker interfaces, that is; `ITransientOperation`, `IScopedOperation`, and `ISingletonOperation`.</span></span> <span data-ttu-id="ed14a-138">개체는 소비자가 지정된 `scope` 매개 변수를 사용하여 작업을 로그할 수 있는 단일 메서드를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-138">The object exposes a single method that allows the consumer to log the operations with a given `scope` parameter.</span></span> <span data-ttu-id="ed14a-139">호출된 경우 `LogOperations` 메서드는 범위 문자열과 메시지를 사용하여 각 작업의 고유 식별자를 로그합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-139">When invoked, the `LogOperations` method logs each operation's unique identifier with the scope string and message.</span></span>

## <a name="register-services-for-di"></a><span data-ttu-id="ed14a-140">DI를 위해 서비스 등록</span><span class="sxs-lookup"><span data-stu-id="ed14a-140">Register services for DI</span></span>

<span data-ttu-id="ed14a-141">다음 코드로 *Program.cs* 를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-141">Update *Program.cs* with the following code:</span></span>

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

> <span data-ttu-id="ed14a-142">각 `services.Add{SERVICE_NAME}` 확장 메서드는 서비스를 추가하고 잠재적으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-142">Each `services.Add{SERVICE_NAME}` extension method adds, and potentially configures, services.</span></span> <span data-ttu-id="ed14a-143">앱에서 이 규칙을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-143">We recommended that apps follow this convention.</span></span> <span data-ttu-id="ed14a-144">확장 메서드를 <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> 네임스페이스에 배치하여 서비스 등록 그룹을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-144">Place extension methods in the <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> namespace to encapsulate groups of service registrations.</span></span> <span data-ttu-id="ed14a-145">DI 확장 메서드에 대해 `Microsoft.Extensions.DependencyInjection` 네임스페이스 부분을 포함하면 다음도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-145">Including the namespace portion `Microsoft.Extensions.DependencyInjection` for DI extension methods also:</span></span>
>
> - <span data-ttu-id="ed14a-146">더 이상의 `using` 블록을 추가하지 않고도 [IntelliSense](/visualstudio/ide/using-intellisense)에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-146">Allows them to be displayed in [IntelliSense](/visualstudio/ide/using-intellisense) without adding additional `using` blocks.</span></span>
> - <span data-ttu-id="ed14a-147">일반적으로 해당 확장 메서드가 호출되는 `Program` 또는 `Startup` 클래스의 과도한 `using` 문을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-147">Prevents excessive `using` statements in the `Program` or `Startup` classes where these extension methods are typically called.</span></span>

<span data-ttu-id="ed14a-148">앱은 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-148">The app:</span></span>

- <span data-ttu-id="ed14a-149">[기본 바인더 설정](generic-host.md#default-builder-settings)을 사용하여 <xref:Microsoft.Extensions.Hosting.IHostBuilder> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-149">Creates an <xref:Microsoft.Extensions.Hosting.IHostBuilder> instance with the [default binder settings](generic-host.md#default-builder-settings).</span></span>
- <span data-ttu-id="ed14a-150">서비스를 구성하고 해당 서비스 수명으로 서비스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-150">Configures services and adds them with their corresponding service lifetime.</span></span>
- <span data-ttu-id="ed14a-151"><xref:Microsoft.Extensions.Hosting.IHostBuilder.Build>를 호출하고 <xref:Microsoft.Extensions.Hosting.IHost> 인스턴스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-151">Calls <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> and assigns an instance of <xref:Microsoft.Extensions.Hosting.IHost>.</span></span>
- <span data-ttu-id="ed14a-152">`ExemplifyScoping`를 호출하여 <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-152">Calls `ExemplifyScoping`, passing in the <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>.</span></span>

## <a name="conclusion"></a><span data-ttu-id="ed14a-153">결론</span><span class="sxs-lookup"><span data-stu-id="ed14a-153">Conclusion</span></span>

<span data-ttu-id="ed14a-154">앱은 다음 예제와 같은 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-154">The app displays output similar to the following example:</span></span>

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
```

<span data-ttu-id="ed14a-155">앱 출력에서 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-155">From the app output, you can see that:</span></span>

- <span data-ttu-id="ed14a-156">Transient 작업은 항상 다르지만 서비스를 검색할 때마다 새 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-156">Transient operations are always different, a new instance is created with every retrieval of the service.</span></span>
- <span data-ttu-id="ed14a-157">Scoped 작업은 새 범위에서 변경될 뿐 아니라 한 범위 내에서는 동일한 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-157">Scoped operations change only with a new scope, but are the same instance within a scope.</span></span>
- <span data-ttu-id="ed14a-158">Singleton 작업은 항상 동일하며 새 인스턴스는 한 번만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ed14a-158">Singleton operations are always the same, a new instance is only created once.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed14a-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed14a-159">See also</span></span>

* [<span data-ttu-id="ed14a-160">종속성 주입 지침</span><span class="sxs-lookup"><span data-stu-id="ed14a-160">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
* [<span data-ttu-id="ed14a-161">ASP.NET Core에서 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="ed14a-161">Dependency injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)
