---
title: .NET 컨테이너에서 대상으로 지정할 OS
description: 컨테이너화된 .NET 애플리케이션을 위한 .NET 마이크로 서비스 아키텍처 | .NET 컨테이너에서 대상으로 지정할 OS
ms.date: 01/13/2021
ms.openlocfilehash: b128a7b98d7f46034a56314bd8cc6b4f5731f121
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957912"
---
# <a name="what-os-to-target-with-net-containers"></a>.NET 컨테이너에서 대상으로 지정할 OS

Docker에서 지원하는 운영 체제의 다양함과 .NET Framework 및 .NET 5 간 차이를 고려해 보면 사용하는 프레임워크에 따라 특정 OS와 특정 버전을 목표로 해야 합니다.

Windows의 경우 Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다. 해당 Windows 버전은 각각 .NET Framework나 .NET 5에서 필요할 수 있는 다양한 특성(Windows Server Core의 IIS와 Nano Server의 Kestrel 같은 자체 호스팅 웹 서버)을 제공합니다.

Linux의 경우 공식 .NET Docker 이미지(예: Debian)에서 여러 배포판을 제공합니다.

그림 3-1에서는 사용하는 .NET 프레임워크에 따라 가능한 OS 버전을 확인할 수 있습니다.

![.NET 컨테이너에 사용할 OS를 보여 주는 다이어그램](./media/net-container-os-targets/targeting-operating-systems.png)

**그림 3-1.** .NET framework의 버전에 따라 대상으로 하는 운영 체제

레거시 .NET Framework 애플리케이션을 배포할 때는 레거시 앱 및 IIS와 호환되지만 더 큰 이미지를 가지는 Windows Server Core를 대상으로 해야 합니다. .NET 5 애플리케이션을 배포할 때는 클라우드에 최적화되고 Kestrel을 사용하며 더 규모가 작으면서 더 빠르게 시작하는 Windows Nano Server를 대상으로 할 수 있습니다. 또한 Debian, Alpine 등을 지원하는 Linux를 대상으로 할 수도 있습니다. Kestrel을 사용하고 더 규모가 작으며 더 빠르게 시작됩니다.

다른 Linux 배포판을 사용하려 하거나 Microsoft에서 제공하지 않는 버전 이미지가 필요한 경우 자체 Docker 이미지를 만들 수도 있습니다. 예를 들어 .NET Framework 및Windows Server Core에서 실행되는 기존 ASP.NET Core를 통해 이미지를 만들 수 있으나 Docker에는 그렇게 일반적인 시나리오가 아닙니다.

Dockerfile 파일에 이미지 이름을 추가할 때는 다음 예제에서처럼 사용하는 태그에 따라 운영 체제와 버전을 선택할 수 있습니다.

| 이미지 | 주석 |
|-------|----------|
| mcr.microsoft.com/dotnet/runtime:5.0 | .NET 5 다중 아키텍처: Docker 호스트에 따라 Linux 및 Windows Nano Server를 지원합니다. |
| mcr.microsoft.com/dotnet/aspnet:5.0 | ASP.NET Core 5.0 다중 아키텍처: Docker 호스트에 따라 Linux 및 Windows Nano Server를 지원합니다. <br/> aspnetcore 이미지에는 ASP.NET Core에 대한 몇 가지 최적화가 있습니다. |
| mcr.microsoft.com/dotnet/aspnet:5.0-buster-slim | Linux Debian 배포판의 .NET 5 런타임 전용 |
| mcr.microsoft.com/dotnet/aspnet:5.0-nanoserver-1809 | Windows Nano Server(Windows Server 버전 1809)의 .NET 5 런타임 전용 |

> [!div class="step-by-step"]
> [이전](container-framework-choice-factors.md)
> [다음](official-net-docker-images.md)
