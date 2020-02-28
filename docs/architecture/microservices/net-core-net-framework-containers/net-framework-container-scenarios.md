---
title: Docker 컨테이너에 대해 .NET Framework를 선택하는 경우
description: 컨테이너화된 .NET 애플리케이션용 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET Framework를 선택하는 경우
ms.date: 01/30/2020
ms.openlocfilehash: dfb1e8883fc9c3d9235672bc2885858bfb64afa5
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501969"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Docker 컨테이너에 대해 .NET Framework를 선택하는 경우

.NET Core는 새 애플리케이션 및 애플리케이션 패턴에 상당한 이점을 제공하는 반면, .NET Framework는 계속해서 다양한 기존 시나리오에 적합한 선택 사양이 될 것입니다.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>기존 애플리케이션을 Windows Server 컨테이너로 직접 마이그레이션

마이크로 서비스를 만들지 않는 경우에도 Docker 컨테이너를 사용하여 배포를 단순화하려고 할 수 있습니다. 예를 들어 Docker를 사용하여 DevOps 워크플로를 향상시키려는 경우, 컨테이너를 통해 더 효율적으로 격리된 테스트 환경을 제공하고, 프로덕션 환경으로 이동할 때 종속성 누락으로 인한 배포 문제를 제거할 수 있습니다. 이러한 경우 모놀리식 애플리케이션을 배포하더라도 현재 .NET Framework 애플리케이션에 Docker 및 Windows 컨테이너를 사용하는 것이 좋습니다.

이 시나리오에서 대부분의 경우 기존 애플리케이션을 .NET Core로 마이그레이션할 필요가 없습니다. 즉 기존 .NET Framework가 포함된 Docker 컨테이너를 사용하면 됩니다. 그러나 ASP.NET Core에서 새 웹 서비스를 작성하는 것과 같이 기존 애플리케이션을 확장할 때 .NET Core를 사용하는 것이 좋습니다.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>.NET Core에 사용할 수 없는 타사 .NET 라이브러리 또는 NuGet 패키지 사용

타사 라이브러리는 [.NET 표준](../../../standard/net-standard.md)을 빠르게 수용하여 .NET Core를 포함한 모든 .NET 계열에서 코드 공유를 사용할 수 있게 합니다. .NET Standard 2.0 이상에서는 서로 다른 프레임워크 간 API 노출 호환성이 크게 확대되었습니다. 게다가 .NET Core 2.x 및 최신 애플리케이션은 기존 .NET Framework 라이브러리를 직접 참조할 수도 있습니다([.NET Standard 2.0을 지원하는 .NET Framework 4.6.1](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#net-framework-461-supporting-net-standard-20) 참조).

또한 [Windows 호환성 팩](../../../core/porting/windows-compat-pack.md)은 Windows의 .NET Standard 2.0에 사용할 수 있는 API 노출을 확장합니다. 이 팩을 사용하면 수정 사항이 거의 없거나 전혀 없이 Windows에서 실행하도록 대부분의 기존 코드를 .NET Standard 2.x에 다시 컴파일할 수 있습니다.

그러나 .NET Standard 2.0 및 .NET Core 2.1 이후의 뛰어난 발전에도 불구하고 특정 NuGet 패키지에서 Windows를 실행해야 하고 .NET Core를 지원하지 않는 경우가 있을 수도 있습니다. 이러한 패키지가 애플리케이션에 매우 중요한 경우 Windows 컨테이너에서 .NET Framework를 사용해야 합니다.

## <a name="using-net-technologies-not-available-for-net-core"></a>.NET Core에 사용할 수 없는 .NET 기술 사용

일부 .NET Framework 기술은 현재 버전의 .NET Core(이 문서 작성 시점을 기준으로 버전 3.1)에서 사용할 수 없습니다. 그 중 일부는 이후 릴리스에서 사용할 수 있겠지만, 다른 일부는 .NET Core가 대상으로 하는 새 애플리케이션 패턴에 맞지 않으며 사용하지 못할 수도 있습니다.

다음 목록에서는 .NET Core 3.1에서 사용할 수 없는 대부분의 기술을 보여 줍니다.

- ASP.NET Web Forms. 이 기술은 .NET Framework에서만 사용할 수 있습니다. 현재 .NET Core에 ASP.NET Web Forms를 적용할 계획은 없습니다.

- WCF 서비스. .NET Core에서 WCF 서비스를 사용할 수 있는 [WCF-클라이언트 라이브러리](https://github.com/dotnet/wcf)가 있더라도(2020년 2월 기준) WCF 서버 구현은 .NET Framework에서만 사용할 수 있습니다. 이 시나리오는 .NET Core의 향후 릴리스에 대해 고려할 수 있으며, 이 경우 [Windows 호환성 팩](../../../core/porting/windows-compat-pack.md)에 일부 API를 포함하도록 고려되고 있습니다.

- 워크플로 관련 서비스. Windows WF(Workflow Foundation), 워크플로 서비스(단일 서비스의 WCF + WF) 및 WCF Data Services(이전의 ADO.NET Data Services)는 .NET Framework에서만 사용할 수 있습니다. 현재 .NET Core로 가져올 계획은 없습니다.

공식 [.NET Core 로드맵](https://github.com/dotnet/core/blob/master/roadmap.md)에 나열된 기술 외에도 다른 기능이 .NET Core 또는 새로운 [통합 .NET 플랫폼](https://devblogs.microsoft.com/dotnet/introducing-net-5/)에 이식될 수도 있습니다. 의견이 반영될 수 있도록 GitHub 토론에 참여하는 것을 고려할 수 있습니다. 누락된 내용이 있다고 생각되는 경우 [dotnet/runtime](https://github.com/dotnet/runtime/issues/new) GitHub 리포지토리에서 새 이슈를 제기하세요.

## <a name="using-a-platform-or-api-that-doesnt-support-net-core"></a>.NET Core를 지원하지 않는 플랫폼 또는 API 사용

일부 Microsoft 및 타사 플랫폼에서는 .NET Core를 지원하지 않습니다. 예를 들어 일부 Azure 서비스는 .NET Core에서 아직 사용할 수 없는 SDK를 제공합니다. 대부분의 Azure SDK는 궁극적으로 .NET Core/Standard로 이식되어야 하지만 여러 가지 이유로 그렇지 않을 수도 있습니다. [Azure SDK 최신 릴리스](https://azure.github.io/azure-sdk/releases/latest/index.html) 페이지에서 사용 가능한 Azure SDK를 확인할 수 있습니다.

그동안 Azure의 플랫폼 또는 서비스에서 여전히 클라이언트 API를 통해 .NET Core를 지원하지 않는 경우에는 Azure 서비스 또는 .NET Framework의 클라이언트 SDK에서 동등한 REST API를 사용할 수 있습니다.

### <a name="additional-resources"></a>추가 자료

- **.NET Core 가이드** \
  [https://docs.microsoft.com/dotnet/core/index](../../../core/index.md)

- **.NET Framework에서 .NET Core로 이식** \
  [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)

- **Docker 가이드의 .NET Core** \
  [https://docs.microsoft.com/dotnet/core/docker/introduction](../../../core/docker/introduction.md)

- **.NET 구성 요소 개요** \
  [https://docs.microsoft.com/dotnet/standard/components](../../../standard/components.md)

>[!div class="step-by-step"]
>[이전](net-core-container-scenarios.md)
>[다음](container-framework-choice-factors.md)
