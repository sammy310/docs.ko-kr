---
title: DockerFile에서 Windows PowerShell 명령을 사용 하 여 Windows 컨테이너 (Docker 표준 기반) 설정
description: Windows 컨테이너에서 Docker를 사용 하는 경우 PowerShell을 사용 하는 방법 알아보기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: d9c0bc28f62d44eb7471b99c63055ef43da12a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644647"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="df4ea-103">DockerFile에서 Windows PowerShell 명령을 사용 하 여 Windows 컨테이너 (Docker 표준 기반) 설정</span><span class="sxs-lookup"><span data-stu-id="df4ea-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="df4ea-104">사용 하 여 [Windows 컨테이너](/virtualization/windowscontainers/about/index), Docker 이미지를 기존 Windows 응용 프로그램 변환 하 고 Docker 에코 시스템의 나머지 부분과 동일한 도구를 사용 하 여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df4ea-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="df4ea-105">Windows 컨테이너를 사용 하려면 하기만 하면 Windows PowerShell 명령은 DockerFile에서 쓸 다음 예제에서 설명한 대로:</span><span class="sxs-lookup"><span data-stu-id="df4ea-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="df4ea-106">이 경우 IIS 뿐만 아니라 Windows Server Core 기본 이미지를 설치 하려면 Windows PowerShell을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df4ea-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="df4ea-107">이와 비슷한 방식으로도 사용 하 여 Windows PowerShell 명령을 기존의 ASP.NET과 같은 추가 구성 요소를 설정 하려면 4.x 및.NET 4.6 또는 다른 Windows 소프트웨어를 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="df4ea-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="df4ea-108">[이전](visual-studio-tools-for-docker.md)
>[다음](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="df4ea-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
