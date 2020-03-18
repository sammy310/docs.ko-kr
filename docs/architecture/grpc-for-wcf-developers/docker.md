---
title: 도커 - WCF 개발자를 위한 gRPC
description: ASP.NET 코어 gRPC 응용 프로그램에 대한 도커 이미지 만들기
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148116"
---
# <a name="create-docker-images"></a><span data-ttu-id="da715-103">Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="da715-103">Create Docker images</span></span>

<span data-ttu-id="da715-104">이 섹션에서는 ASP.NET 코어 gRPC 응용 프로그램에 대한 Docker 이미지 생성을 다루며 Docker, Kubernetes 또는 기타 컨테이너 환경에서 실행할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="da715-105">ASP.NET 코어 MVC 웹 앱 및 gRPC 서비스와 함께 사용되는 샘플 응용 프로그램은 GitHub의 [도트넷 아키텍처/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) 리포지토리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="da715-106">ASP.NET 코어 응용 프로그램에 대 한 마이크로소프트 기본 이미지</span><span class="sxs-lookup"><span data-stu-id="da715-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="da715-107">Microsoft는 .NET Core 응용 프로그램을 빌드하고 실행하기 위한 다양한 기본 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="da715-108">코어 3.0 이미지를 ASP.NET 만들려면 두 개의 기본 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="da715-109">응용 프로그램을 빌드하고 게시할 SDK 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="da715-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="da715-110">배포를 위한 런타임 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="da715-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="da715-111">이미지</span><span class="sxs-lookup"><span data-stu-id="da715-111">Image</span></span> | <span data-ttu-id="da715-112">Description</span><span class="sxs-lookup"><span data-stu-id="da715-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="da715-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="da715-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="da715-114">을 통해 `docker build`응용 프로그램을 빌드하는 경우</span><span class="sxs-lookup"><span data-stu-id="da715-114">For building applications with `docker build`.</span></span> <span data-ttu-id="da715-115">생산에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="da715-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="da715-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="da715-117">런타임 및 ASP.NET Core 종속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="da715-118">생산을 위해.</span><span class="sxs-lookup"><span data-stu-id="da715-118">For production.</span></span> |

<span data-ttu-id="da715-119">각 이미지에 대해 태그별로 구별되는 서로 다른 Linux 배포판을 기반으로 하는 네 가지 변형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="da715-120">이미지 태그</span><span class="sxs-lookup"><span data-stu-id="da715-120">Image tag(s)</span></span> | <span data-ttu-id="da715-121">Linux</span><span class="sxs-lookup"><span data-stu-id="da715-121">Linux</span></span> | <span data-ttu-id="da715-122">메모</span><span class="sxs-lookup"><span data-stu-id="da715-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="da715-123">3.0 버스터, 3.0</span><span class="sxs-lookup"><span data-stu-id="da715-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="da715-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="da715-124">Debian 10</span></span> | <span data-ttu-id="da715-125">OS 변형이 지정되지 않은 경우 기본 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="da715-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="da715-126">3.0 알파인</span><span class="sxs-lookup"><span data-stu-id="da715-126">3.0-alpine</span></span> | <span data-ttu-id="da715-127">알파인 3.9</span><span class="sxs-lookup"><span data-stu-id="da715-127">Alpine 3.9</span></span> | <span data-ttu-id="da715-128">알파인 베이스 이미지는 데비안 이나 우분투 이미지 보다 훨씬 작습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="da715-129">3.0 디스코</span><span class="sxs-lookup"><span data-stu-id="da715-129">3.0-disco</span></span> | <span data-ttu-id="da715-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="da715-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="da715-131">3.0 바이오닉</span><span class="sxs-lookup"><span data-stu-id="da715-131">3.0-bionic</span></span> | <span data-ttu-id="da715-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="da715-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="da715-133">알프스 의 기본 이미지는 데비안 과 우분투 이미지의 경우 200 MB에 비해 약 100 MB입니다.</span><span class="sxs-lookup"><span data-stu-id="da715-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="da715-134">일부 소프트웨어 패키지 또는 라이브러리는 Alpine의 패키지 관리에서 사용하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="da715-135">사용할 이미지를 잘 모르는 경우 기본 데비안(Debian)을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da715-136">빌드 및 런타임에 동일한 Linux 변형을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="da715-137">한 변형에 빌드되고 게시된 응용 프로그램은 다른 변형에서 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="da715-138">Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="da715-138">Create a Docker image</span></span>

<span data-ttu-id="da715-139">Docker 이미지는 *Dockerfile*에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="da715-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="da715-140">이 파일은 응용 프로그램을 빌드하고 응용 프로그램을 빌드하거나 실행하는 데 필요한 모든 종속성을 설치하는 데 필요한 모든 명령을 포함하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="da715-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="da715-141">다음 예제에서는 ASP.NET 코어 3.0 응용 프로그램에 대한 가장 간단한 Dockerfile을 보여 주며 다음과 같은 예제를 보여 주며 다음과 같은 예제를 보여 주며 다음과 같은 예제를 보여 주며 다음과 같은</span><span class="sxs-lookup"><span data-stu-id="da715-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="da715-142">Dockerfile에는 두 부분으로 구성됩니다. `sdk` 두 번째는 `aspnet` 베이스에서 런타임 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da715-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="da715-143">이는 런타임 `sdk` 이미지의 경우 약 200MB에 비해 이미지가 약 900MB이며 대부분의 내용은 런타임에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="da715-144">빌드 단계</span><span class="sxs-lookup"><span data-stu-id="da715-144">The build steps</span></span>

| <span data-ttu-id="da715-145">단계</span><span class="sxs-lookup"><span data-stu-id="da715-145">Step</span></span> | <span data-ttu-id="da715-146">Description</span><span class="sxs-lookup"><span data-stu-id="da715-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="da715-147">기본 이미지를 선언하고 별칭을 `builder` 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="da715-148">디렉터리를 `/src` 만들고 현재 작업 디렉토리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="da715-149">호스트의 현재 디렉터리 아래에 있는 모든 것을 이미지의 현재 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="da715-150">모든 외부 패키지를 복원합니다(ASP.NET 코어 3.0 프레임워크는 SDK와 함께 사전 설치되어 있음).</span><span class="sxs-lookup"><span data-stu-id="da715-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="da715-151">릴리스 빌드를 빌드하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="da715-152">플래그는 `--runtime` 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="da715-153">런타임 이미지 단계</span><span class="sxs-lookup"><span data-stu-id="da715-153">The runtime image steps</span></span>

| <span data-ttu-id="da715-154">단계</span><span class="sxs-lookup"><span data-stu-id="da715-154">Step</span></span> | <span data-ttu-id="da715-155">Description</span><span class="sxs-lookup"><span data-stu-id="da715-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="da715-156">새 기본 이미지를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="da715-157">디렉터리를 `/app` 만들고 현재 작업 디렉토리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="da715-158">첫 번째 `builder` `FROM` 줄의 별칭을 사용하여 이전 이미지에서 게시된 응용 프로그램을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="da715-159">컨테이너가 시작될 때 실행되도록 명령을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="da715-160">런타임 이미지의 `dotnet` 명령은 DLL 파일만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="da715-161">도커의 HTTPS</span><span class="sxs-lookup"><span data-stu-id="da715-161">HTTPS in Docker</span></span>

<span data-ttu-id="da715-162">Docker에 대 한 `ASPNETCORE_URLS` Microsoft 기본 `http://+:80`이미지 환경 변수를 설정 합니다., 즉 Kestrel 해당 포트에 HTTPS 없이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da715-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="da715-163">사용자 지정 [인증서(자체 호스팅 gRPC 응용 프로그램에](self-hosted.md)설명된 대로)와 함께 HTTPS를 사용하는 경우 이를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="da715-164">Dockerfile의 런타임 이미지 생성 부분에서 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="da715-165">.dockerignore 파일</span><span class="sxs-lookup"><span data-stu-id="da715-165">The .dockerignore file</span></span>

<span data-ttu-id="da715-166">소스 `.gitignore` 제어에서 특정 파일 및 디렉터리를 `.dockerignore` 제외하는 파일과 마찬가지로 파일을 사용하여 파일 및 디렉터리가 빌드 하는 동안 이미지에 복사되는 것을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="da715-167">이렇게 하면 복사 시간을 절약할 수 있지만 PC의 `obj` 디렉터리를 이미지로 복사하여 발생하는 일부 오류를 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="da715-168">최소한 `bin` `.dockerignore` 파일에 대한 `obj` 항목을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="da715-169">이미지 빌드</span><span class="sxs-lookup"><span data-stu-id="da715-169">Build the image</span></span>

<span data-ttu-id="da715-170">단일 응용 프로그램과 단일 Dockerfile이 있는 솔루션의 경우 Dockerfile을 기본 디렉터리에 넣는 것이 가장 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="da715-171">즉, 파일과 동일한 디렉토리에 `.sln` 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="da715-172">이 경우 이미지를 빌드하려면 Dockerfile이 `docker build` 포함된 디렉터리에서 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="da715-173">혼동할 수 `--tag` 있는 플래그(단축할 `-t`수 있음)는 지정된 경우 실제 태그를 포함하여 이미지의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="da715-174">끝에는 `.` 빌드가 실행될 컨텍스트를 지정합니다. Dockerfile의 `COPY` 명령에 대한 현재 작업 디렉토리입니다.</span><span class="sxs-lookup"><span data-stu-id="da715-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="da715-175">단일 솔루션 내에 여러 응용 프로그램이 있는 경우 파일 옆에 각 응용 프로그램에 대한 `.csproj` Dockerfile을 자체 폴더에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="da715-176">솔루션과 모든 `docker build` 프로젝트가 이미지에 복사되도록 기본 디렉터리에서 명령을 계속 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="da715-177">(또는) `-f`플래그를 사용하여 현재 디렉터리 `--file` 아래에 Dockerfile을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="da715-178">컴퓨터의 컨테이너에서 이미지 실행</span><span class="sxs-lookup"><span data-stu-id="da715-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="da715-179">로컬 Docker 인스턴스에서 이미지를 실행하려면 `docker run` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="da715-180">플래그는 `-ti` 현재 터미널을 컨테이너터미널에 연결하고 대화형 모드로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="da715-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="da715-181">로컬 `-p 5000:80` 호스트 네트워크 인터페이스에서 포트 5000에 컨테이너에 (링크) 포트(80)를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="da715-182">이미지를 레지스트리로 푸시</span><span class="sxs-lookup"><span data-stu-id="da715-182">Push the image to a registry</span></span>

<span data-ttu-id="da715-183">이미지가 작동하는지 확인한 후 Docker 레지스트리로 푸시하여 다른 시스템에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="da715-184">내부 네트워크는 Docker 레지스트리를 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="da715-185">이는 [Docker `registry` 자체 이미지(Docker](https://docs.docker.com/registry/deploying/) 레지스트리가 Docker 컨테이너에서 실행됨)를 실행하는 것만큼 간단할 수 있지만 다양한 포괄적인 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="da715-186">외부 공유 및 클라우드 사용의 경우 Azure 컨테이너 [레지스트리](https://docs.microsoft.com/azure/container-registry/) 또는 [Docker Hub와](https://docs.docker.com/docker-hub/repos/)같은 다양한 관리되는 레지스트리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="da715-187">Docker Hub로 푸시하려면 사용자 또는 조직 이름으로 이미지 이름을 접두사로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="da715-188">개인 레지스트리로 푸시하려면 레지스트리 호스트 이름과 조직 이름으로 이미지 이름을 접두사로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da715-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="da715-189">이미지가 레지스트리에 있으면 개별 Docker 호스트 또는 Kubernetes와 같은 컨테이너 오케스트레이션 엔진에 이미지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da715-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="da715-190">[이전](self-hosted.md)
>[다음](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="da715-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
