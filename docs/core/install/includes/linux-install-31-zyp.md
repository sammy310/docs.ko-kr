---
ms.openlocfilehash: 36f1ee26def82d426b6637ae96f382fc89791a2f
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135840"
---

### <a name="install-the-sdk"></a><span data-ttu-id="25b70-101">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="25b70-101">Install the SDK</span></span>

<span data-ttu-id="25b70-102">.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b70-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="25b70-103">.NET Core SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25b70-103">To install the .NET Core SDK, run the following commands.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a><span data-ttu-id="25b70-104">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="25b70-104">Install the runtime</span></span>

<span data-ttu-id="25b70-105">.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25b70-105">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="25b70-106">다음 명령을 실행하면 .NET Core에 대해 가장 호환성이 높은 ASP.NET Core 런타임이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="25b70-106">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="25b70-107">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25b70-107">In your terminal, run the following commands.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

<span data-ttu-id="25b70-108">ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 이전 명령에서 `aspnetcore-runtime-2.1`을 `dotnet-runtime-3.1`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="25b70-108">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```
