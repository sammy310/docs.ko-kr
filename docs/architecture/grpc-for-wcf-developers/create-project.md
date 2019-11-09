---
title: WCF 개발자를 위한 새 ASP.NET Core gRPC 프로젝트 gRPC 만들기
description: Visual Studio를 사용 하거나 명령줄에서 gRPC 프로젝트를 만드는 방법에 대해 알아봅니다.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: a30d19e1e48692ad68a648406d4bf369937744d7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841662"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="55bf2-103">새 ASP.NET Core gRPC 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="55bf2-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="55bf2-104">.NET Core는 명령줄에서 프로젝트 및 솔루션을 만들고 관리할 수 있는 강력한 CLI 도구인 `dotnet`와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="55bf2-105">이 도구는 Visual Studio와 긴밀 하 게 통합 되므로 친숙 한 GUI 인터페이스를 통해서도 모든 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="55bf2-106">이 장에서는 새 ASP.NET Core gRPC 프로젝트를 만드는 두 가지 방법을 모두 보여 줍니다. 먼저 Visual Studio를 사용 하 여 .NET Core CLI 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="55bf2-107">Visual Studio를 사용 하 여 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="55bf2-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55bf2-108">ASP.NET Core 3.0 앱을 개발 하려면 **ASP.NET 및 웹 개발** 워크 로드가 설치 된 Visual Studio 2019.3 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="55bf2-109">*빈 솔루션* 템플릿에서 **TraderSys** 라는 빈 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="55bf2-110">`src`이라는 솔루션 폴더를 추가 하 고 폴더를 마우스 오른쪽 단추로 클릭 한 다음 상황에 맞는 메뉴에서 **추가** > **새 프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="55bf2-111">템플릿 검색 상자에 `grpc`를 입력 하면 `gRPC Service`라는 프로젝트 템플릿이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

![GRPC 서비스 프로젝트 템플릿을 보여 주는 새 프로젝트 추가 대화 상자](media/create-project/new-grpc-project.png)

<span data-ttu-id="55bf2-113">**다음** 을 클릭 하 여 **프로젝트 구성** 대화 상자를 계속 진행 하 고 프로젝트 이름을 `TraderSys.Portfolios`한 다음 해당 **위치**에 `src` 하위 디렉터리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![프로젝트 구성 대화 상자](media/create-project/configure-project.png)

<span data-ttu-id="55bf2-115">**다음** 을 클릭 하 여 **새 grpc 프로젝트** 대화 상자로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

![새 gRPC 프로젝트 대화 상자](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="55bf2-117">현재 서비스 만들기에 대 한 제한 된 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="55bf2-118">Docker는이 책에서 나중에 도입 되므로 지금은 해당 확인란을 선택 하지 않은 상태로 두고 **만들기**를 클릭 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="55bf2-119">첫 번째 ASP.NET Core 3.0 gRPC 프로젝트가 생성 되어 솔루션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="55bf2-120">`dotnet CLI`를 사용 하는 방법을 모르는 경우 [예제 코드 섹션 정리](#clean-up-the-example-code) 로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="55bf2-121">.NET Core CLI를 사용 하 여 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="55bf2-122">이 섹션에서는 명령줄에서 솔루션 및 프로젝트를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="55bf2-123">아래와 같이 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-123">Create the solution as shown below.</span></span> <span data-ttu-id="55bf2-124">`-o` (또는 `--output`) 플래그는 현재 디렉터리에 생성 되는 출력 디렉터리를 지정 합니다 (존재 하지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="55bf2-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="55bf2-125">솔루션에는 디렉터리와 동일한 이름 (`TraderSys.sln`)이 지정 됩니다. `-n` (또는 `--name`) 플래그를 사용 하 여 다른 이름을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="55bf2-126">ASP.NET Core 3.0는 gRPC 서비스용 CLI 템플릿과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="55bf2-127">이 템플릿을 사용 하 여 새 프로젝트를 만들고 `src` 하위 디렉터리에 ASP.NET Core 프로젝트에 대 한 규칙으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="55bf2-128">`-n` 플래그를 사용 하 여 다른 이름을 지정 하지 않는 한, 디렉터리 (즉, `TraderSys.Portfolios.csproj`) 뒤에 프로젝트의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="55bf2-129">마지막으로 `dotnet sln` 명령을 사용 하 여 솔루션에 프로젝트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="55bf2-130">지정 된 디렉터리에는 단일 `.csproj` 파일만 포함 되어 있으므로 입력을 저장할 디렉터리만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="55bf2-131">이제 Visual Studio 2019, Visual Studio Code 또는 원하는 편집기에서이 솔루션을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="55bf2-132">예제 코드 정리</span><span class="sxs-lookup"><span data-stu-id="55bf2-132">Clean up the example code</span></span>

<span data-ttu-id="55bf2-133">이제 이전 책에서 검토 한 gRPC 템플릿을 사용 하 여 예제 서비스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="55bf2-134">이는 재고 거래 컨텍스트에서 유용 하지 않으므로 첫 번째 프로젝트에 대 한 항목을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="55bf2-135">프로토콜 파일 이름 바꾸기 및 편집</span><span class="sxs-lookup"><span data-stu-id="55bf2-135">Rename and edit the proto file</span></span>

<span data-ttu-id="55bf2-136">계속 해 서 `Protos/greet.proto` 파일의 이름을 `Protos/portfolios.proto`로 바꾸고 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="55bf2-137">`package` 줄 이후의 모든 항목을 삭제 한 다음 `option csharp_namespace`, `package` 및 `service` 이름을 변경 하 고 기본 `SayHello` 서비스를 제거 합니다. 그러면 코드가 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="55bf2-138">템플릿은 기본적으로 `Protos` 네임 스페이스 파트를 추가 하지 않지만,이를 추가 하면 gRPC에서 생성 된 클래스와 사용자 고유의 클래스를 코드에서 명확 하 게 구분 하 여 쉽게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="55bf2-139">Visual Studio와 같은 IDE (통합 개발 환경)에서 `greet.proto` 파일의 이름을 바꾸면이 파일에 대 한 참조가 `.csproj` 파일에서 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="55bf2-140">그러나 Visual Studio Code와 같은 다른 편집기에서이 참조는 자동으로 업데이트 되지 않으므로 프로젝트 파일을 수동으로 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="55bf2-141">GRPC 빌드 대상에는 컴파일할 `.proto` 파일 및 필요한 코드 생성 형태 ("Server" 또는 "Client")를 지정할 수 있는 `Protobuf` item 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="55bf2-142">GreeterService 클래스 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="55bf2-142">Rename the GreeterService class</span></span>

<span data-ttu-id="55bf2-143">`GreeterService` 클래스는 `Services` 폴더에 있으며 `Greeter.GreeterBase`에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="55bf2-144">`PortfolioService`로 이름을 바꾸고 기본 클래스를 `Portfolios.PortfoliosBase`로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="55bf2-145">`override` 메서드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="55bf2-146">`Startup` 클래스의 `Configure` 메서드에 `GreeterService` 클래스에 대 한 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="55bf2-147">리팩터링을 사용 하 여 클래스의 이름을 바꾼 경우이 참조는 자동으로 업데이트 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="55bf2-148">그러나 그렇지 않은 경우 수동으로 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-148">However, if you didn't, you need to edit it manually.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="55bf2-149">다음 섹션에서는이 새 서비스에 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bf2-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="55bf2-150">[이전](migrate-wcf-to-grpc.md)
>[다음](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="55bf2-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
