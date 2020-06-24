---
ms.openlocfilehash: 703452492eb47c5720fdaad23a3e699585233419
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602815"
---

### <a name="install-the-sdk"></a><span data-ttu-id="4faa0-101">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="4faa0-101">Install the SDK</span></span>

<span data-ttu-id="4faa0-102">.NET Core SDK를 사용하면 .NET Core로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4faa0-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="4faa0-103">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4faa0-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="4faa0-104">.NET Core SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4faa0-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-2.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="4faa0-105">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="4faa0-105">Install the runtime</span></span>

<span data-ttu-id="4faa0-106">.NET Core 런타임을 사용하면 런타임을 포함하지 않았던 .NET Core로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4faa0-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="4faa0-107">아래 명령은 ASP.NET Core 런타임을 설치하며 이는 .NET Core에 대해 가장 호환성이 높은 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="4faa0-107">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="4faa0-108">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4faa0-108">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install aspnetcore-runtime-2.0
```

<span data-ttu-id="4faa0-109">ASP.NET Core 런타임의 대안으로, ASP.NET Core 지원이 포함되지 않은 .NET Core 런타임을 설치할 수 있습니다. 위 명령에서 `aspnetcore-runtime-2.0`을 `dotnet-runtime-2.0`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4faa0-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.0` in the command above with `dotnet-runtime-2.0`.</span></span>

```bash
sudo dnf install dotnet-runtime-2.0
```
