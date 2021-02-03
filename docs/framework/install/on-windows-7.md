---
title: Windows 7 SP1에 .NET Framework 설치
description: Windows 7 SP1에서.NET Framework를 설치하는 방법을 알아봅니다.
ms.date: 04/18/2019
ms.openlocfilehash: 900b38110626a93f37829045a8676ea87101d7e9
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899089"
---
# <a name="install-the-net-framework-on-windows-7-sp1-and-windows-server-2008-r2"></a><span data-ttu-id="79269-103">Windows 7 SP1 및 Windows Server 2008 R2에 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="79269-103">Install the .NET Framework on Windows 7 SP1 and Windows Server 2008 R2</span></span>

<span data-ttu-id="79269-104">Windows에서 많은 애플리케이션을 실행하는 데 .NET Framework가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="79269-104">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="79269-105">다음 지침을 사용하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79269-105">You can use the following instructions to install it.</span></span> <span data-ttu-id="79269-106">애플리케이션을 실행한 후 컴퓨터에 다음 대화 상자가 표시되어 이 페이지를 방문했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79269-106">You may have arrived on this page after trying to run an application and seeing the following dialog on your machine.</span></span>

![이 애플리케이션을 시작할 수 없습니다.](./media/this-application-could-not-be-started.png)

<span data-ttu-id="79269-108">이러한 지침은 필요한 .NET Framework 버전을 설치하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79269-108">These instructions will help you install the .NET Framework versions you need.</span></span> <span data-ttu-id="79269-109">[.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48)은 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="79269-109">The [.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) is the latest version.</span></span> <span data-ttu-id="79269-110">Windows 7 SP1 및 Windows Server 2008 R2에서 지원되고 [Windows 10 2019년 5월 업데이트](https://support.microsoft.com/help/4028685/windows-10-get-the-update)와 함께 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79269-110">It is supported on Windows 7 SP1 and Windows Server 2008 R2 and is included with [Windows 10 May 2019 Update](https://support.microsoft.com/help/4028685/windows-10-get-the-update).</span></span>

## <a name="net-framework-48"></a><span data-ttu-id="79269-111">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="79269-111">.NET Framework 4.8</span></span>

> [!div class="button"]
> [<span data-ttu-id="79269-112">.NET Framework 4.8 다운로드</span><span class="sxs-lookup"><span data-stu-id="79269-112">Download .NET Framework 4.8</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)

<span data-ttu-id="79269-113">[.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48)는 .NET Framework 4.0 이상용으로 빌드된 애플리케이션을 실행하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79269-113">The [.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) can be used to run applications built for .NET Framework 4.0 or later.</span></span>

### <a name="offline-installer"></a><span data-ttu-id="79269-114">오프라인 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="79269-114">Offline installer</span></span>

<span data-ttu-id="79269-115">Windows 7에서 .NET Framework의 오프라인 설치를 수행하려면 먼저 최신 [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm)이 대상 머신에 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79269-115">When doing an offline install for .NET Framework on Windows 7, you'll first need to make sure that the latest [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm) has been installed on the target machine.</span></span>

<span data-ttu-id="79269-116">_certmgr.exe_ 도구는 인증서 설치를 자동화할 수 있으며 Visual Studio 또는 Windows SDK에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="79269-116">The _certmgr.exe_ tool can automate installing a certificate and is obtained from Visual Studio or the Windows SDK.</span></span> <span data-ttu-id="79269-117">다음 명령은 .NET Framework 설치 관리자를 실행하기 전에 인증서를 설치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79269-117">The following command is used to install the certificate before running the .NET Framework installer:</span></span>

```console
certmgr.exe /add MicRooCerAut2011_2011_03_22.crt /s /r localMachine root
```

## <a name="net-framework-35"></a><span data-ttu-id="79269-118">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="79269-118">.NET Framework 3.5</span></span>

<span data-ttu-id="79269-119">[.NET Framework 3.5](https://dotnet.microsoft.com/download/dotnet-framework/net35-sp1)는 Windows 7에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79269-119">The [.NET Framework 3.5](https://dotnet.microsoft.com/download/dotnet-framework/net35-sp1) is included with Windows 7.</span></span>

<span data-ttu-id="79269-120">.NET Framework 3.5는 .NET Framework 1.0~3.5용으로 빌드된 앱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="79269-120">The .NET Framework 3.5 supports apps built for .NET Framework 1.0 through 3.5.</span></span>

## <a name="help"></a><span data-ttu-id="79269-121">도움말</span><span class="sxs-lookup"><span data-stu-id="79269-121">Help</span></span>

<span data-ttu-id="79269-122">설치된 .NET Framework의 정확한 버전을 확인할 수 없는 경우 [Microsoft에 지원을 문의](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79269-122">You can [contact Microsoft for help](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help) if you cannot get the correct version of the .NET Framework installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="79269-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79269-123">See also</span></span>

- [<span data-ttu-id="79269-124">.NET Framework 다운로드</span><span class="sxs-lookup"><span data-stu-id="79269-124">Download the .NET Framework</span></span>](https://dotnet.microsoft.com/download)
- [<span data-ttu-id="79269-125">차단된 .NET Framework 설치 및 제거 문제 해결</span><span class="sxs-lookup"><span data-stu-id="79269-125">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
- [<span data-ttu-id="79269-126">개발자용 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="79269-126">Install the .NET Framework for developers</span></span>](guide-for-developers.md)
