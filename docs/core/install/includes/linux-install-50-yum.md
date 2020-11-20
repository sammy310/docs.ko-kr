---
ms.openlocfilehash: cc394741e399f4fc54dd67f1736f7027badf4c7d
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507108"
---

### <a name="install-the-sdk"></a><span data-ttu-id="d3cef-101">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="d3cef-101">Install the SDK</span></span>

<span data-ttu-id="d3cef-102">.NET SDK를 사용하면 .NET으로 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3cef-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="d3cef-103">.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3cef-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="d3cef-104">.NET SDK를 설치하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3cef-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo yum install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="d3cef-105">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="d3cef-105">Install the runtime</span></span>

<span data-ttu-id="d3cef-106">ASP.NET Core 런타임을 사용하면 런타임을 제공하지 않는 .NET으로 만든 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3cef-106">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="d3cef-107">다음 명령을 실행하면 .NET에 대해 가장 호환성이 높은 ASP.NET Core 런타임이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cef-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="d3cef-108">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3cef-108">In your terminal, run the following commands:</span></span>

```bash
sudo yum install aspnetcore-runtime-5.0
```

<span data-ttu-id="d3cef-109">ASP.NET Core 런타임 대신 ASP.NET Core 지원이 포함되지 않은 .NET 런타임을 설치할 수 있습니다. 이전 명령에서 `aspnetcore-runtime-5.0`을 `dotnet-runtime-5.0`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3cef-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo yum install dotnet-runtime-5.0
```
