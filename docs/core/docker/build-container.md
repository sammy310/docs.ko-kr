---
title: Docker를 사용하여 앱 컨테이너화 자습서
description: 이 자습서에서는 Docker를 사용하여 .NET Core 애플리케이션을 컨테이너화하는 방법을 알아봅니다.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c92f5823f56f74941afdd28638d30e759b2c51c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740758"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="234be-103">자습서: .NET Core 앱 컨테이너화</span><span class="sxs-lookup"><span data-stu-id="234be-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="234be-104">이 자습서에서는 Docker를 사용하여 .NET Core 애플리케이션을 컨테이너화하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="234be-104">In this tutorial, you'll learn how to containerize a .NET Core application with Docker.</span></span> <span data-ttu-id="234be-105">컨테이너에는 변경할 수 없는 인프라를 제공하고, 이식 가능한 아키텍처를 제공하고, 확장성을 사용하는 등의 많은 기능과 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-105">Containers have many features and benefits, such as being an immutable infrastructure, providing a portable architecture, and enabling scalability.</span></span> <span data-ttu-id="234be-106">이미지를 사용하여 로컬 개발 환경이나 프라이빗 클라우드 또는 퍼블릭 클라우드용 컨테이너를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-106">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="234be-107">이 자습서에서는 다음과 같은 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-107">In this tutorial, you:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="234be-108">간단한 .NET Core 앱 만들기 및 게시</span><span class="sxs-lookup"><span data-stu-id="234be-108">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="234be-109">.NET Core용 Dockerfile 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="234be-109">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="234be-110">Docker 이미지 빌드</span><span class="sxs-lookup"><span data-stu-id="234be-110">Build a Docker image</span></span>
> - <span data-ttu-id="234be-111">Docker 컨테이너 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="234be-111">Create and run a Docker container</span></span>

<span data-ttu-id="234be-112">.NET Core 애플리케이션용 Docker 컨테이너 빌드 및 배포 작업을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="234be-112">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="234be-113">Docker 플랫폼은 Docker 엔진을 사용하여 Docker 이미지로 앱을 신속하게 빌드하고 패키지합니다.   </span><span class="sxs-lookup"><span data-stu-id="234be-113">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="234be-114">이 이미지는 계층화된 컨테이너에서 배포되고 실행되도록 *Dockerfile* 형식으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-114">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!NOTE]
> <span data-ttu-id="234be-115">이 자습서는 ASP.NET Core 앱에는 적합하지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="234be-115">This tutorial **is not** for ASP.NET Core apps.</span></span> <span data-ttu-id="234be-116">ASP.NET Core를 사용하는 경우 [ASP.NET Core 애플리케이션을 컨테이너화하는 방법 알아보기](/aspnet/core/host-and-deploy/docker/building-net-docker-images) 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="234be-116">If you're using ASP.NET Core, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="234be-117">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="234be-117">Prerequisites</span></span>

<span data-ttu-id="234be-118">다음 필수 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-118">Install the following prerequisites:</span></span>

- <span data-ttu-id="234be-119">[.NET Core 5.0 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="234be-119">[.NET Core 5.0 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="234be-120">.NET Core가 설치되어 있는 경우 `dotnet --info` 명령을 사용하여 사용 중인 SDK를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-120">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>
- [<span data-ttu-id="234be-121">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="234be-121">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)
- <span data-ttu-id="234be-122">*Dockerfile* 및 .NET Core 예제 앱의 임시 작업 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="234be-122">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="234be-123">이 자습서에서는 이름 *docker-working* 이 작업 폴더로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-123">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="234be-124">.NET Core 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="234be-124">Create .NET Core app</span></span>

<span data-ttu-id="234be-125">Docker 컨테이너가 실행되는 .NET Core 앱이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-125">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="234be-126">아직 없는 경우, 터미널을 열고 작업 폴더를 만든 후 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-126">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="234be-127">작업 폴더에서 다음 명령을 실행하여 *app* 이라는 하위 디렉터리에서 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234be-127">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

<span data-ttu-id="234be-128">폴더 트리는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="234be-128">Your folder tree will look like the following:</span></span>

```
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
```

<span data-ttu-id="234be-129">`dotnet new` 명령은 *App* 이라는 새 폴더를 만들고 “Hello World” 콘솔 애플리케이션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-129">The `dotnet new` command creates a new folder named *App* and generates a "Hello World" console application.</span></span> <span data-ttu-id="234be-130">디렉터리를 변경하고 터미널 세션에서 *App* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-130">Change directories and navigate into the *App* folder, from your terminal session.</span></span> <span data-ttu-id="234be-131">`dotnet run` 명령을 사용하여 앱을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-131">Use the `dotnet run` command to start the app.</span></span> <span data-ttu-id="234be-132">애플리케이션이 실행되고 명령 아래에 `Hello World!`를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-132">The application will run, and print `Hello World!` below the command:</span></span>

```dotnetcli
dotnet run
Hello World!
```

<span data-ttu-id="234be-133">기본 템플릿은 터미널에 출력한 후 종료되는 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234be-133">The default template creates an app that prints to the terminal and then immediately terminates.</span></span> <span data-ttu-id="234be-134">이 자습서에서는 무한 반복되는 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="234be-135">텍스트 편집기에서 *Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="234be-135">Open the *Program.cs* file in a text editor.</span></span>

> [!TIP]
> <span data-ttu-id="234be-136">Visual Studio Code를 사용하는 경우 이전 터미널 세션에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-136">If you're using Visual Studio Code, from the previous terminal session type the following command:</span></span>
>
> ```console
> code .
> ```
>
> <span data-ttu-id="234be-137">이렇게 하면 Visual Studio Code에서 프로젝트가 포함된 *App* 폴더가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="234be-137">This will open the *App* folder that contains the project in Visual Studio Code.</span></span>

<span data-ttu-id="234be-138">*Program.cs* 는 다음 C# 코드와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-138">The *Program.cs* should look like the following C# code:</span></span>

```csharp
using System;

namespace NetCore.Docker
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="234be-139">1초마다 숫자를 계산하는 다음 코드로 파일을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="234be-139">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace NetCore.Docker
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                Console.WriteLine($"Counter: {++counter}");
                await Task.Delay(1000);
            }
        }
    }
}
```

<span data-ttu-id="234be-140">파일을 저장하고 `dotnet run`을 사용하여 프로그램을 다시 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-140">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="234be-141">이 앱은 무한 실행된다는 점을 명심하세요.</span><span class="sxs-lookup"><span data-stu-id="234be-141">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="234be-142">취소 명령 <kbd>CTRL+C</kbd>를 사용하여 앱을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-142">Use the cancel command <kbd>Ctrl+C</kbd> to stop it.</span></span> <span data-ttu-id="234be-143">다음은 출력 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="234be-143">The following is an example output:</span></span>

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="234be-144">명령줄의 숫자를 앱에 전달하면 해당 양까지만 계산되고 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-144">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="234be-145">앱에서 `dotnet run -- 5`를 사용하여 5까지 계산해 보세요.</span><span class="sxs-lookup"><span data-stu-id="234be-145">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="234be-146">`--` 이후 매개 변수는 `dotnet run` 명령에 전달되지 않고 대신 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-146">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="234be-147">.NET Core 앱 게시</span><span class="sxs-lookup"><span data-stu-id="234be-147">Publish .NET Core app</span></span>

<span data-ttu-id="234be-148">Docker 이미지에 .NET Core 앱을 추가하기 전에 먼저 앱을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-148">Before adding the .NET Core app to the Docker image, first it must be published.</span></span> <span data-ttu-id="234be-149">게시된 버전의 앱을 컨테이너에서 실행하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-149">It is best to have the container run the published version of the app.</span></span> <span data-ttu-id="234be-150">앱을 게시하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-150">To publish the app, run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="234be-151">이 명령은 앱을 *publish* 폴더로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-151">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="234be-152">작업 폴더에서 *publish* 폴더의 경로는 `.\App\bin\Release\net5.0\publish\`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-152">The path to the *publish* folder from the working folder should be `.\App\bin\Release\net5.0\publish\`</span></span>

#### <a name="windows"></a>[<span data-ttu-id="234be-153">Windows</span><span class="sxs-lookup"><span data-stu-id="234be-153">Windows</span></span>](#tab/windows)

<span data-ttu-id="234be-154">*App* 폴더에서 publish 폴더의 디렉터리 목록을 가져오고 *NetCore.Docker.dll* 파일이 생성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-154">From the *App* folder, get a directory listing of the publish folder to verify that the *NetCore.Docker.dll* file was created.</span></span>

```powershell
dir .\bin\Release\net5.0\publish\

    Directory: C:\Users\dapine\App\bin\Release\net5.0\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[<span data-ttu-id="234be-155">Linux</span><span class="sxs-lookup"><span data-stu-id="234be-155">Linux</span></span>](#tab/linux)

<span data-ttu-id="234be-156">`ls` 명령을 사용하여 디렉터리 목록을 가져오고 *NetCore.Docker.dll* 파일이 생성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-156">Use the `ls` command to get a directory listing and verify that the *NetCore.Docker.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/net5.0/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a><span data-ttu-id="234be-157">Dockerfile 만들기</span><span class="sxs-lookup"><span data-stu-id="234be-157">Create the Dockerfile</span></span>

<span data-ttu-id="234be-158">*Dockerfile* 파일은 `docker build` 명령에서 컨테이너 이미지를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-158">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="234be-159">이 파일은 확장명이 없는 *Dockerfile* 이라는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="234be-159">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="234be-160">*.csproj* 를 포함하는 디렉터리에 *Dockerfile* 이라는 파일을 만들고 텍스트 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="234be-160">Create a file named *Dockerfile* in directory containing the *.csproj* and open it in a text editor.</span></span> <span data-ttu-id="234be-161">이 자습서에서는 .NET Core 런타임 이미지를 포함하고 .NET Core 콘솔 애플리케이션과 일치하는 ASP.NET Core 런타임 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-161">This tutorial will use the ASP.NET Core runtime image (which contains the .NET Core runtime image) and corresponds with the .NET Core console application.</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:5.0
```

> [!NOTE]
> <span data-ttu-id="234be-162">`mcr.microsoft.com/dotnet/runtime:5.0` 이미지를 사용할 수 있지만 여기서는 의도적으로 ASP.NET Core 런타임 이미지가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-162">The ASP.NET Core runtime image is used intentionally here, although the `mcr.microsoft.com/dotnet/runtime:5.0` image could have been used.</span></span>

<span data-ttu-id="234be-163">`FROM` 키워드에는 정규화된 Docker 컨테이너 이미지 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-163">The `FROM` keyword requires a fully qualified Docker container image name.</span></span> <span data-ttu-id="234be-164">MCR(Microsoft Container Registry, mcr.microsoft.com)은 공개적으로 액세스할 수 있는 컨테이너를 호스트하는 Docker 허브의 신디케이트입니다.</span><span class="sxs-lookup"><span data-stu-id="234be-164">The Microsoft Container Registry (MCR, mcr.microsoft.com) is a syndicate of Docker Hub - which hosts publicly accessible containers.</span></span> <span data-ttu-id="234be-165">`dotnet/core` 세그먼트는 컨테이너 리포지토리입니다. 여기서 `aspnet` 세그먼트는 컨테이너 이미지 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="234be-165">The `dotnet/core` segment is the container repository, where as the `aspnet` segment is the container image name.</span></span> <span data-ttu-id="234be-166">이미지에는 버전 관리에 사용되는 `5.0`태그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-166">The image is tagged with `5.0`, which is used for versioning.</span></span> <span data-ttu-id="234be-167">따라서 `mcr.microsoft.com/dotnet/aspnet:5.0`은 .NET Core 5.0 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="234be-167">Thus, `mcr.microsoft.com/dotnet/aspnet:5.0` is the .NET Core 5.0 runtime.</span></span> <span data-ttu-id="234be-168">SDK에서 대상으로 지정된 런타임과 일치하는 런타임 버전을 풀해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-168">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="234be-169">예를 들어 이전 섹션에서 만든 앱은 .NET Core 5.0 SDK를 사용하고 *Dockerfile* 에서 참조하는 기본 이미지에 **5.0** 태그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-169">For example, the app created in the previous section used the .NET Core 5.0 SDK and the base image referred to in the *Dockerfile* is tagged with **5.0**.</span></span>

<span data-ttu-id="234be-170">*Dockerfile* 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-170">Save the *Dockerfile* file.</span></span> <span data-ttu-id="234be-171">작업 폴더의 디렉터리 구조는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-171">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="234be-172">문서에서 공간을 절약하기 위해 더 깊은 수준의 파일과 폴더의 일부가 생략되었습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-172">Some of the deeper-level files and folders have been omitted to save space in the article:</span></span>

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──net5.0
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

<span data-ttu-id="234be-173">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-173">From your terminal, run the following command:</span></span>

```console
docker build -t counter-image -f Dockerfile .
```

<span data-ttu-id="234be-174">Docker가 *Dockerfile* 에서 각 줄을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-174">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="234be-175">`docker build` 명령의 `.`는 *Dockerfile* 을 찾는 데 현재 폴더를 사용하도록 Docker에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-175">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="234be-176">이 명령은 이미지를 빌드하고 해당 이미지를 가리키는 **counter-image** 라는 로컬 리포지토리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234be-176">This command builds the image and creates a local repository named **counter-image** that points to that image.</span></span> <span data-ttu-id="234be-177">이 명령이 완료된 후 `docker images`를 실행하여 설치된 이미지 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-177">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/aspnet         5.0                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="234be-178">두 이미지가 동일한 **IMAGE ID** 값을 공유함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-178">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="234be-179">*Dockerfile* 의 유일한 명령은 기존 이미지를 기반으로 새 이미지를 만드는 것이므로 두 이미지에서 해당 값이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-179">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="234be-180">*Dockerfile* 에 세 개의 명령을 추가하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-180">Let's add three commands to the *Dockerfile*.</span></span> <span data-ttu-id="234be-181">각 명령은 **counter-image** 리포지토리 진입점을 나타내는 마지막 명령으로 새 이미지 계층을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234be-181">Each command creates a new image layer with the final command representing the **counter-image** repository entry points to.</span></span>

```dockerfile
COPY bin/Release/net5.0/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

<span data-ttu-id="234be-182">`COPY` 명령은 컴퓨터의 지정된 폴더를 컨테이너의 폴더에 복사하도록 Docker에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-182">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="234be-183">이 예제에서 *publish* 폴더는 컨테이너의 *App* 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-183">In this example, the *publish* folder is copied to a folder named *App* in the container.</span></span>

<span data-ttu-id="234be-184">`WORKDIR` 명령은 컨테이너 내부의 **현재 디렉터리** 를 *App* 으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-184">The `WORKDIR` command changes the **current directory** inside of the container to *App*.</span></span>

<span data-ttu-id="234be-185">다음 명령인 `ENTRYPOINT`는 컨테이너가 실행 파일로 실행되게 컨테이너를 구성하도록 Docker에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-185">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="234be-186">컨테이너가 시작되면 `ENTRYPOINT` 명령이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-186">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="234be-187">이 명령이 종료되면 컨테이너가 자동으로 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-187">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="234be-188">터미널에서 `docker build -t counter-image -f Dockerfile .`를 실행하고 명령이 완료되면 `docker images`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-188">From your terminal, run `docker build -t counter-image -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/aspnet:5.0
 ---> e6780479db63
Step 2/4 : COPY bin/Release/net5.0/publish/ App/
 ---> d1732740eed2
Step 3/4 : WORKDIR /App
 ---> Running in b1701a42f3ff
Removing intermediate container b1701a42f3ff
 ---> 919aab5b95e3
Step 4/4 : ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
 ---> Running in c12aebd26ced
Removing intermediate container c12aebd26ced
 ---> cd11c3df9b19
Successfully built cd11c3df9b19
Successfully tagged counter-image:latest

docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              cd11c3df9b19        41 seconds ago      190MB
mcr.microsoft.com/dotnet/aspnet         5.0                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="234be-189">*Dockerfile* 의 각 명령이 계층을 생성하고 **IMAGE ID** 를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-189">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="234be-190">마지막 **IMAGE ID**(사용자에 따라 다름)는 **cd11c3df9b19** 이고 다음에 이 이미지를 기반으로 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234be-190">The final **IMAGE ID** (yours will be different) is **cd11c3df9b19** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="234be-191">컨테이너 만들기</span><span class="sxs-lookup"><span data-stu-id="234be-191">Create a container</span></span>

<span data-ttu-id="234be-192">이제 앱을 포함하는 이미지가 있으므로 컨테이너를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-192">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="234be-193">두 가지 방법으로 컨테이너를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-193">You can create a container in two ways.</span></span> <span data-ttu-id="234be-194">먼저 중지된 새 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234be-194">First, create a new container that is stopped.</span></span>

```console
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

<span data-ttu-id="234be-195">위에서 `docker create` 명령은 **counter-image** 이미지를 기반으로 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="234be-195">The `docker create` command from above will create a container based on the **counter-image** image.</span></span> <span data-ttu-id="234be-196">해당 명령의 출력은 생성된 컨테이너의 **CONTAINER ID**(사용자에 따라 다름)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-196">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="234be-197">모든 컨테이너 목록을 보려면 `docker ps -a` 명령을 사용합니다. </span><span class="sxs-lookup"><span data-stu-id="234be-197">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a><span data-ttu-id="234be-198">컨테이너 관리</span><span class="sxs-lookup"><span data-stu-id="234be-198">Manage the container</span></span>

<span data-ttu-id="234be-199">컨테이너는 특정 이름 `core-counter`를 사용하여 만들어졌으며, 이 이름은 컨테이너를 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-199">The container was created with a specific name `core-counter`, this name is used to manage the container.</span></span> <span data-ttu-id="234be-200">다음 예제에서는 `docker start` 명령을 사용하여 컨테이너를 시작한 후 `docker ps` 명령을 사용하여 실행 중인 컨테이너만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-200">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

<span data-ttu-id="234be-201">마찬가지로 `docker stop` 명령은 컨테이너를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-201">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="234be-202">다음 예제에서는 `docker stop` 명령을 사용하여 컨테이너를 중지한 다음, `docker ps` 명령을 사용하여 컨테이너가 실행 중이지 않음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="234be-202">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="234be-203">컨테이너에 연결</span><span class="sxs-lookup"><span data-stu-id="234be-203">Connect to a container</span></span>

<span data-ttu-id="234be-204">컨테이너가 실행된 후 컨테이너에 연결하여 출력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-204">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="234be-205">`docker start` 및 `docker attach` 명령을 사용하여 컨테이너를 시작하고 출력 스트림을 피킹합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-205">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="234be-206">이 예제에서는 <kbd>Ctrl+C</kbd> 키 입력을 사용하여 실행 중인 컨테이너에서 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-206">In this example, the <kbd>Ctrl+C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="234be-207">별도로 지정하지 않는 한 이 키 입력은 컨테이너에서 프로세스를 종료하여 컨테이너를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-207">This keystroke will end the process in the container unless otherwise specified, which would stop the container.</span></span> <span data-ttu-id="234be-208">`--sig-proxy=false` 매개 변수를 사용하면 <kbd>Ctrl+C</kbd>가 컨테이너에서 프로세스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-208">The `--sig-proxy=false` parameter ensures that <kbd>Ctrl+C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="234be-209">컨테이너에서 분리한 후 다시 연결하여 계속 실행 및 계산 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-209">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
docker start core-counter
core-counter

docker attach --sig-proxy=false core-counter
Counter: 7
Counter: 8
Counter: 9
^C

docker attach --sig-proxy=false core-counter
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="234be-210">컨테이너 삭제</span><span class="sxs-lookup"><span data-stu-id="234be-210">Delete a container</span></span>

<span data-ttu-id="234be-211">이 문서의 목적이 아무 작업도 수행하지 않는 컨테이너를 만드는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="234be-211">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="234be-212">이전에 만든 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-212">Delete the container you previously created.</span></span> <span data-ttu-id="234be-213">컨테이너가 실행 중이면 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-213">If the container is running, stop it.</span></span>

```console
docker stop core-counter
```

<span data-ttu-id="234be-214">다음 예제에는 모든 컨테이너가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-214">The following example lists all containers.</span></span> <span data-ttu-id="234be-215">`docker rm` 명령을 사용하여 컨테이너를 삭제한 후 실행 중인 컨테이너가 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-215">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="234be-216">단일 실행</span><span class="sxs-lookup"><span data-stu-id="234be-216">Single run</span></span>

<span data-ttu-id="234be-217">Docker는 단일 명령으로 컨테이너를 만들고 실행할 수 있는 `docker run` 명령을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-217">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="234be-218">이 명령을 사용하면 `docker create`를 실행한 후 `docker start`를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-218">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="234be-219">컨테이너가 중지될 때 컨테이너를 자동으로 삭제하도록 이 명령을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-219">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="234be-220">예를 들어 `docker run -it --rm`을 사용하여 두 가지 작업을 수행합니다. 먼저 현재 터미널을 사용하여 컨테이너에 연결한 후 컨테이너가 완료되면 컨테이너를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-220">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="234be-221">또한 컨테이너는 .NET Core 앱의 실행에 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-221">The container also passes parameters into the execution of the .NET Core app.</span></span> <span data-ttu-id="234be-222">.NET Core 앱에 3까지만 계산하도록 지시하려면 3을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-222">To instruct the .NET Core app to count only to 3 pass in 3.</span></span>

```console
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

<span data-ttu-id="234be-223">`docker run -it`를 사용하면 <kbd>Ctrl+C</kbd> 명령이 컨테이너에서 실행 중인 프로세스를 중지하고, 이에 따라 컨테이너가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-223">With `docker run -it`, the <kbd>Ctrl+C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="234be-224">`--rm` 매개 변수가 제공되었으므로 프로세스가 중지되면 컨테이너가 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-224">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="234be-225">컨테이너가 존재하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-225">Verify that it doesn't exist:</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="234be-226">ENTRYPOINT 변경</span><span class="sxs-lookup"><span data-stu-id="234be-226">Change the ENTRYPOINT</span></span>

<span data-ttu-id="234be-227">`docker run` 명령을 사용하면 *Dockerfile* 에서 `ENTRYPOINT` 명령을 수정하고 해당 컨테이너에만 해당하는 다른 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-227">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="234be-228">예를 들어 다음 명령을 사용하여 `bash` 또는 `cmd.exe`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-228">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="234be-229">필요에 따라 명령을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-229">Edit the command as necessary.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="234be-230">Windows</span><span class="sxs-lookup"><span data-stu-id="234be-230">Windows</span></span>](#tab/windows)

<span data-ttu-id="234be-231">이 예제에서 `ENTRYPOINT`는 `cmd.exe`로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-231">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="234be-232"><kbd>Ctrl+C</kbd>를 눌러 프로세스를 종료하고 컨테이너를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-232"><kbd>Ctrl+C</kbd> is pressed to end the process and stop the container.</span></span>

```console
docker run -it --rm --entrypoint "cmd.exe" counter-image

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>[<span data-ttu-id="234be-233">Linux</span><span class="sxs-lookup"><span data-stu-id="234be-233">Linux</span></span>](#tab/linux)

<span data-ttu-id="234be-234">이 예제에서 `ENTRYPOINT`는 `bash`로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-234">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="234be-235">`exit` 명령이 실행되면 프로세스가 종료되고 컨테이너가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="234be-235">The `exit` command is run which ends the process and stop the container.</span></span>

```bash
docker run -it --rm --entrypoint "bash" counter-image
root@b735b9799abf:/App# ls
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.exe  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
root@b735b9799abf:/App# dotnet NetCore.Docker.dll 3
Counter: 1
Counter: 2
Counter: 3
root@b735b9799abf:/App# exit
exit
```

---

## <a name="essential-commands"></a><span data-ttu-id="234be-236">필수 명령</span><span class="sxs-lookup"><span data-stu-id="234be-236">Essential commands</span></span>

<span data-ttu-id="234be-237">Docker에는 컨테이너와 이미지를 만들고, 관리하며, 이와 상호 작용하는 다양한 명령이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-237">Docker has many different commands that create, manage, and interact with containers and images.</span></span> <span data-ttu-id="234be-238">이 Docker 명령은 컨테이너 관리에 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="234be-238">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="234be-239">docker build</span><span class="sxs-lookup"><span data-stu-id="234be-239">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="234be-240">docker run</span><span class="sxs-lookup"><span data-stu-id="234be-240">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="234be-241">docker ps</span><span class="sxs-lookup"><span data-stu-id="234be-241">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="234be-242">docker stop</span><span class="sxs-lookup"><span data-stu-id="234be-242">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="234be-243">docker rm</span><span class="sxs-lookup"><span data-stu-id="234be-243">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="234be-244">docker rmi</span><span class="sxs-lookup"><span data-stu-id="234be-244">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="234be-245">docker image</span><span class="sxs-lookup"><span data-stu-id="234be-245">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="234be-246">리소스 정리</span><span class="sxs-lookup"><span data-stu-id="234be-246">Clean up resources</span></span>

<span data-ttu-id="234be-247">이 자습서에서는 컨테이너 및 이미지를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-247">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="234be-248">원하는 경우 이 리소스를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-248">If you want, delete these resources.</span></span> <span data-ttu-id="234be-249">다음 명령을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-249">Use the following commands to</span></span>

01. <span data-ttu-id="234be-250">모든 컨테이너 나열</span><span class="sxs-lookup"><span data-stu-id="234be-250">List all containers</span></span>

    ```console
    docker ps -a
    ```

02. <span data-ttu-id="234be-251">이름으로 실행 중인 컨테이너를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-251">Stop containers that are running by their name.</span></span>

    ```console
    docker stop counter-image
    ```

03. <span data-ttu-id="234be-252">컨테이너 삭제</span><span class="sxs-lookup"><span data-stu-id="234be-252">Delete the container</span></span>

    ```console
    docker rm counter-image
    ```

<span data-ttu-id="234be-253">그런 다음, 머신에서 더 이상 사용하지 않을 이미지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-253">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="234be-254">*Dockerfile* 에서 만든 이미지를 삭제한 후 *Dockerfile* 이 기반으로 하는 .NET Core 이미지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-254">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="234be-255">**IMAGE ID** 또는 **REPOSITORY:TAG** 형식 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-255">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/aspnet:5.0
```

<span data-ttu-id="234be-256">`docker images` 명령을 사용하여 설치된 이미지 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-256">Use the `docker images` command to see a list of images installed.</span></span>

> [!TIP]
> <span data-ttu-id="234be-257">이미지 파일이 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234be-257">Image files can be large.</span></span> <span data-ttu-id="234be-258">일반적으로 앱을 테스트하고 개발하는 동안 만든 임시 컨테이너를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-258">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="234be-259">일반적으로 해당 런타임을 기반으로 다른 이미지를 빌드할 계획인 경우에는 설치된 런타임과 함께 기본 이미지를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="234be-259">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="234be-260">다음 단계</span><span class="sxs-lookup"><span data-stu-id="234be-260">Next steps</span></span>

- [<span data-ttu-id="234be-261">ASP.NET Core 애플리케이션을 컨테이너화하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="234be-261">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="234be-262">ASP.NET Core 마이크로 서비스 자습서 확인 보기</span><span class="sxs-lookup"><span data-stu-id="234be-262">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="234be-263">컨테이너를 지원하는 Azure 서비스 검토</span><span class="sxs-lookup"><span data-stu-id="234be-263">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="234be-264">Dockerfile 명령에 대해 읽어 보기</span><span class="sxs-lookup"><span data-stu-id="234be-264">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="234be-265">Visual studio용 컨테이너 도구 살펴보기</span><span class="sxs-lookup"><span data-stu-id="234be-265">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
