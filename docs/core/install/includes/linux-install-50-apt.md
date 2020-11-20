---
ms.openlocfilehash: 87c7abf6a20dd8e9769f3b3b3cbe271d32fd62c3
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507001"
---

### <a name="install-the-sdk"></a><span data-ttu-id="c8824-101">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="c8824-101">Install the SDK</span></span>

<span data-ttu-id="c8824-102">.NET SDK를 사용하면 .NET으로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8824-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="c8824-103">.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8824-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="c8824-104">.NET SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8824-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="c8824-105">**dotnet-sdk-5.0 패키지를 찾을 수 없음** 과 유사한 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8824-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-5.0**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="c8824-106">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="c8824-106">Install the runtime</span></span>

<span data-ttu-id="c8824-107">ASP.NET Core 런타임을 사용하면 런타임을 제공하지 않는 .NET으로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8824-107">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="c8824-108">다음 명령을 실행하면 .NET에 대해 가장 호환성이 높은 ASP.NET Core 런타임이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8824-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="c8824-109">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8824-109">In your terminal, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-5.0
```

> [!IMPORTANT]
> <span data-ttu-id="c8824-110">**aspnetcore-runtime-5.0 패키지를 찾을 수 없음** 과 같은 오류 메시지가 표시되는 경우 [APT 문제 해결](#apt-troubleshooting) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8824-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-5.0**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="c8824-111">ASP.NET Core 런타임 대신 ASP.NET Core 지원이 포함되지 않은 .NET 런타임을 설치할 수 있습니다. 이전 명령에서 `aspnetcore-runtime-5.0`을 `dotnet-runtime-5.0`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c8824-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo apt-get install -y dotnet-runtime-5.0
```
