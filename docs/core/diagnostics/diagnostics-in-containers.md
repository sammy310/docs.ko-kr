---
title: 컨테이너에서 진단 정보 수집
description: 이 문서에서는 Docker 컨테이너에서 .NET Core 진단 도구를 사용하는 방법에 대해 알아봅니다.
ms.date: 09/01/2020
ms.openlocfilehash: e57f3696433bbf6f35b2e3e5d1e72ae8b1e3eeb3
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91450838"
---
# <a name="collect-diagnostics-in-containers"></a>컨테이너에서 진단 정보 수집

다른 시나리오에서 .NET Core 문제를 진단하는 데 유용한 진단 도구를 Docker 컨테이너에서도 사용할 수 있습니다. 다만 일부 도구를 컨테이너에서 사용하려면 특별한 단계가 필요합니다. 이 문서에서는 Docker 컨테이너에서 성능 추적을 수집하고 덤프를 수집하는 도구를 사용하는 방법을 설명합니다.

## <a name="using-net-core-cli-tools-in-a-container"></a>컨테이너에서 .NET Core CLI 도구 사용

**이 문서의 적용 대상: ✔️** .NET Core 3.0 SDK 이상 버전

.NET Core 전역 CLI 진단 도구([`dotnet-counters`](dotnet-counters.md), [`dotnet-dump`](dotnet-dump.md), [`dotnet-gcdump`](dotnet-gcdump.md), [`dotnet-trace`](dotnet-trace.md))는 다양한 환경에서 작동하도록 설계되었으며, Docker 컨테이너에서 직접 작동해야 합니다. 따라서 이러한 도구는 컨테이너에서 .NET Core 3.0 이상(또는 `dotnet-gcdump`의 경우 3.1 이상)을 대상으로 하는 .NET Core 시나리오에서 진단 정보를 수집하는 기본 방법입니다.

컨테이너에서 이러한 도구를 사용할 때 복잡한 점은 이러한 도구는 .NET Core SDK와 함께 설치되는데, 많은 Docker 컨테이너가 .NET Core SDK가 없는 상태에서 실행된다는 것뿐입니다. 이 문제의 한 가지 간단한 해결책은 초기 Docker 이미지에 도구를 설치하는 것입니다. .NET Core SDK가 실행될 필요는 없고 설치만 되어 있으면 됩니다. 따라서 빌드 단계(.NET Core SDK가 있는)에서 도구를 설치한 다음 이진 파일을 최종 이미지에 복사하는 [다단계 빌드](https://docs.docker.com/develop/develop-images/multistage-build/)를 사용하여 Dockefile을 만들 수 있습니다. 이 방법의 유일한 단점은 Docker 이미지 크기가 늘어난다는 것입니다.

```dockerfile
# In build stage
# Install desired .NET CLI diagnostics tools
RUN dotnet tool install --tool-path /tools dotnet-trace
RUN dotnet tool install --tool-path /tools dotnet-counters
RUN dotnet tool install --tool-path /tools dotnet-dump

...

# In final stage
# Copy diagnostics tools
WORKDIR /tools
COPY --from=build /tools .
```

또는 CLI 도구를 설치하기 위해 필요한 경우 컨테이너에 .NET Core SDK를 설치할 수 있습니다. .NET Core SDK를 설치하면 .NET Core 런타임을 다시 설치해야 하는 부작용이 있습니다. 따라서 컨테이너에 있는 런타임과 일치하는 SDK 버전을 설치해야 합니다.

### <a name="using-net-core-global-cli-tools-in-a-sidecar-container"></a>사이드카 컨테이너에서 .NET Core 전역 CLI 도구 사용

.NET Core 전역 CLI 진단 도구를 사용하여 다른 컨테이너의 프로세스를 진단하려면 다음과 같은 추가 요구 사항을 염두에 두어야 합니다.

1. 사이드카 컨테이너의 도구가 대상 컨테이너의 프로세스에 액세스할 수 있도록 컨테이너가 [프로세스 네임스페이스를 공유](https://docs.docker.com/engine/reference/run/#pid-settings---pid)해야 합니다.
2. .NET Core 전역 CLI 진단 도구는 .NET Core 런타임이 /tmp 디렉터리에 쓰는 파일에 액세스해야 하므로 볼륨 탑재를 통해 대상 컨테이너와 사이드카 컨테이너가 /tmp 디렉터리를 공유해야 합니다. 이것은 예를 들어 컨테이너가 공통 [볼륨](https://docs.docker.com/storage/volumes/#create-and-manage-volumes) 또는 Kubernetes [emptyDir](https://kubernetes.io/docs/concepts/storage/volumes/#emptydir) 볼륨을 공유하도록 하면 가능합니다. /tmp 디렉터리를 공유하지 않고 사이드카 컨테이너에서 진단 도구를 사용하려고 하면 “호환되는 .NET 런타임 실행 중 아님”이라는 프로세스에 대한 오류가 표시됩니다.

## <a name="using-perfcollect-in-a-container"></a>컨테이너에서 `PerfCollect` 사용

**이 도구의 적용 대상: ✔️** .NET Core 2.1 이상 버전

[`PerfCollect`](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/linux-performance-tracing.md) 스크립트는 성능 추적을 수집하는 데 유용하며, .NET Core 3.0 이전에 추적을 수집하는 데 권장되는 도구입니다. 컨테이너에서 `PerfCollect`를 사용하는 경우 다음 요구 사항을 염두에 두세요.

1. `PerfCollect`는 `perf` 도구를 실행하기 위해 [`SYS_ADMIN` 기능](https://man7.org/linux/man-pages/man7/capabilities.7.html)이 필요하므로 컨테이너가 [해당 기능으로 시작](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities)해야 합니다.
2. `PerfCollect`는 프로파일링하는 앱이 시작하기 전에 일부 환경 변수를 설정해야 합니다. 이러한 변수는 [Dockerfile](https://docs.docker.com/engine/reference/builder/#env)에서 또는 [컨테이너를 시작](https://docs.docker.com/engine/reference/run/#env-environment-variables)할 때 설정할 수 있습니다. 이러한 변수는 일반적인 프로덕션 환경에서 설정하면 안 되므로 프로파일링될 컨테이너를 시작할 때 추가하는 것이 일반적입니다. PerfCollect에 필요한 두 변수는 다음과 같습니다.
    1. COMPlus_PerfMapEnabled=1
    1. COMPlus_EnableEventLog=1

### <a name="using-perfcollect-in-a-sidecar-container"></a>사이드카 컨테이너에서 `PerfCollect` 사용

한 컨테이너에서 `PerfCollect`를 실행하여 다른 컨테이너의 .NET Core 프로세스를 프로파일링하려는 경우 다음 차이를 제외하면 환경은 거의 동일합니다.

1. 위에 언급한 환경 변수(COMPlus_PerfMapEnabled 및 COMPlus_EnableEventLog)를 대상 컨테이너(`PerfCollect`를 실행하는 컨테이너가 아님)에 설정해야 합니다.
2. `PerfCollect`를 실행하는 컨테이너에는 `SYS_ADMIN` 기능이 있어야 합니다(대상 컨테이너가 아님).
3. 두 컨테이너는 [프로세스 네임스페이스를 공유](https://docs.docker.com/engine/reference/run/#pid-settings---pid)해야 합니다.

## <a name="using-createdump-in-a-container"></a>컨테이너에서 `createdump` 사용

**이 도구의 적용 대상: ✔️** .NET Core 2.1 이상 버전

`dotnet-dump`의 대안인 [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md)를 사용하여 네이티브 및 관리되는 정보를 모두 포함하는 코어 덤프를 Linux에서 만들 수 있습니다. `createdump` 도구는 .NET Core 런타임과 함께 설치되며 libcoreclr.so 옆에(일반적으로 “/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]”에) 있습니다. 이 도구는 [`SYS_PTRACE` 기능](https://man7.org/linux/man-pages/man7/capabilities.7.html)이 필요하다는 점만 제외하면 컨테이너에서도 컨테이너화되지 않은 Linux 환경에서와 동일하게 작동하므로 Docker 컨테이너는 [해당 기능으로 시작](https://docs.docker.com/engine/reference/run/#runtime-privilege-and-linux-capabilities)해야 합니다.

### <a name="using-createdump-in-a-sidecar-container"></a>사이드카 컨테이너에서 `createdump` 사용

`createdump`를 사용하여 다른 컨테이너의 프로세스에서 덤프를 만드려는 경우 다음 차이를 제외하면 환경은 거의 동일합니다.

1. `createdump`를 실행하는 컨테이너에는 `SYS_PTRACE` 기능이 있어야 합니다(대상 컨테이너가 아님).
2. 두 컨테이너는 [프로세스 네임스페이스를 공유](https://docs.docker.com/engine/reference/run/#pid-settings---pid)해야 합니다.
