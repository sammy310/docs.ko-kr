---
title: Docker 컨테이너에 대해 .NET 5를 선택하는 경우
description: 컨테이너화된 .NET 애플리케이션용 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET을 선택하는 경우
ms.date: 01/13/2021
ms.openlocfilehash: 61909c91d795582af499456c65ae0d7b4f2911e2
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189280"
---
# <a name="when-to-choose-net-for-docker-containers"></a>Docker 컨테이너에 대해 .NET을 선택하는 경우

.NET 5는 모듈성 있고 간단하므로 컨테이너에 매우 적합합니다. 컨테이너를 배포 및 시작할 때 이미지 크기는 .NET Framework보다 .NET 5에서 훨씬 작습니다. 반면, .NET Framework를 컨테이너에 사용하려면 이미지가 Windows Server Core 이미지를 기반으로 해야 하는데, .NET 5에 사용하는 Windows Nano Server 또는 Linux 이미지보다 훨씬 무겁습니다.

또한 .NET 5는 여러 플랫폼에 적용되므로 Linux나 Windows 컨테이너 이미지를 통해 서버 앱을 배포할 수 있습니다. 그러나 기존 .NET Framework를 사용하는 경우 Windows Server Core 기반의 이미지만 배포할 수 있습니다.

.NET 5를 선택하는 이유에 관한 자세한 설명은 다음과 같습니다.

## <a name="developing-and-deploying-cross-platform"></a>플랫폼 간 개발 및 배포

분명히, Docker에서 지원하는 여러 플랫폼(Linux 및 Windows)에서 실행할 수 있는 애플리케이션(웹앱 또는 서비스)이 목표라면 .NET 5가 올바른 선택 사항입니다. .NET Framework는 Windows만 지원하기 때문입니다.

.NET 5는 개발 플랫폼으로 macOS도 지원합니다. 그러나 Docker 호스트에 컨테이너를 배포할 때는 (현재) 호스트가 Linux 또는 Windows를 기반으로 해야 합니다. 예를 들어 개발 환경에서는 Mac에서 실행되는 Linux VM을 사용할 수 있습니다.

[Visual Studio](https://www.visualstudio.com/vs/)는 Windows를 위한 IDE(통합 개발 환경)를 제공하며 Docker 개발을 지원합니다.

[Mac용 Visual Studio](https://www.visualstudio.com/vs/visual-studio-mac/)는 Xamarin Studio에서 진화한 IDE로, macOS에서 실행되고 Docker 기반 애플리케이션 개발을 지원합니다. 해당 도구는 Mac 머신에서 작업 중인 개발자가 강력한 IDE도 사용하려는 경우에 권장되는 선택 사항입니다.

또한 macOS, Linux 및 Windows에서 [Visual Studio Code](https://code.visualstudio.com/)를 사용할 수 있습니다. Visual Studio Code는 IntelliSense 및 디버깅을 포함하여 .NET 5를 완벽하게 지원합니다. VS Code는 간단한 편집기이므로 머신에서 컨테이너화된 앱을 개발할 때 Docker CLI 및 [.NET CLI](../../../core/tools/index.md)와 함께 사용할 수 있습니다. Sublime, Emacs, vi 같은 대부분의 타사 편집기와 IntelliSense 지원을 제공하는 오픈 소스 OmniSharp 프로젝트에서도 .NET 5를 대상으로 지정할 수 있습니다.

IDE 및 편집기 외에도 지원되는 모든 플랫폼에 [.NET CLI](../../../core/tools/index.md)를 사용할 수 있습니다.

## <a name="using-containers-for-new-green-field-projects"></a>새("그린-필드") 프로젝트에 컨테이너 사용

컨테이너는 아키텍처 패턴을 따르는 웹앱 또는 서비스를 컨테이너화하는 데 사용할 수 있지만 일반적으로 마이크로 서비스 아키텍처와 연계하여 사용됩니다. Windows 컨테이너에 .NET Framework를 사용할 수 있지만, .NET 5는 모듈성 있고 간단하므로 컨테이너와 마이크로 서비스 아키텍처에 매우 적합합니다. 컨테이너를만들어 배포할 때 이미지 크기는 .NET Framework보다 .NET Core에서 훨씬 작습니다.

## <a name="create-and-deploy-microservices-on-containers"></a>컨테이너에서 마이크로 서비스 만들기 및 배포

기존 .NET Framework를 통해 일반 프로세스를 사용하여 컨테이너 없는 마이크로 서비스 기반 애플리케이션을 구축할 수 있습니다. 이렇게 하면 .NET Framework가 이미 설치되어 프로세스 간에 공유되기 때문에 프로세스가 가볍고 신속하게 시작됩니다. 그러나 컨테이너를 사용할 경우 기존 .NET Framework의 이미지가 Windows Server Core를 기반으로 할 수 있어 컨테이너 위의 마이크로 서비스 방식에 대해서는 너무 무거워집니다. 그러나 팀은 .NET Framework 사용자의 환경을 개선할 수 있는 기회도 찾고 있습니다. 최근 [Windows Server Core 컨테이너 이미지의 크기가 40% 이상 작아졌습니다](https://devblogs.microsoft.com/dotnet/we-made-windows-server-core-container-images-40-smaller).

한편, 컨테이너 기반의 마이크로 서비스 중심 시스템을 수용하려면 .NET 5가 가장 적합합니다. .NET 5는 간단하기 때문입니다. 또한 Linux나 Windows Nano Server의 경우 관련 컨테이너 이미지가 간결하고 작아 컨테이너를 가볍고 빠르게 시작할 수 있습니다.

마이크로 서비스는 가능한 작아야 합니다. 즉 신속하게 가공되고 작은 공간을 사용해야 하며 경계가 지정된 컨텍스트가 적어야 하고(DDD([도메인 기반 디자인](https://en.wikipedia.org/wiki/Domain-driven_design)) 확인) 우려되는 부분이 적어야 하며 신속하게 시작 및 중지할 수 있어야 합니다. 해당 요구 사항을 충족하기 위해 .NET 5 컨테이너 이미지와 같이 신속하게 인스턴스화할 수 있는 작은 컨테이너 이미지를 사용하는 것이 좋습니다.

마이크로 서비스 아키텍처를 사용하면 서비스 경계를 벗어나 여러 기술을 융합할 수 있습니다. 해당 접근 방식을 사용하면 Node.js, Python, Java, GoLang 또는 그 밖의 기술로 개발된 다른 마이크로 서비스나 서비스와 연계 작동하는 새 마이크로 서비스를 위해 .NET 5로의 점진적 마이그레이션이 가능합니다.

## <a name="deploying-high-density-in-scalable-systems"></a>확장 가능한 시스템에서 높은 밀도의 배포

컨테이너 기반 시스템에 가장 적합한 밀도, 세분성 및 성능이 필요한 경우 .NET과 ASP.NET Core가 가장 좋은 옵션입니다. ASP.NET Core는 기존 .NET Framework의 ASP.NET보다 10배 빠르며 Java 서블릿, Go 및 node.js와 같이 업계에서 널리 사용되는 마이크로 서비스 기술을 이끌고 있습니다.

해당 접근 방식은 수백 개의 마이크로 서비스(컨테이너)를 실행하는 마이크로 서비스 아키텍처의 경우 특히 관련이 있습니다. Linux 또는 Windows Nano의 ASP.NET Core 이미지(.NET 런타임 기반)를 통해 더 적은 수의 서버나 VM으로 시스템을 실행하여 인프라 및 호스팅 비용을 절감할 수 있습니다.

>[!div class="step-by-step"]
>[이전](general-guidance.md)
>[다음](net-framework-container-scenarios.md)
