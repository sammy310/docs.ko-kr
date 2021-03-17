---
title: D 4에서 시작
description: 로컬 개발 환경을 준비 하 고, .NET 응용 프로그램을 사용 하 여 첫 번째 .NET 응용 프로그램을 구축 하기 위한 가이드입니다.
author: amolenk
ms.date: 02/25/2021
ms.openlocfilehash: 1b6ecd2cc2bf077375262155f0866cfef2dab708
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623813"
---
# <a name="get-started-with-dapr"></a><span data-ttu-id="bec1a-103">D 4에서 시작</span><span class="sxs-lookup"><span data-stu-id="bec1a-103">Get started with Dapr</span></span>

<span data-ttu-id="bec1a-104">처음 두 장에서는 d 4의 기본 개념을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-104">In the first two chapters, you learned basic concepts about Dapr.</span></span> <span data-ttu-id="bec1a-105">*시험* 사용에 사용할 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-105">It's time to take it for a *test drive*.</span></span> <span data-ttu-id="bec1a-106">이 장에서는 로컬 개발 환경을 준비 하 고 두 개의 4 개의 기본 .NET 응용 프로그램을 빌드하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-106">This chapter will guide you through preparing your local development environment and building two Dapr .NET applications.</span></span>

## <a name="install-dapr-into-your-local-environment"></a><span data-ttu-id="bec1a-107">로컬 환경에 4Apr 설치</span><span class="sxs-lookup"><span data-stu-id="bec1a-107">Install Dapr into your local environment</span></span>

<span data-ttu-id="bec1a-108">먼저 개발 컴퓨터에 d 4를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-108">You'll start by installing Dapr on your development computer.</span></span> <span data-ttu-id="bec1a-109">완료 되 면 [자체 호스팅 모드](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-overview/)에서 4apr 응용 프로그램을 빌드하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-109">Once complete, you can build and run Dapr applications in [self-hosted mode](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-overview/).</span></span>

1. <span data-ttu-id="bec1a-110">[Eapr CLI를 설치](https://docs.dapr.io/getting-started/install-dapr-cli/)합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-110">[Install the Dapr CLI](https://docs.dapr.io/getting-started/install-dapr-cli/).</span></span> <span data-ttu-id="bec1a-111">이 기능을 사용 하면 4 개 인스턴스를 시작, 실행 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-111">It enables you to launch, run, and manage Dapr instances.</span></span> <span data-ttu-id="bec1a-112">또한 디버깅 지원도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-112">It also provides debugging support.</span></span>

1. <span data-ttu-id="bec1a-113">[Docker Desktop](https://docs.docker.com/get-docker/)을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-113">Install [Docker Desktop](https://docs.docker.com/get-docker/).</span></span> <span data-ttu-id="bec1a-114">Windows에서 실행 하는 경우 **windows 용 Docker 데스크톱이** Linux 컨테이너를 사용 하도록 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-114">If you're running on Windows, make sure that **Docker Desktop for Windows** is configured to use Linux containers.</span></span>

> [!NOTE]
> <span data-ttu-id="bec1a-115">기본적으로 d 4는 Docker 컨테이너를 사용 하 여 최적의 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-115">By default, Dapr uses Docker containers to provide you the best out-of-the-box experience.</span></span> <span data-ttu-id="bec1a-116">Docker 외부에서 Docker를 실행 하려면이 단계를 건너뛰고 [ *슬림* 한 초기화를 실행할](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-116">To run Dapr outside of Docker, you can skip this step and [execute a *slim* initialization](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/).</span></span> <span data-ttu-id="bec1a-117">이 챕터의 예제에서는 Docker 컨테이너를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-117">The examples in this chapter require you use Docker containers.</span></span>

1. <span data-ttu-id="bec1a-118">[초기화](https://docs.dapr.io/getting-started/install-dapr/)합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-118">[Initialize Dapr](https://docs.dapr.io/getting-started/install-dapr/).</span></span> <span data-ttu-id="bec1a-119">이 단계에서는 최신 Eapr 이진 파일과 컨테이너 이미지를 설치 하 여 개발 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-119">This step sets up your development environment by installing the latest Dapr binaries and container images.</span></span>

1. <span data-ttu-id="bec1a-120">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-120">Install the [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1).</span></span>

<span data-ttu-id="bec1a-121">이제는 d 4 월이 설치 되었으므로 첫 번째 응용 프로그램을 빌드할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-121">Now that Dapr is installed, it's time to build your first Dapr application!</span></span>

## <a name="build-your-first-dapr-application"></a><span data-ttu-id="bec1a-122">첫 번째 4Apr 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="bec1a-122">Build your first Dapr application</span></span>

<span data-ttu-id="bec1a-123">먼저 [Eapr 상태 관리](state-management.md) 빌딩 블록을 사용 하는 간단한 .net 콘솔 응용 프로그램을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-123">You'll start by building a simple .NET Console application that consumes the [Dapr state management](state-management.md) building block.</span></span>

### <a name="create-the-application"></a><span data-ttu-id="bec1a-124">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="bec1a-124">Create the application</span></span>

1. <span data-ttu-id="bec1a-125">선택한 명령 셸 또는 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-125">Open up the command shell or terminal of your choice.</span></span> <span data-ttu-id="bec1a-126">[Visual Studio Code](https://code.visualstudio.com/)의 터미널 기능을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-126">You might consider the terminal capabilities in [Visual Studio Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="bec1a-127">응용 프로그램을 빌드하는 데 사용할 루트 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-127">Navigate to the root folder in which you want to build your application.</span></span> <span data-ttu-id="bec1a-128">새 .NET 콘솔 응용 프로그램을 만들려면 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-128">Once there, enter the following command to create a new .NET Console application:</span></span>

    ```dotnetcli
    dotnet new console -o DaprCounter
    ```

    <span data-ttu-id="bec1a-129">명령은 간단한 "헬로 월드" .NET Core 응용 프로그램을 스 캐 폴드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-129">The command scaffolds a simple "Hello World" .NET Core application.</span></span>

1. <span data-ttu-id="bec1a-130">그런 다음, 이전 명령으로 만든 새 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-130">Then, navigate into the new directory created by the previous command:</span></span>

    ```console
    cd DaprCounter
    ```

1. <span data-ttu-id="bec1a-131">명령을 사용 하 여 새로 만든 응용 프로그램을 실행 합니다 `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-131">Run the newly created application using the `dotnet run` command.</span></span> <span data-ttu-id="bec1a-132">"헬로 월드!"을 (를) 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-132">Doing so writes "Hello World!"</span></span> <span data-ttu-id="bec1a-133">콘솔 화면으로:</span><span class="sxs-lookup"><span data-stu-id="bec1a-133">to the console screen:</span></span>

    ```dotnetcli
    dotnet run
    ```

### <a name="add-dapr-state-management"></a><span data-ttu-id="bec1a-134">Eapr 상태 관리 추가</span><span class="sxs-lookup"><span data-stu-id="bec1a-134">Add Dapr State Management</span></span>

<span data-ttu-id="bec1a-135">다음으로는, 프로그램에서 상태 저장 카운터를 구현 하는 데에는 Eapr [상태 관리 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/state-management/state-management-overview/) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-135">Next, you'll use the Dapr [state management building block](https://docs.dapr.io/developing-applications/building-blocks/state-management/state-management-overview/) to implement a stateful counter in the program.</span></span>

<span data-ttu-id="bec1a-136">HTTP 및 gRPC에 대 한 4 개의 기본 지원을 사용 하 여 모든 개발 플랫폼에서 4 개의 Api를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-136">You can invoke Dapr APIs across any development platform using Dapr's native support for HTTP and gRPC.</span></span> <span data-ttu-id="bec1a-137">그러나 .NET 개발자는 보다 자연스럽 고 직관적인 .NET SDK를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-137">However, .NET Developers will find the Dapr .NET SDK more natural and intuitive.</span></span> <span data-ttu-id="bec1a-138">이 클래스는 Eapr Api를 호출 하기 위한 강력한 형식의 .NET 클라이언트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-138">It provides a strongly typed .NET client to call the Dapr APIs.</span></span> <span data-ttu-id="bec1a-139">또한 .NET SDK는 ASP.NET Core와 긴밀 하 게 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-139">The .NET SDK also tightly integrates with ASP.NET Core.</span></span>

1. <span data-ttu-id="bec1a-140">터미널 창에서 `Dapr.Client` 응용 프로그램에 NuGet 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-140">From the terminal window, add the `Dapr.Client` NuGet package to your application:</span></span>

    ```dotnetcli
    dotnet add package Dapr.Client
    ```

    > [!NOTE]
    > <span data-ttu-id="bec1a-141">버전 4의 시험판 버전을 사용 하는 경우 `--prerelease` 플래그를 명령에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-141">If you're working with a pre-release version of Dapr, be sure to add the `--prerelease` flag to the command.</span></span>

1. <span data-ttu-id="bec1a-142">자주 사용 `Program.cs` 하는 편집기에서 파일을 열고 내용을 다음 코드로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-142">Open the `Program.cs` file in your favorite editor and update its contents to the following code:</span></span>

    ```csharp
    using System;
    using System.Threading.Tasks;
    using Dapr.Client;

    namespace DaprCounter
    {
        class Program
        {
            static async Task Main(string[] args)
            {
                const string storeName = "statestore";
                const string key = "counter";

                var daprClient = new DaprClientBuilder().Build();
                var counter = await daprClient.GetStateAsync<int>(storeName, key);

                while (true)
                {
                    Console.WriteLine($"Counter = {counter++}");

                    await daprClient.SaveStateAsync(storeName, key, counter);
                    await Task.Delay(1000);
                }
            }
        }
    }
    ```

    <span data-ttu-id="bec1a-143">업데이트 된 코드는 다음 단계를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-143">The updated code implements the following steps:</span></span>

    - <span data-ttu-id="bec1a-144">처음에는 새 `DaprClient` 인스턴스가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-144">First a new `DaprClient` instance is instantiated.</span></span> <span data-ttu-id="bec1a-145">이 클래스를 사용 하 여 사이드카와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-145">This class enables you to interact with the Dapr sidecar.</span></span>
    - <span data-ttu-id="bec1a-146">상태 저장소에서 `DaprClient.GetStateAsync` 키에 대 한 값을 페치합니다 `counter` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-146">From the state store, `DaprClient.GetStateAsync` fetches the value for the `counter` key.</span></span> <span data-ttu-id="bec1a-147">키가 없으면 기본값 `int` ( `0` )이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-147">If the key doesn't exist, the default `int` value (which is `0`) is returned.</span></span>
    - <span data-ttu-id="bec1a-148">그런 다음 코드는를 반복 하 여 `counter` 값을 콘솔에 쓰고 증가 된 값을 상태 저장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-148">The code then iterates, writing the `counter` value to the console and saving an incremented value to the state store.</span></span>

1. <span data-ttu-id="bec1a-149">D Apr CLI `run` 명령은 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-149">The Dapr CLI `run` command starts the application.</span></span> <span data-ttu-id="bec1a-150">기본 6Apr 런타임을 호출 하 고 응용 프로그램과 d 4 사이드카를 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-150">It invokes the underlying Dapr runtime and enables both the application and Dapr sidecar to run together.</span></span> <span data-ttu-id="bec1a-151">를 생략 하는 경우에는 `app-id` 응용 프로그램에 대 한 고유한 이름을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-151">If you omit the `app-id`, Dapr will generate a unique name for the application.</span></span> <span data-ttu-id="bec1a-152">명령의 마지막 세그먼트는 `dotnet run` .net core 응용 프로그램을 실행 하도록 Capr 런타임에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-152">The final segment of the command, `dotnet run`, instructs the Dapr runtime to run the .NET core application.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bec1a-153">`app-id`상태 관리 빌딩 블록을 사용 하는 경우 항상 명시적 매개 변수를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-153">Care must be taken to always pass an explicit `app-id` parameter when consuming the state management building block.</span></span> <span data-ttu-id="bec1a-154">블록은 각 키/값 쌍에 대 한 상태 키의 *접두사로* 응용 프로그램 id 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-154">The block uses the application id value as a *prefix* for its state key for each key/value pair.</span></span> <span data-ttu-id="bec1a-155">응용 프로그램 id가 변경 되 면 이전에 저장 된 상태에 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-155">If the application id changes, you can no longer access the previously stored state.</span></span>

    <span data-ttu-id="bec1a-156">이제 다음 명령을 사용 하 여 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-156">Now run the application with the following command:</span></span>

    ```console
    dapr run --app-id DaprCounter dotnet run
    ```

    <span data-ttu-id="bec1a-157">응용 프로그램을 중지 하 고 다시 시작 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bec1a-157">Try stopping and restarting the application.</span></span> <span data-ttu-id="bec1a-158">카운터가 다시 설정 되지 않는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-158">You'll see that the counter doesn't reset.</span></span> <span data-ttu-id="bec1a-159">대신 이전에 저장 된 상태에서 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-159">Instead it continues from the previously saved state.</span></span> <span data-ttu-id="bec1a-160">Eapr 빌딩 블록은 응용 프로그램 상태 저장을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-160">The Dapr building block makes the application stateful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bec1a-161">응용 프로그램 예제는 미리 구성 된 상태 구성 요소와 통신 하지만 직접 종속성은 없다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-161">It's important to understand your sample application communicates with a pre-configured state component, but has no direct dependency on it.</span></span> <span data-ttu-id="bec1a-162">D apr는 종속성을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-162">Dapr abstracts away the dependency.</span></span> <span data-ttu-id="bec1a-163">잠시 후 간단한 구성 업데이트를 사용 하 여 기본 상태 저장소 구성 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-163">As you'll shortly see, the underlying state store component can be changed with a simple configuration update.</span></span>

<span data-ttu-id="bec1a-164">정확 하 게 저장 된 상태는 궁금할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-164">You might be wondering, where exactly is the state stored?</span></span>

## <a name="component-configuration-files"></a><span data-ttu-id="bec1a-165">구성 요소 구성 파일</span><span class="sxs-lookup"><span data-stu-id="bec1a-165">Component configuration files</span></span>

<span data-ttu-id="bec1a-166">로컬 환경에 대해 처음 초기화할 때 Redis 컨테이너를 자동으로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-166">When you first initialized Dapr for your local environment, it automatically provisioned a Redis container.</span></span> <span data-ttu-id="bec1a-167">그런 다음 Redis 컨테이너를 구성 요소 구성 파일을 사용 하 여 기본 상태 저장소 구성 요소로 구성 `statestore.yaml` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-167">Dapr then configured the Redis container as the default state store component with a component configuration file, entitled `statestore.yaml`.</span></span> <span data-ttu-id="bec1a-168">다음은 해당 내용을 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-168">Here's a look at its contents:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
```

> [!NOTE]
> <span data-ttu-id="bec1a-169">기본 구성 요소 구성 파일은 `$HOME/.dapr/components` Linux/macOS의 폴더와 `%USERPROFILE%\.dapr\components` Windows의 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-169">Default component configuration files are stored in the `$HOME/.dapr/components` folder on Linux/macOS, and in the `%USERPROFILE%\.dapr\components` folder on Windows.</span></span>

<span data-ttu-id="bec1a-170">이전 구성 요소 구성 파일의 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-170">Note the format of the previous component configuration file:</span></span>

- <span data-ttu-id="bec1a-171">각 구성 요소에는 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-171">Each component has a name.</span></span> <span data-ttu-id="bec1a-172">위의 샘플에서 구성 요소의 이름은 `statestore` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-172">In the sample above, the component is named `statestore`.</span></span> <span data-ttu-id="bec1a-173">첫 번째 코드 예제에서이 이름을 사용 하 여 사용할 구성 요소를 사이드카에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-173">We used that name in our first code example to tell the Dapr sidecar which component to use.</span></span>
- <span data-ttu-id="bec1a-174">각 구성 요소 구성 파일에는 `spec` 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-174">Each component configuration file has a `spec` section.</span></span> <span data-ttu-id="bec1a-175">`type`구성 요소 유형을 지정 하는 필드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-175">It contains a `type` field that specifies the component type.</span></span> <span data-ttu-id="bec1a-176">`version`필드는 구성 요소 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-176">The `version` field specifies the component version.</span></span> <span data-ttu-id="bec1a-177">필드에는 `metadata` 연결 정보 및 기타 설정과 같이 구성 요소에 필요한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-177">The `metadata` field contains information that the component requires, such as connection details and other settings.</span></span> <span data-ttu-id="bec1a-178">메타 데이터 값은 다양 한 구성 요소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-178">The metadata values will vary for the different types of components.</span></span>

<span data-ttu-id="bec1a-179">사이드카는 응용 프로그램에 구성 된 모든 Eapr 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-179">A Dapr sidecar can consume any Dapr component configured in your application.</span></span> <span data-ttu-id="bec1a-180">그러나 구성 요소에 대 한 액세스 가능성을 제한 하기 위한 아키텍처 근거가 있는 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="bec1a-180">But, what if you had an architectural justification to limit the accessibility of a component?</span></span> <span data-ttu-id="bec1a-181">프로덕션 환경 에서만 실행 되는 Redis 구성 요소를 Aapr 사이드카로 제한 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="bec1a-181">How could you restrict the Redis component to Dapr sidecars running only in a production environment?</span></span>

<span data-ttu-id="bec1a-182">이렇게 하려면 `namespace` 프로덕션 환경에 대 한을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-182">To do so, you could define a `namespace` for the production environment.</span></span> <span data-ttu-id="bec1a-183">이름을로 할 수 있습니다 `production` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-183">You might name it `production`.</span></span> <span data-ttu-id="bec1a-184">자체 호스팅 모드에서는 환경 변수를 설정 하 여 Eapr 사이드카의 네임 스페이스를 지정 합니다 `NAMESPACE` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-184">In self-hosted mode, you specify the namespace of a Dapr sidecar by setting the `NAMESPACE` environment variable.</span></span> <span data-ttu-id="bec1a-185">구성 된 경우에는 사이드카가 네임 스페이스와 일치 하는 구성 요소만 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-185">When configured, the Dapr sidecar will only load the components that match the namespace.</span></span> <span data-ttu-id="bec1a-186">Kubernetes 배포의 경우 Kubernetes 네임 스페이스는 로드 되는 구성 요소를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-186">For Kubernetes deployments, the Kubernetes namespace determines the components that are loaded.</span></span> <span data-ttu-id="bec1a-187">다음 샘플에서는 네임 스페이스에 배치 된 Redis 구성 요소를 보여 줍니다 `production` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-187">The following sample shows the Redis component placed in a `production` namespace.</span></span> <span data-ttu-id="bec1a-188">`namespace`요소의 선언을 확인 합니다 `metadata` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-188">Note the `namespace` declaration in the `metadata` element:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
  namespace: production
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
```

> [!IMPORTANT]
> <span data-ttu-id="bec1a-189">Namespaced 구성 요소는 동일한 네임 스페이스에서 실행 되는 응용 프로그램 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-189">A namespaced component is only accessible to applications running in the same namespace.</span></span> <span data-ttu-id="bec1a-190">Eapr 응용 프로그램이 구성 요소를 로드 하지 못하는 경우 응용 프로그램 네임 스페이스는 구성 요소 네임 스페이스와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-190">If your Dapr application fails to load a component, make sure that the application namespace matches the component namespace.</span></span> <span data-ttu-id="bec1a-191">응용 프로그램 네임 스페이스는 환경 변수에 저장 되는 자체 호스팅 모드에서는 특히 복잡할 수 있습니다 `NAMESPACE` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-191">This can be especially tricky in self-hosted mode where the application namespace is stored in a `NAMESPACE` environment variable.</span></span>

<span data-ttu-id="bec1a-192">필요한 경우 특정 응용 프로그램으로 구성 요소를 추가로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-192">If needed, you could further restrict a component to a particular application.</span></span> <span data-ttu-id="bec1a-193">`production`네임 스페이스 내에서 Redis cache에 대 한 액세스를 응용 프로그램 으로만 제한 하는 것이 좋습니다 `DaprCounter` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-193">Within the `production` namespace, you may want to limit access of the Redis cache to only the `DaprCounter` application.</span></span> <span data-ttu-id="bec1a-194">구성 요소 구성에서을 지정 하 여이 작업을 수행 `scopes` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-194">You do so by specifying `scopes` in the component configuration.</span></span> <span data-ttu-id="bec1a-195">다음 예제에서는 `statestore` `DaprCounter` 네임 스페이스의 응용 프로그램에 대 한 Redis 구성 요소에 대 한 액세스를 제한 하는 방법을 보여 줍니다 `production` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-195">The following example shows how to restrict access to the Redis `statestore` component to the application `DaprCounter` in the `production` namespace:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
  namespace: production
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
  scopes:
  - DaprCounter
```

## <a name="build-a-multi-container-dapr-application"></a><span data-ttu-id="bec1a-196">다중 컨테이너 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="bec1a-196">Build a multi-container Dapr application</span></span>

<span data-ttu-id="bec1a-197">첫 번째 예제에서는 사이드카를 사용 하 여 side-by-side로 실행 되는 간단한 .NET 콘솔 응용 프로그램을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-197">In the first example, you created a simple .NET console application that ran side-by-side with a Dapr sidecar.</span></span> <span data-ttu-id="bec1a-198">그러나 최신 분산 응용 프로그램은 종종 많은 이동 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-198">Modern distributed applications, however, often consist of many moving parts.</span></span> <span data-ttu-id="bec1a-199">독립적인 마이크로 서비스를 동시에 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-199">They can simultaneously run independent microservices.</span></span> <span data-ttu-id="bec1a-200">이러한 최신 응용 프로그램은 일반적으로 컨테이너 화 된, Docker Compose 또는 Kubernetes와 같은 컨테이너 오케스트레이션 도구가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-200">These modern applications are typically containerized and require container orchestration tools such as Docker Compose or Kubernetes.</span></span>

<span data-ttu-id="bec1a-201">다음 예제에서는 다중 컨테이너 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-201">In the next example, you'll create a multi-container application.</span></span> <span data-ttu-id="bec1a-202">또한 서비스 간에 통신 하는 데는 [Eapr 서비스 호출](service-invocation.md) 빌딩 블록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-202">You'll also use the [Dapr service invocation](service-invocation.md) building block to communicate between services.</span></span> <span data-ttu-id="bec1a-203">이 솔루션은 웹 API에서 날씨 예측을 검색 하는 웹 응용 프로그램으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-203">The solution will consist of a web application that retrieves weather forecasts from a web API.</span></span> <span data-ttu-id="bec1a-204">각 사용자는 Docker 컨테이너에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-204">They will each run in a Docker container.</span></span> <span data-ttu-id="bec1a-205">Docker Compose를 사용 하 여 컨테이너를 로컬로 실행 하 고 디버깅 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-205">You'll use Docker Compose to run the container locally and enable debugging capabilities.</span></span>

<span data-ttu-id="bec1a-206">Core를 사용 하 여 .Net Core 3.1 개발 도구를 설치 했는지 확인 하 고 [.Net Core 개발 도구](https://dotnet.microsoft.com/download/dotnet-core/3.1) 를 설치 했는지 확인 합니다 (이 챕터의 앞부분에서 설명).</span><span class="sxs-lookup"><span data-stu-id="bec1a-206">Make sure you've configured your local environment for Dapr and installed the [.NET Core 3.1 Development Tools](https://dotnet.microsoft.com/download/dotnet-core/3.1) (instructions are available at the beginning of this chapter).</span></span>

<span data-ttu-id="bec1a-207">또한 **.Net Core 플랫폼 간 개발** 워크 로드가 설치 된 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) 을 사용 하 여이 샘플을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-207">Additionally, you'll need complete this sample using [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) with the **.NET Core cross-platform development** workload installed.</span></span>

### <a name="create-the-application"></a><span data-ttu-id="bec1a-208">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="bec1a-208">Create the application</span></span>

1. <span data-ttu-id="bec1a-209">Visual Studio 2019에서 **ASP.NET Core 웹 앱** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-209">In Visual Studio 2019, create an **ASP.NET Core Web App** project:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-createproject.png" alt-text="새 프로젝트를 만드는 스크린샷":::

1. <span data-ttu-id="bec1a-211">프로젝트 `DaprFrontEnd` 및 솔루션의 이름을 `DaprMultiContainer` 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-211">Name your project `DaprFrontEnd` and your solution `DaprMultiContainer`:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-configureproject.png" alt-text="새 프로젝트를 구성 하는 스크린샷":::

1. <span data-ttu-id="bec1a-213">**웹 애플리케이션** 을 선택하여 Razor Pages로 웹 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-213">Select **Web Application** to create a web application with Razor pages.</span></span> <span data-ttu-id="bec1a-214">Docker 지원 사용을 선택하지 **마세요**.</span><span class="sxs-lookup"><span data-stu-id="bec1a-214">Don't select **Enable Docker Support**.</span></span> <span data-ttu-id="bec1a-215">Docker 지원은 나중에 추가하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-215">You'll add Docker support later.</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-createwebapp.png" alt-text="새 ASP.NET Core 웹 응용 프로그램을 만드는 스크린샷":::

1. <span data-ttu-id="bec1a-217">ASP.NET Core Web API 프로젝트를 동일한 솔루션에 추가 하 고 _DaprBackEnd_ 를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-217">Add a ASP.NET Core Web API project to the same solution and call it _DaprBackEnd_.</span></span> <span data-ttu-id="bec1a-218">프로젝트 형식으로 **API** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-218">Select **API** as the project type.</span></span> <span data-ttu-id="bec1a-219">기본적으로, 사이드카는 네트워크 경계를 사용 하 여 공용 API에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-219">By default, a Dapr sidecar relies on the network boundary to limit access to its public API.</span></span> <span data-ttu-id="bec1a-220">따라서 **HTTPS에 대해 구성** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-220">So, clear the checkbox for **Configure for HTTPS**.</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-createwebapi.png" alt-text="Web API 만들기 스크린샷":::

### <a name="add-dapr-service-invocation"></a><span data-ttu-id="bec1a-222">Eapr 서비스 호출 추가</span><span class="sxs-lookup"><span data-stu-id="bec1a-222">Add Dapr service invocation</span></span>

<span data-ttu-id="bec1a-223">이제는 Eapr [서비스 호출 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/)을 사용 하 여 서비스 간의 통신을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-223">Now, you'll configure communication between the services using Dapr [service invocation building block](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/).</span></span> <span data-ttu-id="bec1a-224">웹 앱이 web API에서 날씨 예측을 검색할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-224">You'll enable the web app to retrieve weather forecasts from the web API.</span></span> <span data-ttu-id="bec1a-225">서비스 호출 구성 요소는 다양 한 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-225">The service invocation building block features many benefits.</span></span> <span data-ttu-id="bec1a-226">여기에는 서비스 검색, 자동 다시 시도, mTLS를 사용 하는 메시지 암호화 및 향상 된 관찰성 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-226">It includes service discovery, automatic retries, message encryption (using mTLS), and improved observability.</span></span> <span data-ttu-id="bec1a-227">Dapr 사이드카에서 서비스 호출 API를 호출 하려면 Dapr .NET SDK를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-227">You'll use the Dapr .NET SDK to invoke the service invocation API on the Dapr sidecar.</span></span>

1. <span data-ttu-id="bec1a-228">Visual Studio에서 패키지 관리자 콘솔 (**도구 > NuGet 패키지 관리자 > 패키지 관리자 콘솔**)을 열고 `DaprFrontEnd` 이 기본 프로젝트 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-228">In Visual Studio, open the Package Manager Console (**Tools > NuGet Package Manager > Package Manager Console**) and make sure that `DaprFrontEnd` is the default project.</span></span> <span data-ttu-id="bec1a-229">콘솔에서 `Dapr.AspNetCore` NuGet 패키지를 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-229">From the console, add the `Dapr.AspNetCore` NuGet package to the project:</span></span>

    ```powershell
    Install-Package Dapr.AspNetCore
    ```

    > [!NOTE]
    > <span data-ttu-id="bec1a-230">시험판에 있는 버전을 대상으로 하는 경우 `Dapr.AspNetCore` 플래그를 지정 해야 `-Prerelease` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-230">If you're targeting a version of `Dapr.AspNetCore` that is in prerelease, you need to specify the `-Prerelease` flag.</span></span>

1. <span data-ttu-id="bec1a-231">프로젝트에서 `DaprFrontEnd` *Startup.cs* 파일을 열고 `ConfigureServices` 메서드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-231">In the `DaprFrontEnd` project, open the *Startup.cs* file, and replace the `ConfigureServices` method with the following code:</span></span>

    ```csharp
    // This method gets called by the runtime. Use this method to add services to the container.
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddControllers().AddDapr();
        services.AddRazorPages();
    }
    ```

    <span data-ttu-id="bec1a-232">호출은 `AddDapr` `DaprClient` ASP.NET Core 종속성 주입 시스템에 클래스를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-232">The call to `AddDapr` registers the `DaprClient` class with the ASP.NET Core dependency injection system.</span></span> <span data-ttu-id="bec1a-233">클라이언트를 등록 하면 이제 `DaprClient` 서비스 코드에 인스턴스를 삽입 하 여 사이드카, 빌딩 블록 및 구성 요소와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-233">With the client registered, you can now inject an instance of `DaprClient` into your service code to communicate with the Dapr sidecar, building blocks, and components.</span></span>

1. <span data-ttu-id="bec1a-234">*WeatherForecast* 라는 새 c # 클래스 파일을 프로젝트에 추가 합니다 `DaprFrontEnd` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-234">Add a new C# class file named *WeatherForecast* to the `DaprFrontEnd` project:</span></span>

    ```csharp
    using System;

    namespace DaprFrontEnd
    {
        public class WeatherForecast
        {
            public DateTime Date { get; set; }

            public int TemperatureC { get; set; }

            public int TemperatureF { get; set; }

            public string Summary { get; set; }
        }
    }
    ```

1. <span data-ttu-id="bec1a-235">*Pages* 폴더에서 *Index.cshtml.cs* 파일을 열고 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-235">Open the *Index.cshtml.cs* file in the *Pages* folder, and replace its contents with the following code:</span></span>

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Net.Http;
    using System.Threading.Tasks;
    using Dapr.Client;
    using Microsoft.AspNetCore.Mvc.RazorPages;

    namespace DaprFrontEnd.Pages
    {
        public class IndexModel : PageModel
        {
            private readonly DaprClient _daprClient;

            public IndexModel(DaprClient daprClient)
            {
                _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));
            }

            public async Task OnGet()
            {
                var forecasts = await _daprClient.InvokeMethodAsync<IEnumerable<WeatherForecast>>(
                    HttpMethod.Get,
                    "daprbackend",
                    "weatherforecast");

                ViewData["WeatherForecastData"] = forecasts;
            }
        }
    }
    ```

    <span data-ttu-id="bec1a-236">생성자에 클래스를 삽입 하 여 웹 앱에 Eapr 기능을 추가 합니다 `DaprClient` `IndexModel` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-236">You add Dapr capabilities into the web app by injecting the `DaprClient` class into `IndexModel` constructor.</span></span> <span data-ttu-id="bec1a-237">메서드에서는 `OnGet` Eapr 서비스 호출 빌딩 블록을 사용 하 여 API 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-237">In the `OnGet` method, you call the API service with the Dapr service invocation building block.</span></span> <span data-ttu-id="bec1a-238">`OnGet`메서드는 사용자가 홈 페이지를 방문할 때마다 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-238">The `OnGet` method is invoked whenever a user visits the home page.</span></span> <span data-ttu-id="bec1a-239">메서드를 사용 하 여 `DaprClient.InvokeMethodAsync` `weatherforecast` 서비스의 메서드를 호출 합니다 `daprbackend` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-239">You use the `DaprClient.InvokeMethodAsync` method to invoke the `weatherforecast` method of the `daprbackend` service.</span></span> <span data-ttu-id="bec1a-240">응용 프로그램 ID로 사용할 웹 API를 구성 하는 경우에는 해당 `daprbackend` 응용 프로그램 ID를 사용 하 여,</span><span class="sxs-lookup"><span data-stu-id="bec1a-240">You'll configure the web API to use `daprbackend` as its application ID later on when configuring it to run with Dapr.</span></span> <span data-ttu-id="bec1a-241">마지막으로 서비스 응답은 보기 데이터에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-241">Finally, the service response is saved in view data.</span></span>

1. <span data-ttu-id="bec1a-242">*Pages* 폴더에 있는 *Index. cshtml* 파일의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-242">Replace the contents of the *Index.cshtml* file in the *Pages* folder, with the following code.</span></span> <span data-ttu-id="bec1a-243">사용자에 게 보기 데이터에 저장 된 날씨 예측을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-243">It displays the weather forecasts stored in the view data to the user:</span></span>

    ```razor
    @page
    @model IndexModel
    @{
        ViewData["Title"] = "Home page";
    }

    <div class="text-center">
        <h1 class="display-4">Welcome</h1>
        <p>Learn about <a href="https://docs.microsoft.com/aspnet/core">building Web apps with ASP.NET Core</a>.</p>
        @foreach (var forecast in (IEnumerable<WeatherForecast>)ViewData["WeatherForecastData"])
        {
            <p>The forecast for @forecast.Date is @forecast.Summary!</p>
        }
    </div>
    ```

### <a name="add-container-support"></a><span data-ttu-id="bec1a-244">컨테이너 지원 추가</span><span class="sxs-lookup"><span data-stu-id="bec1a-244">Add container support</span></span>

<span data-ttu-id="bec1a-245">이 예제의 마지막 부분에서는 컨테이너 지원을 추가 하 고 Docker Compose를 사용 하 여 솔루션을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-245">In the final part of this example, you'll add container support and run the solution using Docker Compose.</span></span>

1. <span data-ttu-id="bec1a-246">프로젝트를 마우스 오른쪽 단추로 클릭 `DaprFrontEnd` 하 고   >  **컨테이너 Orchestrator 지원** 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-246">Right-click the `DaprFrontEnd` project, and choose **Add** > **Container Orchestrator Support**.</span></span> <span data-ttu-id="bec1a-247">**컨테이너 Orchestrator 지원 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-247">The **Add Container Orchestrator Support** dialog appears:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-addorchestrator.png" alt-text="컨테이너 orchestrator 지원 추가 스크린샷":::

    <span data-ttu-id="bec1a-249">**Docker Compose** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-249">Choose **Docker Compose**.</span></span>

1. <span data-ttu-id="bec1a-250">다음 대화 상자에서 대상 OS로 **Linux** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-250">In the next dialog, select **Linux** as the Target OS:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-targetos.png" alt-text="Docker 대상 OS 선택 스크린샷":::

    <span data-ttu-id="bec1a-252">Visual Studio는 솔루션의 **docker 작성** 폴더에 *docker-compose.ci.build.yml* 파일과 *dockerignore* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-252">Visual Studio creates a *docker-compose.yml* file and a *.dockerignore* file in the **docker-compose** folder in the solution:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-dockersolution.png" alt-text="Docker 작성 프로젝트의 스크린샷":::

    <span data-ttu-id="bec1a-254">*Docker-compose.ci.build.yml* 파일에는 다음과 같은 내용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-254">The *docker-compose.yml* file has the following content:</span></span>

    ```yaml
    version: "3.4"

    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile
    ```

    <span data-ttu-id="bec1a-255">*.dockerignore* 파일에는 Docker에서 컨테이너에 포함하지 않을 파일 형식과 확장명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-255">The *.dockerignore* file contains file types and extensions that you don't want Docker to include in the container.</span></span> <span data-ttu-id="bec1a-256">이러한 파일은 개발 환경 및 소스 제어와 연결 되며 배포 중인 앱 또는 서비스가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-256">These files are associated with the development environment and source control and not the app or service you're deploying.</span></span>

    <span data-ttu-id="bec1a-257">*DaprFrontEnd* 프로젝트 디렉터리의 루트에 새 *dockerfile* 이 생성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-257">In the root of the *DaprFrontEnd* project directory, a new *Dockerfile* was created.</span></span> <span data-ttu-id="bec1a-258">*Dockerfile* 은 이미지를 빌드하는 데 사용 되는 일련의 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-258">A *Dockerfile* is a sequence of commands that are used to build an image.</span></span> <span data-ttu-id="bec1a-259">자세한 내용은 [Dockerfile 참조](https://docs.docker.com/engine/reference/builder)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bec1a-259">For more information, see [Dockerfile reference](https://docs.docker.com/engine/reference/builder).</span></span>

    <span data-ttu-id="bec1a-260">*Dockerfile* 에는 yaml이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-260">The *Dockerfile* contains the YAML:</span></span>

    ```yml
    FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
    WORKDIR /app
    EXPOSE 80
    EXPOSE 443

    FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
    WORKDIR /src
    COPY ["DaprFrontEnd/DaprFrontEnd.csproj", "DaprFrontEnd/"]
    RUN dotnet restore "DaprFrontEnd/DaprFrontEnd.csproj"
    COPY . .
    WORKDIR "/src/DaprFrontEnd"
    RUN dotnet build "DaprFrontEnd.csproj" -c Release -o /app/build

    FROM build AS publish
    RUN dotnet publish "DaprFrontEnd.csproj" -c Release -o /app/publish

    FROM base AS final
    WORKDIR /app
    COPY --from=publish /app/publish .
    ENTRYPOINT ["dotnet", "DaprFrontEnd.dll"]
    ```

    <span data-ttu-id="bec1a-261">앞의 *Dockerfile* 은 호출 될 때 다음 단계를 순차적으로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-261">The preceding *Dockerfile* sequentially performs the following steps when invoked:</span></span>

    1. <span data-ttu-id="bec1a-262">이미지를 끌어온 `mcr.microsoft.com/dotnet/aspnet:3.1` 다음 이름을로 `base` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-262">Pulls the `mcr.microsoft.com/dotnet/aspnet:3.1` image and names it `base`.</span></span>
    1. <span data-ttu-id="bec1a-263">작업 디렉터리를 */proapp* 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-263">Sets the working directory to */app*.</span></span>
    1. <span data-ttu-id="bec1a-264">포트 `80` 및를 노출 `443` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-264">Exposes port `80` and `443`.</span></span>
    1. <span data-ttu-id="bec1a-265">이미지를 끌어온 `mcr.microsoft.com/dotnet/sdk:3.1` 다음 이름을로 `build` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-265">Pulls the `mcr.microsoft.com/dotnet/sdk:3.1` image and names it `build`.</span></span>
    1. <span data-ttu-id="bec1a-266">작업 디렉터리를 */src* 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-266">Sets the working directory to */src*.</span></span>
    1. <span data-ttu-id="bec1a-267">_DaprFrontEnd/DaprFrontEnd_ 를 *DaprFrontEnd/* 라는 새 디렉터리에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-267">Copies the _DaprFrontEnd/DaprFrontEnd.csproj_ to a new directory named *DaprFrontEnd/*.</span></span>
    1. <span data-ttu-id="bec1a-268">[`dotnet restore`](../../core/tools/dotnet-restore.md)프로젝트에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-268">Calls [`dotnet restore`](../../core/tools/dotnet-restore.md) on the project.</span></span>
    1. <span data-ttu-id="bec1a-269">루트 디렉터리에서 이미지의 루트에 모든 항목을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-269">Copies everything from the root directory into the image's root.</span></span>
    1. <span data-ttu-id="bec1a-270">작업 디렉터리를 _/src/DaprFrontEnd_ 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-270">Sets the working directory to _/src/DaprFrontEnd_.</span></span>
    1. <span data-ttu-id="bec1a-271">[`dotnet build`](../../core/tools/dotnet-build.md)프로젝트에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-271">Calls [`dotnet build`](../../core/tools/dotnet-build.md) on the project.</span></span>
        - <span data-ttu-id="bec1a-272">**릴리스** 구성의 대상을 지정 하 고 */app/build* 에 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-272">Targeting the **Release** configuration and outputs to */app/build*.</span></span>
    1. <span data-ttu-id="bec1a-273">기존 기본 이미지에서 새 빌드 단계를 초기화 `build` 하 고 이름을로 만듭니다 `publish` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-273">Initializes a new build stage from the existing `build` base image and names it `publish`.</span></span>
    1. <span data-ttu-id="bec1a-274">`dotnet publish`프로젝트에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-274">Calls `dotnet publish` on the project.</span></span>
        - <span data-ttu-id="bec1a-275">**릴리스** 구성 대상 지정 및 */app/publish* 로 출력</span><span class="sxs-lookup"><span data-stu-id="bec1a-275">Targeting the **Release** configuration and outputs to */app/publish*.</span></span>
    1. <span data-ttu-id="bec1a-276">기존 기본 이미지에서 새 빌드 단계를 초기화 `publish` 하 고 이름을로 만듭니다 `final` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-276">Initializes a new build stage from the existing `publish` base image and names it `final`.</span></span>
    1. <span data-ttu-id="bec1a-277">작업 디렉터리를 */proapp* 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-277">Sets the working directory to */app*.</span></span>
    1. <span data-ttu-id="bec1a-278">이미지의 `/app/publish` 디렉터리를 `publish` 이미지의 루트에 복사 `final` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-278">Copies the `/app/publish` directory from the `publish` image into the root of the `final` image.</span></span>
    1. <span data-ttu-id="bec1a-279">진입점을 이미지로 설정 하 고을 인수로 `dotnet` 전달 합니다 `DaprFrontEnd.dll` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-279">Sets the entry point as the image to `dotnet` and passes the `DaprFrontEnd.dll` as an arg.</span></span>

1. <span data-ttu-id="bec1a-280">`DaprBackEnd`Web API 프로젝트에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고   >  **컨테이너 Orchestrator 지원** 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-280">In the `DaprBackEnd` web API project, right-click on the project node, and choose **Add** > **Container Orchestrator Support**.</span></span> <span data-ttu-id="bec1a-281">**Docker Compose** 를 선택 하 고 대상 OS로 **Linux** 를 다시 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-281">Choose **Docker Compose**, and then select **Linux** again as the target OS.</span></span>

    <span data-ttu-id="bec1a-282">_DaprBackEnd_ 프로젝트 디렉터리의 루트에 새 *dockerfile* 이 생성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-282">In the root of the _DaprBackEnd_ project directory, a new *Dockerfile* was created.</span></span> <span data-ttu-id="bec1a-283">*Dockerfile* 에는 다음 yaml이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-283">The *Dockerfile* contains the following YAML:</span></span>

    ```yml
    FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
    WORKDIR /app
    EXPOSE 80

    FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
    WORKDIR /src
    COPY ["DaprBackEnd/DaprBackEnd.csproj", "DaprBackEnd/"]
    RUN dotnet restore "DaprBackEnd/DaprBackEnd.csproj"
    COPY . .
    WORKDIR "/src/DaprBackEnd"
    RUN dotnet build "DaprBackEnd.csproj" -c Release -o /app/build

    FROM build AS publish
    RUN dotnet publish "DaprBackEnd.csproj" -c Release -o /app/publish

    FROM base AS final
    WORKDIR /app
    COPY --from=publish /app/publish .
    ENTRYPOINT ["dotnet", "DaprBackEnd.dll"]
    ```

    <span data-ttu-id="bec1a-284">*Docker-compose.ci.build.yml* 파일을 다시 열고 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-284">Open the *docker-compose.yml* file again and examine its contents.</span></span> <span data-ttu-id="bec1a-285">Visual Studio에서 **Docker Compose** 파일을 업데이트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-285">Visual Studio has updated the **Docker Compose** file.</span></span> <span data-ttu-id="bec1a-286">이제 두 서비스 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-286">Now both services are included:</span></span>

    ```yaml
    version: '3.4'

    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile

      daprbackend:
        image: ${DOCKER_REGISTRY-}daprbackend
        build:
          context: .
          dockerfile: DaprBackEnd/Dockerfile
    ```

1. <span data-ttu-id="bec1a-287">컨테이너 화 된 응용 프로그램 내에서 Eapr 빌딩 블록을 사용 하려면 작성 파일에 Eapr 사이드카 컨테이너를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-287">To use Dapr building blocks from inside a containerized application, you'll need to add the Dapr sidecars containers to your Compose file.</span></span> <span data-ttu-id="bec1a-288">다음 예제와 일치 하도록 *docker-compose.ci.build.yml* 파일의 내용을 신중 하 게 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-288">Carefully update the content of the *docker-compose.yml* file to match the following example.</span></span> <span data-ttu-id="bec1a-289">서식 지정 및 간격에 주목 하 고 탭을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-289">Pay close attention to the formatting and spacing and don't use tabs.</span></span>

    ```yaml
    version: '3.4'
    
    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile
        ports:
          - "51000:50001"

      daprfrontend-dapr:
        image: "daprio/daprd:latest"
        command: [ "./daprd", "-app-id", "daprfrontend", "-app-port", "80" ]
        depends_on:
          - daprfrontend
        network_mode: "service:daprfrontend"

      daprbackend:
        image: ${DOCKER_REGISTRY-}daprbackend
        build:
          context: .
          dockerfile: DaprBackEnd/Dockerfile
        ports:
          - "52000:50001"

      daprbackend-dapr:
        image: "daprio/daprd:latest"
        command: [ "./daprd", "-app-id", "daprbackend", "-app-port", "80" ]
        depends_on:
          - daprfrontend
        network_mode: "service:daprbackend"
    ```

    <span data-ttu-id="bec1a-290">업데이트 된 파일에서 `daprfrontend-dapr` 및 서비스를 각각 추가 하 고 `daprbackend-dapr` 사이드카 `daprfrontend` `daprbackend` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-290">In the updated file, we've added `daprfrontend-dapr` and `daprbackend-dapr` sidecars for the `daprfrontend` and `daprbackend` services respectively.</span></span> <span data-ttu-id="bec1a-291">업데이트 된 파일에서 다음 변경 내용에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="bec1a-291">In the updated file, pay close attention to the following changes:</span></span>

    - <span data-ttu-id="bec1a-292">사이드카는 컨테이너 이미지를 사용 합니다 `daprio/daprd:latest` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-292">The sidecars use the `daprio/daprd:latest` container image.</span></span> <span data-ttu-id="bec1a-293">태그를 사용 하는 `latest` 것은 프로덕션 시나리오에 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-293">The use of the `latest` tag isn't recommended for production scenarios.</span></span> <span data-ttu-id="bec1a-294">프로덕션의 경우 특정 버전 번호를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-294">For production, it's better to use a specific version number.</span></span>
    - <span data-ttu-id="bec1a-295">작성 파일에 정의 된 각 서비스에는 네트워크 격리를 위해 자체 네트워크 네임 스페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-295">Each service defined in the Compose file has its own network namespace for network isolation purposes.</span></span> <span data-ttu-id="bec1a-296">사이드카는 `network_mode: "service:..."` 응용 프로그램과 같은 네트워크 네임 스페이스에서 실행 되도록 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-296">The sidecars use `network_mode: "service:..."` to ensure they run in the same network namespace as the application.</span></span> <span data-ttu-id="bec1a-297">이렇게 하면 사이드카 및 응용 프로그램에서를 사용 하 여 통신할 수 있습니다 `localhost` .</span><span class="sxs-lookup"><span data-stu-id="bec1a-297">Doing so allows the sidecar and the application to communicate using `localhost`.</span></span>
    - <span data-ttu-id="bec1a-298">사이드카가 서로 통신할 수 있도록 하기 위해 사이드카가 gRPC 통신을 수신 대기 하는 포트 (기본적으로 50001)가 노출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-298">The ports on which the Dapr sidecars are listening for gRPC communication (by default 50001) must be exposed to allow the sidecars to communicate with each other.</span></span>

1. <span data-ttu-id="bec1a-299">솔루션 (<kbd>f5</kbd> 또는 <kbd>Ctrl + f5</kbd>)을 실행 하 여 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-299">Run the solution (<kbd>F5</kbd> or <kbd>Ctrl+F5</kbd>) to verify that it works as expected.</span></span> <span data-ttu-id="bec1a-300">모든 항목이 올바르게 구성 된 경우 날씨 예측 데이터가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-300">If everything is configured correctly, you should see the weather forecast data:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-result.png" alt-text="날씨 예보 데이터를 보여 주는 최종 솔루션의 스크린샷":::

    <span data-ttu-id="bec1a-302">Docker Compose 및 Visual Studio 2019을 사용 하 여 로컬로 실행 하는 경우 중단점을 설정 하 고 응용 프로그램으로 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-302">Running locally with Docker Compose and Visual Studio 2019, you can set breakpoints and debug into the application.</span></span> <span data-ttu-id="bec1a-303">프로덕션 시나리오의 경우 Kubernetes에서 응용 프로그램을 호스트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-303">For production scenarios, it's recommended to host your application in Kubernetes.</span></span> <span data-ttu-id="bec1a-304">이 책에는 Kubernetes에 배포할 스크립트를 포함 하는 함께 제공 되는 참조 응용 프로그램 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-304">This book includes an accompanying reference application, [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr), that contains scripts to deploy to Kubernetes.</span></span>

    <span data-ttu-id="bec1a-305">이 연습에서 사용 되는 Dapr 서비스 호출 빌딩 블록에 대해 자세히 알아보려면 [6 장](service-invocation.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bec1a-305">To learn more about the Dapr service invocation building block used in this walkthrough, refer to [chapter 6](service-invocation.md).</span></span>

## <a name="summary"></a><span data-ttu-id="bec1a-306">요약</span><span class="sxs-lookup"><span data-stu-id="bec1a-306">Summary</span></span>

<span data-ttu-id="bec1a-307">이 장에서는 d 4의 *드라이브를 테스트할* 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-307">In this chapter, you had an opportunity to *test drive* Dapr.</span></span> <span data-ttu-id="bec1a-308">Dapr .NET SDK를 사용 하 여 Dapr를 .NET 응용 프로그램 플랫폼과 통합 하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-308">Using the Dapr .NET SDK, you saw how Dapr integrates with the .NET application platform.</span></span>

<span data-ttu-id="bec1a-309">첫 번째 예제는 Eapr 상태 관리 빌딩 블록을 사용 하는 간단한 상태 저장 .NET 콘솔 응용 프로그램 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-309">The first example was a simple, stateful, .NET Console application that used the Dapr state management building block.</span></span>

<span data-ttu-id="bec1a-310">두 번째 예제는 Docker에서 실행 되는 다중 컨테이너 응용 프로그램을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-310">The second example involved a multi-container application running in Docker.</span></span> <span data-ttu-id="bec1a-311">Docker Compose에서 Visual Studio를 사용 하 여 모든 .NET 앱에서 사용할 수 있는 익숙한 *F5 디버깅 환경을* 경험 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-311">By using Visual Studio with Docker Compose, you experienced the familiar *F5 debugging experience* available across all .NET apps.</span></span>

<span data-ttu-id="bec1a-312">또한 d 4의 구성 요소 구성 파일에 대해 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-312">You also got a closer look at Dapr component configuration files.</span></span> <span data-ttu-id="bec1a-313">이러한 구성 요소는 Eapr 구성 요소에서 사용 하는 실제 인프라 구현을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-313">They configure the actual infrastructure implementation used by the Dapr building blocks.</span></span> <span data-ttu-id="bec1a-314">네임 스페이스 및 범위를 사용 하 여 특정 환경 및 응용 프로그램에 대 한 구성 요소 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-314">You can use namespaces and scopes to restrict component access to particular environments and applications.</span></span>

<span data-ttu-id="bec1a-315">이후 장에서는 d 4에서 제공 하는 빌딩 블록에 대해 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bec1a-315">In the upcoming chapters, you'll dive deep into the building blocks offered by Dapr.</span></span>

### <a name="references"></a><span data-ttu-id="bec1a-316">참조</span><span class="sxs-lookup"><span data-stu-id="bec1a-316">References</span></span>

- [<span data-ttu-id="bec1a-317">4apr 설명서-시작 하기</span><span class="sxs-lookup"><span data-stu-id="bec1a-317">Dapr documentation - Getting started</span></span>](https://docs.dapr.io/getting-started)
- [<span data-ttu-id="bec1a-318">eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="bec1a-318">eShopOnDapr</span></span>](https://github.com/dotnet-architecture/eShopOnDapr)

> [!div class="step-by-step"]
> <span data-ttu-id="bec1a-319">[이전](dapr-at-20000-feet.md)
> [다음](reference-application.md)</span><span class="sxs-lookup"><span data-stu-id="bec1a-319">[Previous](dapr-at-20000-feet.md)
[Next](reference-application.md)</span></span>
