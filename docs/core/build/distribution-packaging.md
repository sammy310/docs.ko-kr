---
title: .NET Core 배포 패키징
description: 배포를 위해 .NET Core를 패키지하고 이름과 버전을 지정하는 방법에 관해 알아봅니다.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: b961d84053dc41e75e002c8c12419fdef99ded4b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585260"
---
# <a name="net-core-distribution-packaging"></a>.NET Core 배포 패키징

.NET Core를 점점 더 많은 플랫폼에서 사용할 수 있게 되므로 이를 패키지하고 이름과 버전을 지정하는 방법을 알아보는 것이 도움이 됩니다. 이를 통해 패키지 유지 관리자는 사용자가 .NET을 어디서 실행하든 상관없이 일관된 환경을 보장할 수 있습니다. 이 문서는 다음에 해당하는 사용자에게 유용합니다.

* 원본에서 .NET Core를 빌드하려는 사용자
* 결과 레이아웃 또는 생성된 패키지에 영향을 미칠 수 있는 .NET Core CLI 변경을 수행하려는 사용자

## <a name="disk-layout"></a>디스크 레이아웃

설치하면 .NET Core는 파일 시스템에서 다음과 같이 배치된 여러 구성 요소로 구성됩니다.

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
└── shared
    ├── Microsoft.NETCore.App
    │   └── <runtime version>    (5)
    └── Microsoft.AspNetCore.App
        └── <aspnetcore version> (6)
    └── Microsoft.AspNetCore.All
        └── <aspnetcore version> (7)
/
├─usr/share/man/man1
│       └── dotnet.1.gz          (9)
└─usr/bin
        └── dotnet               (10)
```

- (1) **dotnet** 호스트("muxer"라고도 함)는 런타임을 활성화하여 애플리케이션을 시작하고 SDK를 활성화하여 명령을 보내는 두 가지의 고유한 역할을 가지고 있습니다. 호스트는 네이티브 실행 파일(`dotnet.exe`)입니다.

단일 호스트가 있지만 다른 구성 요소는 대부분 버전이 지정된 디렉터리(2,3,5,6)에 있습니다. 여러 버전이 나란히 설치되므로 시스템에 여러 버전이 표시될 수 있습니다.

- (2) **host/fxr/\<fxr 버전>** 에는 호스트에서 사용하는 프레임워크 확인 논리가 포함됩니다. 호스트는 설치된 최신 hostfxr을 사용합니다. hostfxr는 .NET Core 애플리케이션을 실행할 때 적합한 런타임을 선택하는 일을 담당합니다. 예를 들어 .NET Core 2.0.0에 대해 빌드된 애플리케이션을 사용할 수 있는 경우 2.0.5 런타임을 사용합니다. 마찬가지로 hostfxr은 개발 중에 적절한 SDK를 선택합니다.

- (3) **sdk/\<sdk version>** SDK("도구"라고도 함)는 .NET Core 라이브러리 및 애플리케이션을 작성하고 빌드하는 데 사용할 수 있는 관리형 도구 집합입니다. SDK는 .NET Core CLI(명령줄 인터페이스), 관리형 언어 컴파일러, MSBuild 및 연결된 빌드 작업과 대상, NuGet, 새 프로젝트 템플릿 등을 포함합니다.

- (4) **sdk/NuGetFallbackFolder**에는 `dotnet restore` 또는 `dotnet build /t:Restore` 실행처럼 복원 작업 중에 SDK에서 사용하는 NuGet 패키지의 캐시가 포함됩니다.

**공유** 폴더에는 프레임워크가 포함됩니다. 공유 프레임워크는 다른 애플리케이션에서 사용할 수 있도록 중앙 위치에 라이브러리의 집합을 제공합니다.

- (5) **shared/Microsoft.NETCore.App/\<runtime 버전>** 이 프레임워크에는 지원되는 .NET Core 런타임 및 관리 라이브러리가 포함됩니다.

- (6,7) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore 버전>** 에는 ASP.NET Core 라이브러리가 포함됩니다. `Microsoft.AspNetCore.App`에서 라이브러리를 개발하고 .NET Core 프로젝트의 일부로 지원합니다. `Microsoft.AspNetCore.All`의 라이브러리는 타사 라이브러리도 포함하는 상위 집합입니다.

- (8) **LICENSE.txt,ThirdPartyNotices.txt**는 각각 .NET Core에서 사용되는 .NET Core 라이선스 및 타사 라이브러리의 라이선스입니다.

- (9, 10) **dotnet.1.gz, dotnet**`dotnet.1.gz`은 dotnet 설명서 페이지입니다. `dotnet`은 dotnet 호스트(1)의 symlink입니다. 이러한 파일은 시스템 통합을 위해 잘 알려진 위치에 설치됩니다.

## <a name="recommended-packages"></a>권장된 패키지

.NET Core 버전 관리는 런타임 구성 요소 `[major].[minor]` 버전 번호에 기반합니다.
SDK 버전은 동일한 `[major].[minor]`를 사용하고, SDK의 기능 및 패치 의미 체계를 결합한 독립 `[patch]`를 포함합니다.
예: SDK 버전 2.2.302는 2.2 런타임을 지원하는 SDK의 세 번째 기능 릴리스의 두 번째 패치 릴리스입니다. 버전 관리의 작동 방식에 대 한 자세한 내용은 [.NET Core 버전 관리 개요](../versions/index.md)를 참조하세요.

일부 패키지에는 해당 이름의 버전 번호 일부가 포함됩니다. 그러면 특정 버전을 설치할 수 있습니다.
버전의 나머지 부분은 버전 이름에 포함되지 않습니다. 이 때문에 OS 패키지 관리자가 패키지를 업데이트할 수 있습니다(예: 보안 해결을 자동으로 설치). 지원되는 패키지 관리자는 Linux 특정입니다.

다음 표에서는 권장되는 패키지를 보여줍니다.

| name                                    | 예제                | 사용 사례: 설치 ...           | 포함           | 종속성                                   | 버전            |
|-----------------------------------------|------------------------|---------------------------------|--------------------|------------------------------------------------|--------------------|
| dotnet-sdk-[major]                      | dotnet-sdk-2           | 주요 런타임의 최신 sdk    |                    | dotnet-sdk-[major].[latestminor]               | \<sdk version>     |
| dotnet-sdk-[major].[minor]              | dotnet-sdk-2.1         | 특정 런타임의 최신 sdk |                    | dotnet-sdk-[major].[minor].[latest sdk feat]xx | \<sdk version>     |
| dotnet-sdk-[major].[minor].[sdk feat]xx | dotnet-sdk-2.1.3xx     | 특정 sdk 기능 릴리스    | (3),(4)            | aspnetcore-runtime-[major].[minor]             | \<sdk version>     |
| aspnetcore-runtime-[major].[minor]      | aspnetcore-runtime-2.1 | 특정 ASP.NET Core 런타임   | (6),[(7)]          | dotnet-runtime-[major].[minor]                 | \<runtime version> |
| dotnet-runtime-[major].[minor]          | dotnet-runtime-2.1     | 특정 런타임                | (5)                | host-fxr:\<runtime 버전>+                   | \<runtime version> |
| dotnet-host-fxr                         | dotnet-host-fxr        | _dependency_                    | (2)                | host:\<runtime 버전>+                       | \<runtime version> |
| dotnet-host                             | dotnet-host            | _dependency_                    | (1),(8),(9),(10)   |                                                | \<runtime version> |

대부분의 배포는 모든 아티팩트를 원본에서 빌드해야 합니다. 그러면 패키지에 영향을 줍니다.

- `shared/Microsoft.AspNetCore.All`의 타사 라이브러리는 원본에서 쉽게 빌드할 수 없습니다. 따라서 `aspnetcore-runtime` 패키지에서 해당 폴더를 생략합니다.

- `nuget.org`에서 이진 아티팩트를 사용하여 `NuGetFallbackFolder`를 채웁니다. 비워 두어야 합니다.

여러 `dotnet-sdk` 패키지는 `NuGetFallbackFolder`에 동일한 파일을 제공할 수 있습니다. 패키지 관리자를 사용하여 문제를 방지하려면 이러한 파일이 동일해야 합니다(체크섬, 수정 날짜 등).

### <a name="preview-versions"></a>미리 보기 버전

패키지 유지 관리자는 공유 프레임워크 및 SDK의 미리 보기 버전을 제공하도록 결정할 수 있습니다. `dotnet-sdk-[major].[minor].[sdk feat]xx`, `aspnetcore-runtime-[major].[minor]` 또는 `dotnet-runtime-[major].[minor]` 패키지를 사용하여 미리 보기 릴리스를 제공할 수 있습니다. 미리 보기 릴리스의 경우 주요 패키지 버전을 0으로 설정해야 합니다. 이러한 방식으로 패키지의 업그레이드로 최종 릴리스를 설치합니다.

### <a name="patch-packages"></a>패치 패키지

패치 버전의 패키지가 획기적으로 변경될 수 있으므로 패키지 유지 관리자는 _패치 패키지_를 제공하려고 합니다. 이러한 패키지를 사용하면 자동으로 업그레이드되지 않는 특정 패치 버전을 설치할 수 있습니다. (보안) 수정 사항으로 업그레이드되지 않으므로 드문 경우에만 패치 패키지를 사용해야 합니다.

다음 표에서는 권장되는 패키지 및 **패치 패키지**를 보여줍니다.

| name                                           | 예                  | 포함         | 종속성                                              |
|------------------------------------------------|--------------------------|------------------|-----------------------------------------------------------|
| dotnet-sdk-[major]                             | dotnet-sdk-2             |                  | dotnet-sdk-[major].[latest sdk minor]                     |
| dotnet-sdk-[major].[minor]                     | dotnet-sdk-2.1           |                  | dotnet-sdk-[major].[minor].[latest sdk feat]xx            |
| dotnet-sdk-[major].[minor].[sdk feat]xx        | dotnet-sdk-2.1.3xx       |                  | dotnet-sdk-[major].[minor].[latest sdk patch]             |
| **dotnet-sdk-[major].[minor].[patch]**         | dotnet-sdk-2.1.300       | (3),(4)          | aspnetcore-runtime-[major].[minor].[sdk runtime patch]    |
| aspnetcore-runtime-[major].[minor]             | aspnetcore-runtime-2.1   |                  | aspnetcore-runtime-[major].[minor].[latest runtime patch] |
| **aspnetcore-runtime-[major].[minor].[patch]** | aspnetcore-runtime-2.1.0 | (6),[(7)]        | dotnet-runtime-[major].[minor].[patch]                    |
| dotnet-runtime-[major].[minor]                 | dotnet-runtime-2.1       |                  | dotnet-runtime-[major].[minor].[latest runtime patch]     |
| **dotnet-runtime-[major].[minor].[patch]**     | dotnet-runtime-2.1.0     | (5)              | host-fxr:\<runtime 버전>+                              |
| dotnet-host-fxr                                | dotnet-host-fxr          | (2)              | host:\<runtime 버전>+                                  |
| dotnet-host                                    | dotnet-host              | (1),(8),(9),(10) |                                                           |

패치 패키지를 사용하는 대신 패키지 관리자를 사용하여 특정 버전에 패키지를 _고정_합니다. 다른 애플리케이션/사용자에 영향을 주지 않으려면 컨테이너에서 이러한 애플리케이션을 빌드하고 배포합니다.

## <a name="building-packages"></a>패키지 빌드

[dotnet/source-build](https://github.com/dotnet/source-build) 리포지토리는 .NET Core SDK 및 모든 해당 구성 요소의 소스 Tarball을 빌드하는 방법에 대한 지침을 제공합니다. 원본 빌드 리포지토리의 출력은 이 아티클의 첫 번째 섹션에 설명된 레이아웃과 일치합니다.
