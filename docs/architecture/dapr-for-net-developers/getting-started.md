---
title: D 4에서 시작
description: 로컬 개발 환경을 준비 하 고, .NET 응용 프로그램을 사용 하 여 첫 번째 .NET 응용 프로그램을 구축 하기 위한 가이드입니다.
author: amolenk
ms.date: 02/25/2021
ms.openlocfilehash: 1c60f731138911d7d22ff871c9a3849704d81dd6
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874383"
---
# <a name="get-started-with-dapr"></a>D 4에서 시작

처음 두 장에서는 d 4의 기본 개념을 배웠습니다. *시험* 사용에 사용할 시간입니다. 이 장에서는 로컬 개발 환경을 준비 하 고 두 개의 4 개의 기본 .NET 응용 프로그램을 빌드하는 과정을 안내 합니다.

## <a name="install-dapr-into-your-local-environment"></a>로컬 환경에 4Apr 설치

먼저 개발 컴퓨터에 d 4를 설치 합니다. 완료 되 면 [자체 호스팅 모드](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-overview/)에서 4apr 응용 프로그램을 빌드하고 실행할 수 있습니다.

1. [Eapr CLI를 설치](https://docs.dapr.io/getting-started/install-dapr-cli/)합니다. 이 기능을 사용 하면 4 개 인스턴스를 시작, 실행 및 관리할 수 있습니다. 또한 디버깅 지원도 제공 합니다.

1. [Docker Desktop](https://docs.docker.com/get-docker/)을 설치 합니다. Windows에서 실행 하는 경우 **windows 용 Docker 데스크톱이** Linux 컨테이너를 사용 하도록 구성 되어 있는지 확인 합니다.

> [!NOTE]
> 기본적으로 d 4는 Docker 컨테이너를 사용 하 여 최적의 환경을 제공 합니다. Docker 외부에서 Docker를 실행 하려면이 단계를 건너뛰고 [ *슬림* 한 초기화를 실행할](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/)수 있습니다. 이 챕터의 예제에서는 Docker 컨테이너를 사용 해야 합니다.

1. [초기화](https://docs.dapr.io/getting-started/install-dapr/)합니다. 이 단계에서는 최신 Eapr 이진 파일과 컨테이너 이미지를 설치 하 여 개발 환경을 설정 합니다.

1. [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1)를 설치합니다.

이제는 d 4 월이 설치 되었으므로 첫 번째 응용 프로그램을 빌드할 때입니다.

## <a name="build-your-first-dapr-application"></a>첫 번째 4Apr 응용 프로그램 빌드

먼저 [Eapr 상태 관리](state-management.md) 빌딩 블록을 사용 하는 간단한 .net 콘솔 응용 프로그램을 작성 합니다.

### <a name="create-the-application"></a>애플리케이션 만들기

1. 선택한 명령 셸 또는 터미널을 엽니다. [Visual Studio Code](https://code.visualstudio.com/)의 터미널 기능을 고려할 수 있습니다. 응용 프로그램을 빌드하는 데 사용할 루트 폴더로 이동 합니다. 새 .NET 콘솔 응용 프로그램을 만들려면 다음 명령을 입력 합니다.

    ```dotnetcli
    dotnet new console -o DaprCounter
    ```

    명령은 간단한 "헬로 월드" .NET Core 응용 프로그램을 스 캐 폴드 합니다.

1. 그런 다음, 이전 명령으로 만든 새 디렉터리로 이동 합니다.

    ```console
    cd DaprCounter
    ```

1. 명령을 사용 하 여 새로 만든 응용 프로그램을 실행 합니다 `dotnet run` . "헬로 월드!"을 (를) 작성 합니다. 콘솔 화면으로:

    ```dotnetcli
    dotnet run
    ```

### <a name="add-dapr-state-management"></a>Eapr 상태 관리 추가

다음으로는, 프로그램에서 상태 저장 카운터를 구현 하는 데에는 Eapr [상태 관리 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/state-management/state-management-overview/) 을 사용 합니다.

HTTP 및 gRPC에 대 한 4 개의 기본 지원을 사용 하 여 모든 개발 플랫폼에서 4 개의 Api를 호출할 수 있습니다. 그러나 .NET 개발자는 보다 자연스럽 고 직관적인 .NET SDK를 찾을 수 있습니다. 이 클래스는 Eapr Api를 호출 하기 위한 강력한 형식의 .NET 클라이언트를 제공 합니다. 또한 .NET SDK는 ASP.NET Core와 긴밀 하 게 통합 됩니다.

1. 터미널 창에서 `Dapr.Client` 응용 프로그램에 NuGet 패키지를 추가 합니다.

    ```dotnetcli
    dotnet add package Dapr.Client
    ```

    > [!NOTE]
    > 버전 4의 시험판 버전을 사용 하는 경우 `--prerelease` 플래그를 명령에 추가 해야 합니다.

1. 자주 사용 `Program.cs` 하는 편집기에서 파일을 열고 내용을 다음 코드로 업데이트 합니다.

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

    업데이트 된 코드는 다음 단계를 구현 합니다.

    - 처음에는 새 `DaprClient` 인스턴스가 인스턴스화됩니다. 이 클래스를 사용 하 여 사이드카와 상호 작용할 수 있습니다.
    - 상태 저장소에서 `DaprClient.GetStateAsync` 키에 대 한 값을 페치합니다 `counter` . 키가 없으면 기본값 `int` ( `0` )이 반환 됩니다.
    - 그런 다음 코드는를 반복 하 여 `counter` 값을 콘솔에 쓰고 증가 된 값을 상태 저장소에 저장 합니다.

1. D Apr CLI `run` 명령은 응용 프로그램을 시작 합니다. 기본 6Apr 런타임을 호출 하 고 응용 프로그램과 d 4 사이드카를 함께 실행할 수 있습니다. 를 생략 하는 경우에는 `app-id` 응용 프로그램에 대 한 고유한 이름을 생성 합니다. 명령의 마지막 세그먼트는 `dotnet run` .net core 응용 프로그램을 실행 하도록 Capr 런타임에 지시 합니다.

    > [!IMPORTANT]
    > `app-id`상태 관리 빌딩 블록을 사용 하는 경우 항상 명시적 매개 변수를 전달 해야 합니다. 블록은 각 키/값 쌍에 대 한 상태 키의 *접두사로* 응용 프로그램 id 값을 사용 합니다. 응용 프로그램 id가 변경 되 면 이전에 저장 된 상태에 더 이상 액세스할 수 없습니다.

    이제 다음 명령을 사용 하 여 응용 프로그램을 실행 합니다.

    ```console
    dapr run --app-id DaprCounter dotnet run
    ```

    응용 프로그램을 중지 하 고 다시 시작 하십시오. 카운터가 다시 설정 되지 않는 것을 볼 수 있습니다. 대신 이전에 저장 된 상태에서 계속 됩니다. Eapr 빌딩 블록은 응용 프로그램 상태 저장을 설정 합니다.

> [!IMPORTANT]
> 응용 프로그램 예제는 미리 구성 된 상태 구성 요소와 통신 하지만 직접 종속성은 없다는 것을 이해 하는 것이 중요 합니다. D apr는 종속성을 추출 합니다. 잠시 후 간단한 구성 업데이트를 사용 하 여 기본 상태 저장소 구성 요소를 변경할 수 있습니다.

정확 하 게 저장 된 상태는 궁금할 수 있습니다.

## <a name="component-configuration-files"></a>구성 요소 구성 파일

로컬 환경에 대해 처음 초기화할 때 Redis 컨테이너를 자동으로 프로 비전 합니다. 그런 다음 Redis 컨테이너를 구성 요소 구성 파일을 사용 하 여 기본 상태 저장소 구성 요소로 구성 `statestore.yaml` 합니다. 다음은 해당 내용을 확인 하는 것입니다.

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
> 기본 구성 요소 구성 파일은 `$HOME/.dapr/components` Linux/macOS의 폴더와 `%USERPROFILE%\.dapr\components` Windows의 폴더에 저장 됩니다.

이전 구성 요소 구성 파일의 형식을 확인 합니다.

- 각 구성 요소에는 이름이 있습니다. 위의 샘플에서 구성 요소의 이름은 `statestore` 입니다. 첫 번째 코드 예제에서이 이름을 사용 하 여 사용할 구성 요소를 사이드카에 게 알립니다.
- 각 구성 요소 구성 파일에는 `spec` 섹션이 있습니다. `type`구성 요소 유형을 지정 하는 필드가 포함 되어 있습니다. `version`필드는 구성 요소 버전을 지정 합니다. 필드에는 `metadata` 연결 정보 및 기타 설정과 같이 구성 요소에 필요한 정보가 포함 되어 있습니다. 메타 데이터 값은 다양 한 구성 요소 유형에 따라 달라 집니다.

사이드카는 응용 프로그램에 구성 된 모든 Eapr 구성 요소를 사용할 수 있습니다. 그러나 구성 요소에 대 한 액세스 가능성을 제한 하기 위한 아키텍처 근거가 있는 경우 어떻게 되나요? 프로덕션 환경 에서만 실행 되는 Redis 구성 요소를 Aapr 사이드카로 제한 하려면 어떻게 해야 하나요?

이렇게 하려면 `namespace` 프로덕션 환경에 대 한을 정의할 수 있습니다. 이름을로 할 수 있습니다 `production` . 자체 호스팅 모드에서는 환경 변수를 설정 하 여 Eapr 사이드카의 네임 스페이스를 지정 합니다 `NAMESPACE` . 구성 된 경우에는 사이드카가 네임 스페이스와 일치 하는 구성 요소만 로드 합니다. Kubernetes 배포의 경우 Kubernetes 네임 스페이스는 로드 되는 구성 요소를 결정 합니다. 다음 샘플에서는 네임 스페이스에 배치 된 Redis 구성 요소를 보여 줍니다 `production` . `namespace`요소의 선언을 확인 합니다 `metadata` .

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
> Namespaced 구성 요소는 동일한 네임 스페이스에서 실행 되는 응용 프로그램 에서만 액세스할 수 있습니다. Eapr 응용 프로그램이 구성 요소를 로드 하지 못하는 경우 응용 프로그램 네임 스페이스는 구성 요소 네임 스페이스와 일치 하는지 확인 합니다. 응용 프로그램 네임 스페이스는 환경 변수에 저장 되는 자체 호스팅 모드에서는 특히 복잡할 수 있습니다 `NAMESPACE` .

필요한 경우 특정 응용 프로그램으로 구성 요소를 추가로 제한할 수 있습니다. `production`네임 스페이스 내에서 Redis cache에 대 한 액세스를 응용 프로그램 으로만 제한 하는 것이 좋습니다 `DaprCounter` . 구성 요소 구성에서을 지정 하 여이 작업을 수행 `scopes` 합니다. 다음 예제에서는 `statestore` `DaprCounter` 네임 스페이스의 응용 프로그램에 대 한 Redis 구성 요소에 대 한 액세스를 제한 하는 방법을 보여 줍니다 `production` .

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

## <a name="build-a-multi-container-dapr-application"></a>다중 컨테이너 응용 프로그램 빌드

첫 번째 예제에서는 사이드카를 사용 하 여 side-by-side로 실행 되는 간단한 .NET 콘솔 응용 프로그램을 만들었습니다. 그러나 최신 분산 응용 프로그램은 종종 많은 이동 부분으로 구성 됩니다. 독립적인 마이크로 서비스를 동시에 실행할 수 있습니다. 이러한 최신 응용 프로그램은 일반적으로 컨테이너 화 된, Docker Compose 또는 Kubernetes와 같은 컨테이너 오케스트레이션 도구가 필요 합니다.

다음 예제에서는 다중 컨테이너 응용 프로그램을 만듭니다. 또한 서비스 간에 통신 하는 데는 [Eapr 서비스 호출](service-invocation.md) 빌딩 블록을 사용 합니다. 이 솔루션은 웹 API에서 날씨 예측을 검색 하는 웹 응용 프로그램으로 구성 됩니다. 각 사용자는 Docker 컨테이너에서 실행 됩니다. Docker Compose를 사용 하 여 컨테이너를 로컬로 실행 하 고 디버깅 기능을 사용 하도록 설정 합니다.

Core를 사용 하 여 .Net Core 3.1 개발 도구를 설치 했는지 확인 하 고 [.Net Core 개발 도구](https://dotnet.microsoft.com/download/dotnet-core/3.1) 를 설치 했는지 확인 합니다 (이 챕터의 앞부분에서 설명).

또한 **.Net Core 플랫폼 간 개발** 워크 로드가 설치 된 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) 을 사용 하 여이 샘플을 완료 해야 합니다.

### <a name="create-the-application"></a>애플리케이션 만들기

1. Visual Studio 2019에서 **ASP.NET Core 웹 앱** 프로젝트를 만듭니다.

    :::image type="content" source="./media/getting-started/multicontainer-createproject.png" alt-text="새 프로젝트를 만드는 스크린샷":::

1. 프로젝트 `DaprFrontEnd` 및 솔루션의 이름을 `DaprMultiContainer` 다음과 같이 합니다.

    :::image type="content" source="./media/getting-started/multicontainer-configureproject.png" alt-text="새 프로젝트를 구성 하는 스크린샷":::

1. **웹 애플리케이션** 을 선택하여 Razor Pages로 웹 애플리케이션을 만듭니다. Docker 지원 사용을 선택하지 **마세요**. Docker 지원은 나중에 추가하겠습니다.

    :::image type="content" source="./media/getting-started/multicontainer-createwebapp.png" alt-text="새 ASP.NET Core 웹 응용 프로그램을 만드는 스크린샷":::

1. ASP.NET Core Web API 프로젝트를 동일한 솔루션에 추가 하 고 _DaprBackEnd_ 를 호출 합니다. 프로젝트 형식으로 **API** 를 선택 합니다. 기본적으로, 사이드카는 네트워크 경계를 사용 하 여 공용 API에 대 한 액세스를 제한 합니다. 따라서 **HTTPS에 대해 구성** 확인란의 선택을 취소 합니다.

    :::image type="content" source="./media/getting-started/multicontainer-createwebapi.png" alt-text="Web API 만들기 스크린샷":::

### <a name="add-dapr-service-invocation"></a>Eapr 서비스 호출 추가

이제는 Eapr [서비스 호출 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/)을 사용 하 여 서비스 간의 통신을 구성 합니다. 웹 앱이 web API에서 날씨 예측을 검색할 수 있도록 설정 합니다. 서비스 호출 구성 요소는 다양 한 이점을 제공 합니다. 여기에는 서비스 검색, 자동 다시 시도, mTLS를 사용 하는 메시지 암호화 및 향상 된 관찰성 포함 됩니다. Dapr 사이드카에서 서비스 호출 API를 호출 하려면 Dapr .NET SDK를 사용 합니다.

1. Visual Studio에서 패키지 관리자 콘솔 (**도구 > NuGet 패키지 관리자 > 패키지 관리자 콘솔**)을 열고 `DaprFrontEnd` 이 기본 프로젝트 인지 확인 합니다. 콘솔에서 `Dapr.AspNetCore` NuGet 패키지를 프로젝트에 추가 합니다.

    ```powershell
    Install-Package Dapr.AspNetCore
    ```

    > [!NOTE]
    > 시험판에 있는 버전을 대상으로 하는 경우 `Dapr.AspNetCore` 플래그를 지정 해야 `-Prerelease` 합니다.

1. 프로젝트에서 `DaprFrontEnd` *시작 .cs* 파일을 열고 `ConfigureServices` 메서드를 다음 코드로 바꿉니다.

    ```csharp
    // This method gets called by the runtime. Use this method to add services to the container.
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddControllers().AddDapr();
        services.AddRazorPages();
    }
    ```

    호출은 `AddDapr` `DaprClient` ASP.NET Core 종속성 주입 시스템에 클래스를 등록 합니다. 클라이언트를 등록 하면 이제 `DaprClient` 서비스 코드에 인스턴스를 삽입 하 여 사이드카, 빌딩 블록 및 구성 요소와 통신할 수 있습니다.

1. *WeatherForecast* 라는 새 c # 클래스 파일을 프로젝트에 추가 합니다 `DaprFrontEnd` .

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

1. *Pages* 폴더에서 *Index. cshtml* 파일을 열고 해당 내용을 다음 코드로 바꿉니다.

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

    생성자에 클래스를 삽입 하 여 웹 앱에 Eapr 기능을 추가 합니다 `DaprClient` `IndexModel` . 메서드에서는 `OnGet` Eapr 서비스 호출 빌딩 블록을 사용 하 여 API 서비스를 호출 합니다. `OnGet`메서드는 사용자가 홈 페이지를 방문할 때마다 호출 됩니다. 메서드를 사용 하 여 `DaprClient.InvokeMethodAsync` `weatherforecast` 서비스의 메서드를 호출 합니다 `daprbackend` . 응용 프로그램 ID로 사용할 웹 API를 구성 하는 경우에는 해당 `daprbackend` 응용 프로그램 ID를 사용 하 여, 마지막으로 서비스 응답은 보기 데이터에 저장 됩니다.

1. *Pages* 폴더에 있는 *Index. cshtml* 파일의 내용을 다음 코드로 바꿉니다. 사용자에 게 보기 데이터에 저장 된 날씨 예측을 표시 합니다.

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

### <a name="add-container-support"></a>컨테이너 지원 추가

이 예제의 마지막 부분에서는 컨테이너 지원을 추가 하 고 Docker Compose를 사용 하 여 솔루션을 실행 합니다.

1. 프로젝트를 마우스 오른쪽 단추로 클릭 `DaprFrontEnd` 하 고   >  **컨테이너 Orchestrator 지원** 추가를 선택 합니다. **컨테이너 Orchestrator 지원 추가** 대화 상자가 나타납니다.

    :::image type="content" source="./media/getting-started/multicontainer-addorchestrator.png" alt-text="컨테이너 orchestrator 지원 추가 스크린샷":::

    **Docker Compose** 를 선택합니다.

1. 다음 대화 상자에서 대상 OS로 **Linux** 를 선택 합니다.

    :::image type="content" source="./media/getting-started/multicontainer-targetos.png" alt-text="Docker 대상 OS 선택 스크린샷":::

    Visual Studio는 솔루션의 **docker 작성** 폴더에 *docker-compose.ci.build.yml* 파일과 *dockerignore* 파일을 만듭니다.

    :::image type="content" source="./media/getting-started/multicontainer-dockersolution.png" alt-text="Docker 작성 프로젝트의 스크린샷":::

    *Docker-compose.ci.build.yml* 파일에는 다음과 같은 내용이 있습니다.

    ```yaml
    version: "3.4"

    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile
    ```

    *.dockerignore* 파일에는 Docker에서 컨테이너에 포함하지 않을 파일 형식과 확장명이 포함되어 있습니다. 이러한 파일은 개발 환경 및 소스 제어와 연결 되며 배포 중인 앱 또는 서비스가 아닙니다.

    *DaprFrontEnd* 프로젝트 디렉터리의 루트에 새 *dockerfile* 이 생성 되었습니다. *Dockerfile* 은 이미지를 빌드하는 데 사용 되는 일련의 명령입니다. 자세한 내용은 [Dockerfile 참조](https://docs.docker.com/engine/reference/builder)를 참조 하세요.

    *Dockerfile* 에는 yaml이 포함 됩니다.

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

    앞의 *Dockerfile* 은 호출 될 때 다음 단계를 순차적으로 수행 합니다.

    1. 이미지를 끌어온 `mcr.microsoft.com/dotnet/aspnet:3.1` 다음 이름을로 `base` 합니다.
    1. 작업 디렉터리를 */proapp* 으로 설정 합니다.
    1. 포트 `80` 및를 노출 `443` 합니다.
    1. 이미지를 끌어온 `mcr.microsoft.com/dotnet/sdk:3.1` 다음 이름을로 `build` 합니다.
    1. 작업 디렉터리를 */src* 로 설정 합니다.
    1. _DaprFrontEnd/DaprFrontEnd_ 를 *DaprFrontEnd/* 라는 새 디렉터리에 복사 합니다.
    1. [`dotnet restore`](../../core/tools/dotnet-restore.md)프로젝트에서를 호출 합니다.
    1. 루트 디렉터리에서 이미지의 루트에 모든 항목을 복사 합니다.
    1. 작업 디렉터리를 _/src/DaprFrontEnd_ 로 설정 합니다.
    1. [`dotnet build`](../../core/tools/dotnet-build.md)프로젝트에서를 호출 합니다.
        - **릴리스** 구성의 대상을 지정 하 고 */app/build* 에 출력 합니다.
    1. 기존 기본 이미지에서 새 빌드 단계를 초기화 `build` 하 고 이름을로 만듭니다 `publish` .
    1. `dotnet publish`프로젝트에서를 호출 합니다.
        - **릴리스** 구성 대상 지정 및 */app/publish* 로 출력
    1. 기존 기본 이미지에서 새 빌드 단계를 초기화 `publish` 하 고 이름을로 만듭니다 `final` .
    1. 작업 디렉터리를 */proapp* 으로 설정 합니다.
    1. 이미지의 `/app/publish` 디렉터리를 `publish` 이미지의 루트에 복사 `final` 합니다.
    1. 진입점을 이미지로 설정 하 고을 인수로 `dotnet` 전달 합니다 `DaprFrontEnd.dll` .

1. `DaprBackEnd`Web API 프로젝트에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고   >  **컨테이너 Orchestrator 지원** 추가를 선택 합니다. **Docker Compose** 를 선택 하 고 대상 OS로 **Linux** 를 다시 선택 합니다.

    _DaprBackEnd_ 프로젝트 디렉터리의 루트에 새 *dockerfile* 이 생성 되었습니다. *Dockerfile* 에는 다음 yaml이 포함 되어 있습니다.

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

    *Docker-compose.ci.build.yml* 파일을 다시 열고 내용을 확인 합니다. Visual Studio에서 **Docker Compose** 파일을 업데이트 했습니다. 이제 두 서비스 모두 포함 됩니다.

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

1. 컨테이너 화 된 응용 프로그램 내에서 Eapr 빌딩 블록을 사용 하려면 작성 파일에 Eapr 사이드카 컨테이너를 추가 해야 합니다. 다음 예제와 일치 하도록 *docker-compose.ci.build.yml* 파일의 내용을 신중 하 게 업데이트 합니다. 서식 지정 및 간격에 주목 하 고 탭을 사용 하지 않습니다.

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

    업데이트 된 파일에서 `daprfrontend-dapr` 및 서비스를 각각 추가 하 고 `daprbackend-dapr` 사이드카 `daprfrontend` `daprbackend` 합니다. 업데이트 된 파일에서 다음 변경 내용에 유의 하세요.

    - 사이드카는 컨테이너 이미지를 사용 합니다 `daprio/daprd:latest` . 태그를 사용 하는 `latest` 것은 프로덕션 시나리오에 권장 되지 않습니다. 프로덕션의 경우 특정 버전 번호를 사용 하는 것이 좋습니다.
    - 작성 파일에 정의 된 각 서비스에는 네트워크 격리를 위해 자체 네트워크 네임 스페이스가 있습니다. 사이드카는 `network_mode: "service:..."` 응용 프로그램과 같은 네트워크 네임 스페이스에서 실행 되도록 하는 데 사용 됩니다. 이렇게 하면 사이드카 및 응용 프로그램에서를 사용 하 여 통신할 수 있습니다 `localhost` .
    - 사이드카가 서로 통신할 수 있도록 하기 위해 사이드카가 gRPC 통신을 수신 대기 하는 포트 (기본적으로 50001)가 노출 되어야 합니다.

1. 솔루션 (<kbd>f5</kbd> 또는 <kbd>Ctrl + f5</kbd>)을 실행 하 여 예상 대로 작동 하는지 확인 합니다. 모든 항목이 올바르게 구성 된 경우 날씨 예측 데이터가 표시 되어야 합니다.

    :::image type="content" source="./media/getting-started/multicontainer-result.png" alt-text="날씨 예보 데이터를 보여 주는 최종 솔루션의 스크린샷":::

    Docker Compose 및 Visual Studio 2019을 사용 하 여 로컬로 실행 하는 경우 중단점을 설정 하 고 응용 프로그램으로 디버그할 수 있습니다. 프로덕션 시나리오의 경우 Kubernetes에서 응용 프로그램을 호스트 하는 것이 좋습니다. 이 책에는 Kubernetes에 배포할 스크립트를 포함 하는 함께 제공 되는 참조 응용 프로그램 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)가 포함 되어 있습니다.

    이 연습에서 사용 되는 Dapr 서비스 호출 빌딩 블록에 대해 자세히 알아보려면 [6 장](service-invocation.md)을 참조 하세요.

## <a name="summary"></a>요약

이 장에서는 d 4의 *드라이브를 테스트할* 수 있습니다. Dapr .NET SDK를 사용 하 여 Dapr를 .NET 응용 프로그램 플랫폼과 통합 하는 방법을 살펴보았습니다.

첫 번째 예제는 Eapr 상태 관리 빌딩 블록을 사용 하는 간단한 상태 저장 .NET 콘솔 응용 프로그램 이었습니다.

두 번째 예제는 Docker에서 실행 되는 다중 컨테이너 응용 프로그램을 포함 합니다. Docker Compose에서 Visual Studio를 사용 하 여 모든 .NET 앱에서 사용할 수 있는 익숙한 *F5 디버깅 환경을* 경험 했습니다.

또한 d 4의 구성 요소 구성 파일에 대해 자세히 살펴봅니다. 이러한 구성 요소는 Eapr 구성 요소에서 사용 하는 실제 인프라 구현을 구성 합니다. 네임 스페이스 및 범위를 사용 하 여 특정 환경 및 응용 프로그램에 대 한 구성 요소 액세스를 제한할 수 있습니다.

이후 장에서는 d 4에서 제공 하는 빌딩 블록에 대해 자세히 살펴보겠습니다.

### <a name="references"></a>참조

- [4apr 설명서-시작 하기](https://docs.dapr.io/getting-started)
- [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)

> [!div class="step-by-step"]
> [이전](dapr-at-20000-feet.md)
> [다음](reference-application.md)
