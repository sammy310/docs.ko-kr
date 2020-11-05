---
ms.openlocfilehash: 68b55eb40d86ac3c92853acbb17ad622704b1336
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135651"
---

### <a name="install-the-sdk"></a><span data-ttu-id="a8a8c-101">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="a8a8c-101">Install the SDK</span></span>

<span data-ttu-id="a8a8c-102">.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="a8a8c-103">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="a8a8c-104">.NET Core SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-3.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="a8a8c-105">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="a8a8c-105">Install the runtime</span></span>

<span data-ttu-id="a8a8c-106">.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="a8a8c-107">다음 명령을 실행하면 .NET Core에 대해 가장 호환성이 높은 ASP.NET Core 런타임이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="a8a8c-108">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-108">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.0
```

<span data-ttu-id="a8a8c-109">ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 이전 명령에서 `aspnetcore-runtime-3.0`을 `dotnet-runtime-3.0`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a8a8c-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-3.0` in the previous command with `dotnet-runtime-3.0`.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
```
