---
title: DockerFile에서 Windows PowerShell 명령을 사용하여 Windows 컨테이너 설정(Docker 표준 기반)
description: Windows 컨테이너에서 Docker로 작업할 때 PowerShell을 사용하는 방법 알아보기
ms.date: 08/06/2020
ms.openlocfilehash: 4e7b9e7fedf11b97b3f468aef541bf72a4e88ebc
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915392"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="9011c-103">DockerFile에서 Windows PowerShell 명령을 사용하여 Windows 컨테이너 설정(Docker 표준 기반)</span><span class="sxs-lookup"><span data-stu-id="9011c-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="9011c-104">[Windows 컨테이너](/virtualization/windowscontainers/about/index)를 사용하면 Docker 에코시스템의 나머지 부분과 동일한 도구로 기존 Windows 애플리케이션을 Docker 이미지로 변환하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9011c-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="9011c-105">Windows 컨테이너를 사용하려면 다음 예제에서 설명한 대로 Windows PowerShell 명령을 DockerFile에 쓰기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9011c-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="9011c-106">이 경우 Windows PowerShell을 사용하여 IIS뿐만 아니라 Windows Server Core 기본 이미지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9011c-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="9011c-107">비슷한 방법으로 Windows PowerShell 명령을 사용하여 다음과 같이 기존 ASP.NET 4.x 및 .NET 4.6 또는 기타 Windows 소프트웨어와 같은 추가 구성 요소를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9011c-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="9011c-108">[이전](visual-studio-tools-for-docker.md)
>[다음](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="9011c-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
