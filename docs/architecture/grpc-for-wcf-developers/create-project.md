---
title: WCF 개발자를 위한 새 ASP.NET Core gRPC 프로젝트 gRPC 만들기
description: Visual Studio 또는 명령줄을 사용 하 여 gRPC 프로젝트를 만드는 방법에 대해 알아봅니다.
ms.date: 09/02/2019
ms.openlocfilehash: fbcc598cf503a5baeca941803ff8fa0d5fc99671
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919406"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="34347-103">새 ASP.NET Core gRPC 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="34347-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="34347-104">.NET Core SDK는 명령줄에서 프로젝트와 솔루션을 만들고 관리할 수 있는 강력한 CLI 도구인 `dotnet`와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34347-104">The .NET Core SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="34347-105">SDK는 Visual Studio와 긴밀 하 게 통합 되므로 친숙 한 그래픽 사용자 인터페이스를 통해서도 모든 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="34347-106">이 장에서는 새 ASP.NET Core gRPC 프로젝트를 만드는 두 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34347-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="34347-107">Visual Studio를 사용 하 여 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="34347-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34347-108">ASP.NET Core 3.0 앱을 개발 하려면 **ASP.NET 및 웹 개발** 워크 로드가 설치 된 Visual Studio 2019 버전 16.3 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019 version 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="34347-109">*빈 솔루션* 템플릿에서 **TraderSys** 라는 빈 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34347-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="34347-110">`src`이라는 솔루션 폴더를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="34347-111">그런 다음 폴더를 마우스 오른쪽 단추로 클릭 하 고 **추가** > **새 프로젝트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="34347-112">템플릿 검색 상자에 `grpc`를 입력 하면 `gRPC Service`라는 프로젝트 템플릿이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34347-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![새 프로젝트 추가 대화 상자 스크린샷](media/create-project/new-grpc-project.png)

<span data-ttu-id="34347-114">**다음** 을 선택 하 여 **새 프로젝트 구성** 대화 상자를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="34347-115">프로젝트 이름을 `TraderSys.Portfolios` 하 고 **위치**에 `src` 하위 디렉터리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-115">Name the project `TraderSys.Portfolios` and add an `src` subdirectory to the **Location**.</span></span>

![새 프로젝트 구성 대화 상자 스크린샷](media/create-project/configure-project.png)

<span data-ttu-id="34347-117">**다음** 을 선택 하 여 **새 grpc 서비스 만들기** 대화 상자를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![새 gRPC 서비스 만들기 대화 상자 스크린샷](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="34347-119">현재는 서비스 만들기에 대 한 옵션이 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="34347-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="34347-120">Docker는 나중에 도입 되므로 지금은이 옵션을 선택 하지 않은 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="34347-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="34347-121">**만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-121">Just select **Create**.</span></span> <span data-ttu-id="34347-122">첫 번째 ASP.NET Core 3.0 gRPC 프로젝트가 생성 되어 솔루션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34347-122">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="34347-123">`dotnet CLI`를 사용 하는 방법을 모르는 경우 [예제 코드 섹션 정리](#clean-up-the-example-code) 로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="34347-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-core-cli"></a><span data-ttu-id="34347-124">.NET Core CLI를 사용 하 여 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34347-124">Create the project by using the .NET Core CLI</span></span>

<span data-ttu-id="34347-125">이 섹션에서는 명령줄에서 솔루션 및 프로젝트를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="34347-126">다음 명령에 표시 된 대로 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34347-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="34347-127">`-o` (또는 `--output`) 플래그는 현재 디렉터리에 생성 되는 출력 디렉터리를 지정 합니다 (이미 존재 하지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="34347-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="34347-128">솔루션의 이름은 `TraderSys.sln`디렉터리와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="34347-129">`-n` (또는 `--name`) 플래그를 사용 하 여 다른 이름을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="34347-130">ASP.NET Core 3.0는 gRPC 서비스용 CLI 템플릿과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34347-130">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="34347-131">이 템플릿을 사용 하 여 새 프로젝트를 만듭니다 .이 템플릿을 사용 하 여 ASP.NET Core 프로젝트에 대 한 기본으로 `src` 하위 디렉터리에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="34347-132">`-n` 플래그를 사용 하 여 다른 이름을 지정 하지 않은 경우 프로젝트 이름은 디렉터리 (`TraderSys.Portfolios.csproj`) 뒤에 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34347-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="34347-133">마지막으로 `dotnet sln` 명령을 사용 하 여 솔루션에 프로젝트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="34347-134">특정 디렉터리에는 단일 `.csproj` 파일만 포함 되어 있으므로, 디렉터리만 지정 하 여 입력을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="34347-135">이제 Visual Studio 2019, Visual Studio Code 또는 원하는 편집기에서이 솔루션을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="34347-136">예제 코드 정리</span><span class="sxs-lookup"><span data-stu-id="34347-136">Clean up the example code</span></span>

<span data-ttu-id="34347-137">이제 이전 책에서 검토 한 gRPC 템플릿을 사용 하 여 예제 서비스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="34347-138">이는 재고 거래 컨텍스트에서 유용 하지 않으므로 첫 번째 프로젝트에 대 한 항목을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-138">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="34347-139">프로토콜 파일 이름 바꾸기 및 편집</span><span class="sxs-lookup"><span data-stu-id="34347-139">Rename and edit the proto file</span></span>

<span data-ttu-id="34347-140">계속 해 서 `Protos/greet.proto` 파일의 이름을 `Protos/portfolios.proto`로 바꾸고 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="34347-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="34347-141">`package` 줄 뒤에 나오는 모든 항목을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="34347-142">그런 다음 `option csharp_namespace`, `package` 및 `service` 이름을 변경 하 고 기본 `SayHello` 서비스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="34347-143">이제 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="34347-144">템플릿은 기본적으로 `Protos` 네임 스페이스 파트를 추가 하지 않지만,이를 추가 하면 gRPC에서 생성 된 클래스와 사용자 고유의 클래스를 코드에서 명확 하 게 구분 하 여 쉽게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="34347-145">Visual Studio와 같은 IDE (통합 개발 환경)에서 `greet.proto` 파일의 이름을 바꾸면이 파일에 대 한 참조가 `.csproj` 파일에서 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34347-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="34347-146">그러나 Visual Studio Code와 같은 다른 편집기에서이 참조는 자동으로 업데이트 되지 않으므로 프로젝트 파일을 수동으로 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="34347-147">GRPC 빌드 대상에는 컴파일할 `.proto` 파일 및 필요한 코드 생성 형태 ("Server" 또는 "Client")를 지정할 수 있는 `Protobuf` item 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="34347-148">`GreeterService` 클래스 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="34347-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="34347-149">`GreeterService` 클래스는 `Services` 폴더에 있으며 `Greeter.GreeterBase`에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34347-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="34347-150">`PortfolioService`로 이름을 바꾸고 기본 클래스를 `Portfolios.PortfoliosBase`변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="34347-151">`override` 메서드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="34347-152">`Startup` 클래스의 `Configure` 메서드에 `GreeterService` 클래스에 대 한 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34347-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="34347-153">리팩터링을 사용 하 여 클래스의 이름을 바꾼 경우이 참조는 자동으로 업데이트 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="34347-154">그러나 그렇지 않은 경우 수동으로 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="34347-155">다음 섹션에서는이 새 서비스에 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="34347-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="34347-156">[이전](migrate-wcf-to-grpc.md)
>[다음](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="34347-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
