---
ms.openlocfilehash: cac1fbd2369277b3a322247a7008f07929502437
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507020"
---

### <a name="install-the-sdk"></a><span data-ttu-id="f22e8-101">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="f22e8-101">Install the SDK</span></span>

<span data-ttu-id="f22e8-102">.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22e8-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="f22e8-103">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f22e8-103">If you install the .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f22e8-104">.NET Core SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f22e8-104">To install the .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="f22e8-105">**패키지 dotnet-sdk-3.1을 찾을 수 없습니다** 와 같은 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f22e8-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="f22e8-106">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="f22e8-106">Install the runtime</span></span>

<span data-ttu-id="f22e8-107">.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22e8-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="f22e8-108">다음 명령을 실행하면 .NET Core에 대해 가장 호환성이 높은 ASP.NET Core 런타임이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22e8-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="f22e8-109">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f22e8-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="f22e8-110">**패키지 aspnetcore-runtime-3.1을 찾을 수 없습니다** 와 같은 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f22e8-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="f22e8-111">ASP.NET Core 런타임 대신 ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 이전 명령에서 `aspnetcore-runtime-3.1`을 `dotnet-runtime-3.1`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f22e8-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-3.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-3.1
```
