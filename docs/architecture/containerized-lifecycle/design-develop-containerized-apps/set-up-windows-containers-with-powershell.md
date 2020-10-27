---
title: DockerFile에서 Windows PowerShell 명령을 사용하여 Windows 컨테이너 설정(Docker 표준 기반)
description: Windows 컨테이너에서 Docker로 작업할 때 PowerShell을 사용하는 방법 알아보기
ms.date: 08/06/2020
ms.openlocfilehash: 6096e4cbad4fb37b485d595c650dc10dc5ed5a22
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434810"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>DockerFile에서 Windows PowerShell 명령을 사용하여 Windows 컨테이너 설정(Docker 표준 기반)

[Windows 컨테이너](/virtualization/windowscontainers/about/index)를 사용하면 Docker 에코시스템의 나머지 부분과 동일한 도구로 기존 Windows 애플리케이션을 Docker 이미지로 변환하고 배포할 수 있습니다.

Windows 컨테이너를 사용하려면 다음 예제에서 설명한 대로 Windows PowerShell 명령을 DockerFile에 쓰기만 하면 됩니다.

```dockerfile
FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

이 경우 Windows PowerShell을 사용하여 IIS뿐만 아니라 Windows Server Core 기본 이미지를 설치합니다.

비슷한 방법으로 Windows PowerShell 명령을 사용하여 다음과 같이 기존 ASP.NET 4.x 및 .NET 4.6 또는 기타 Windows 소프트웨어와 같은 추가 구성 요소를 설치할 수도 있습니다.

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[이전](visual-studio-tools-for-docker.md)
>[다음](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
