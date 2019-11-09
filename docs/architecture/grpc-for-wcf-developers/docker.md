---
title: WCF 개발자를 위한 Docker gRPC
description: ASP.NET Core gRPC 응용 프로그램에 대 한 Docker 이미지 만들기
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: cc369da9494ade532187dfc8d19a94a3a037ebab
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841656"
---
# <a name="docker"></a><span data-ttu-id="bfce3-103">Docker</span><span class="sxs-lookup"><span data-stu-id="bfce3-103">Docker</span></span>

<span data-ttu-id="bfce3-104">이 섹션에서는 ASP.NET Core gRPC 응용 프로그램에 대 한 Docker 이미지 생성, Docker, Kubernetes 또는 기타 컨테이너 환경에서 실행할 준비를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-104">This section will cover the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="bfce3-105">ASP.NET Core MVC 웹 앱 및 gRPC 서비스를 사용 하 여 사용 되는 샘플 응용 프로그램은 GitHub의 [dotnet-아키텍처/grpc-wcf-개발자](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) 리포지토리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="bfce3-106">ASP.NET Core 응용 프로그램용 Microsoft 기본 이미지</span><span class="sxs-lookup"><span data-stu-id="bfce3-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="bfce3-107">Microsoft는 .NET Core 응용 프로그램 빌드 및 실행을 위한 다양 한 기본 이미지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="bfce3-108">ASP.NET Core 3.0 이미지를 만들기 위해 응용 프로그램을 빌드 및 게시 하기 위한 SDK 이미지와 배포용 런타임 이미지 라는 두 개의 기본 이미지가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-108">To create an ASP.NET Core 3.0 image, two base images are used: an SDK image to build and publish the application, and a runtime image for deployment.</span></span>

| <span data-ttu-id="bfce3-109">이미지</span><span class="sxs-lookup"><span data-stu-id="bfce3-109">Image</span></span> | <span data-ttu-id="bfce3-110">설명</span><span class="sxs-lookup"><span data-stu-id="bfce3-110">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="bfce3-111">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="bfce3-111">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="bfce3-112">`docker build`를 사용 하 여 응용 프로그램을 빌드하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-112">For building applications with `docker build`.</span></span> <span data-ttu-id="bfce3-113">프로덕션에서는 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-113">Not to be used in production.</span></span> |
| [<span data-ttu-id="bfce3-114">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="bfce3-114">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="bfce3-115">런타임 및 ASP.NET Core 종속성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-115">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="bfce3-116">프로덕션의 경우.</span><span class="sxs-lookup"><span data-stu-id="bfce3-116">For production.</span></span> |

<span data-ttu-id="bfce3-117">각 이미지에는 다른 Linux 배포판을 기반으로 하는 네 가지 변형이 있습니다 (태그로 구분).</span><span class="sxs-lookup"><span data-stu-id="bfce3-117">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="bfce3-118">이미지 태그</span><span class="sxs-lookup"><span data-stu-id="bfce3-118">Image tag(s)</span></span> | <span data-ttu-id="bfce3-119">Linux</span><span class="sxs-lookup"><span data-stu-id="bfce3-119">Linux</span></span> | <span data-ttu-id="bfce3-120">노트</span><span class="sxs-lookup"><span data-stu-id="bfce3-120">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="bfce3-121">3.0-buster, 3.0</span><span class="sxs-lookup"><span data-stu-id="bfce3-121">3.0-buster, 3.0</span></span> | <span data-ttu-id="bfce3-122">Debian 10</span><span class="sxs-lookup"><span data-stu-id="bfce3-122">Debian 10</span></span> | <span data-ttu-id="bfce3-123">OS 변형이 지정 되지 않은 경우 기본 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-123">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="bfce3-124">3.0-알파인</span><span class="sxs-lookup"><span data-stu-id="bfce3-124">3.0-alpine</span></span> | <span data-ttu-id="bfce3-125">알파인 3.9</span><span class="sxs-lookup"><span data-stu-id="bfce3-125">Alpine 3.9</span></span> | <span data-ttu-id="bfce3-126">알파인 기본 이미지는 Debian 또는 Ubuntu 1 보다 훨씬 작습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-126">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="bfce3-127">3.0-disco</span><span class="sxs-lookup"><span data-stu-id="bfce3-127">3.0-disco</span></span> | <span data-ttu-id="bfce3-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="bfce3-128">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="bfce3-129">3.0-bionic</span><span class="sxs-lookup"><span data-stu-id="bfce3-129">3.0-bionic</span></span> | <span data-ttu-id="bfce3-130">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="bfce3-130">Ubuntu 18.04</span></span> | |

<span data-ttu-id="bfce3-131">알파인 기본 이미지는 Debian 및 Ubuntu 이미지에 대 한 200 MB와 비교해 100 약 이지만 일부 소프트웨어 패키지 또는 라이브러리는 알파인의 패키지 관리에서 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images, but some software packages or libraries may not be available in Alpine's package management.</span></span> <span data-ttu-id="bfce3-132">사용할 이미지를 잘 모르는 경우 다른 배포판를 사용 해야 하는 경우를 제외 하 고 기본 Debian을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-132">If you're not sure which image to use, it's best to stick to the default Debian unless you have a compelling need to use a different distro.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfce3-133">빌드 및 런타임에 동일한 유형의 Linux를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-133">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="bfce3-134">하나의 변형에 빌드되고 게시 된 응용 프로그램은 다른 변형에서 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-134">Applications built and published on one variant may not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="bfce3-135">Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="bfce3-135">Create a Docker image</span></span>

<span data-ttu-id="bfce3-136">Docker 이미지는 응용 프로그램을 빌드하고 응용 프로그램을 빌드하고 실행 하는 데 필요한 모든 종속성을 설치 하는 데 필요한 모든 명령을 포함 하는 텍스트 파일인 *Dockerfile*에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-136">A Docker image is defined by a *Dockerfile*, a text file that contains all the commands that are needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="bfce3-137">다음 예제에서는 ASP.NET Core 3.0 응용 프로그램에 대 한 가장 간단한 Dockerfile을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-137">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="bfce3-138">Dockerfile에는 두 부분이 있습니다. 첫 번째는 `sdk` 기본 이미지를 사용 하 여 응용 프로그램을 빌드하고 게시 합니다. 두 번째는 `aspnet` 기반에서 런타임 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-138">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="bfce3-139">이는 `sdk` 이미지가 런타임 이미지에 대 한 약 200 MB와 비교 하 여 약 900이이 고, 런타임에 대부분의 콘텐츠는 필요 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-139">This is because the `sdk` image is around 900 MB compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="bfce3-140">빌드 단계</span><span class="sxs-lookup"><span data-stu-id="bfce3-140">The build steps</span></span>

| <span data-ttu-id="bfce3-141">단계</span><span class="sxs-lookup"><span data-stu-id="bfce3-141">Step</span></span> | <span data-ttu-id="bfce3-142">설명</span><span class="sxs-lookup"><span data-stu-id="bfce3-142">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="bfce3-143">기본 이미지를 선언 하 고 `builder` 별칭을 할당 합니다 (설명에 대해서는 다음 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="bfce3-143">Declares the base image and assigns the `builder` alias (see next section for explanation).</span></span> |
| `WORKDIR /src` | <span data-ttu-id="bfce3-144">`/src` 디렉터리를 만들고 현재 작업 디렉터리로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-144">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="bfce3-145">호스트의 현재 디렉터리 아래에 있는 모든 항목을 이미지의 현재 디렉터리에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-145">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="bfce3-146">외부 패키지를 복원 합니다 (ASP.NET Core 3.0 프레임 워크는 SDK와 함께 사전 설치 됨).</span><span class="sxs-lookup"><span data-stu-id="bfce3-146">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="bfce3-147">릴리스 빌드를 빌드하고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-147">Builds and publishes a Release build.</span></span> <span data-ttu-id="bfce3-148">`--runtime` 플래그는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-148">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="bfce3-149">런타임 이미지 단계</span><span class="sxs-lookup"><span data-stu-id="bfce3-149">The runtime image steps</span></span>

| <span data-ttu-id="bfce3-150">단계</span><span class="sxs-lookup"><span data-stu-id="bfce3-150">Step</span></span> | <span data-ttu-id="bfce3-151">설명</span><span class="sxs-lookup"><span data-stu-id="bfce3-151">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="bfce3-152">새 기본 이미지를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-152">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="bfce3-153">`/app` 디렉터리를 만들고 현재 작업 디렉터리로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-153">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="bfce3-154">첫 번째 `FROM` 줄의 `builder` 별칭을 사용 하 여 이전 이미지에서 게시 된 응용 프로그램을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-154">Copies the published application from the previous image, using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="bfce3-155">컨테이너가 시작 될 때 실행할 명령을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-155">Sets the command to run when the container starts.</span></span> <span data-ttu-id="bfce3-156">런타임 이미지의 `dotnet` 명령은 DLL 파일만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-156">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="bfce3-157">Docker의 HTTPS</span><span class="sxs-lookup"><span data-stu-id="bfce3-157">HTTPS in Docker</span></span>

<span data-ttu-id="bfce3-158">Docker 용 Microsoft의 기본 이미지는 `ASPNETCORE_URLS` 환경 변수를 `http://+:80`로 설정 합니다. 즉, Kestrel은 해당 포트에서 HTTPS 없이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-158">Microsoft's base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel will run without HTTPS on that port.</span></span> <span data-ttu-id="bfce3-159">[이전 섹션](self-hosted.md)에서 설명한 대로 사용자 지정 인증서와 함께 HTTPS를 사용 하는 경우 Dockerfile의 **런타임 이미지 생성 부분에** 환경 변수를 설정 하 여이를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-159">If you're using HTTPS with a custom certificate (as described in [the previous section](self-hosted.md)), you should override this by setting the environment variable **in the runtime image creation part** of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="bfce3-160">. Dockerignore 파일</span><span class="sxs-lookup"><span data-stu-id="bfce3-160">The .dockerignore file</span></span>

<span data-ttu-id="bfce3-161">특정 파일 및 디렉터리를 소스 제어에서 제외 하는 `.gitignore` 파일과 마찬가지로 `.dockerignore` 파일을 사용 하 여 파일 및 디렉터리를 빌드하는 동안 이미지에 복사 하지 않도록 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-161">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="bfce3-162">이렇게 하면 복사 시간이 절약 될 뿐만 아니라 PC에서 이미지에 복사 된 `obj` 디렉터리를 사용 하 여 발생 하는 혼동을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-162">This not only saves time copying, but can also avoid some confusing errors that arise from having (particularly) the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="bfce3-163">`bin`에 대 한 항목을 하나 이상 추가 하 고 `.dockerignore` 파일에 `obj` 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-163">You should add at least entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="bfce3-164">이미지 빌드</span><span class="sxs-lookup"><span data-stu-id="bfce3-164">Build the image</span></span>

<span data-ttu-id="bfce3-165">단일 응용 프로그램, 즉 단일 Dockerfile이 있는 솔루션의 경우 Dockerfile을 기본 디렉터리에 배치 하는 것이 가장 간단 합니다. 즉, `.sln` 파일과 동일한 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-165">For a solution with a single application, and thus a single Dockerfile, it is simplest to put the Dockerfile in the base directory; that is, the same directory as the `.sln` file.</span></span> <span data-ttu-id="bfce3-166">이 경우 이미지를 빌드하려면 Dockerfile을 포함 하는 디렉터리에서 다음 `docker build` 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-166">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="bfce3-167">혼동 이라는 이름의 `--tag` 플래그 (`-t`으로 줄일 수 있음)는 지정 된 경우 실제 태그를 *포함* 하 여 이미지의 전체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-167">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, *including* the actual tag if specified.</span></span> <span data-ttu-id="bfce3-168">끝에 있는 `.`는 빌드가 실행 될 *컨텍스트* 를 지정 합니다. Dockerfile의 `COPY` 명령에 대 한 현재 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-168">The `.` at the end specifies the *context* in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="bfce3-169">단일 솔루션 내에 여러 응용 프로그램이 있는 경우 각 응용 프로그램에 대 한 Dockerfile을 `.csproj` 파일 옆에 있는 자체 폴더에 유지할 수 있지만, 솔루션과 모든 프로젝트가 이미지에 복사 되도록 기본 디렉터리에서 `docker build` 명령을 계속 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-169">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file, but you should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="bfce3-170">`--file` (또는 `-f`) 플래그를 사용 하 여 현재 디렉터리 아래에 Dockerfile을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-170">You can specify a Dockerfile below the current directory using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="bfce3-171">컴퓨터의 컨테이너에서 이미지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-171">Run the image in a container on your machine</span></span>

<span data-ttu-id="bfce3-172">로컬 Docker 인스턴스에서 이미지를 실행 하려면 `docker run` 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-172">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="bfce3-173">`-ti` 플래그는 현재 터미널을 컨테이너의 터미널에 연결 하 고 대화형 모드로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-173">The `-ti` flag connects your current terminal to the container's terminal and runs in interactive mode.</span></span> <span data-ttu-id="bfce3-174">`-p 5000:80`는 컨테이너의 포트 80를 localhost 네트워크 인터페이스의 포트 80에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-174">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="bfce3-175">레지스트리에 이미지 푸시</span><span class="sxs-lookup"><span data-stu-id="bfce3-175">Push the image to a registry</span></span>

<span data-ttu-id="bfce3-176">이미지가 작동 하는지 확인 한 후에는 다른 시스템에서 사용할 수 있도록 Docker 레지스트리에 푸시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-176">Once you've verified that the image works, you need to push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="bfce3-177">내부 네트워크에서 Docker 레지스트리를 프로 비전 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-177">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="bfce3-178">이는 [docker의 자체 `registry` 이미지](https://docs.docker.com/registry/deploying/) 를 실행 하는 것 처럼 간단할 수 있습니다 (docker 레지스트리는 docker 컨테이너에서 실행 됨). 그러나 다양 한 포괄적인 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-178">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (that's right, the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="bfce3-179">외부 공유 및 클라우드 사용을 위해 [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) 또는 [Docker 허브](https://docs.docker.com/docker-hub/repos/)와 같이 다양 한 관리 되는 레지스트리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-179">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="bfce3-180">Docker 허브에 푸시 하려면 이미지 이름 앞에 사용자 또는 조직 이름을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-180">To push to the Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="bfce3-181">개인 레지스트리에 푸시 하려면 이미지 이름 앞에 레지스트리 호스트 이름 및 조직 이름을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-181">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="bfce3-182">이미지가 레지스트리에 있으면 개별 Docker 호스트 또는 Kubernetes와 같은 컨테이너 오케스트레이션 엔진에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce3-182">Once the image is in a registry, you can deploy it to individual Docker hosts or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bfce3-183">[이전](self-hosted.md)
>[다음](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="bfce3-183">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
