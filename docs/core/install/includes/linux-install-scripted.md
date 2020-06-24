---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602719"
---

<span data-ttu-id="c8ad1-101">[dotnet-install 스크립트](../../tools/dotnet-install-script.md)는 자동화 및 **SDK**의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK**.</span></span> <span data-ttu-id="c8ad1-102"><https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="c8ad1-103">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-103">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="c8ad1-104">(LTS) 버전이 아닐 수 있는 현재 릴리스를 설치하려면 `-c Current` 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="c8ad1-105">SDK 대신 .NET Core 런타임을 설치하려면 `--runtime` 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-105">To install .NET Core Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime
```

<span data-ttu-id="c8ad1-106">특정 버전을 지정하도록 `-c` 매개 변수를 변경하여 특정 버전을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="c8ad1-107">다음 명령은 .NET Core SDK 3.1을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-107">The following command installs .NET Core SDK 3.1.</span></span>

```bash
./dotnet-install.sh -c 3.1
```

<span data-ttu-id="c8ad1-108">자세한 내용은 [dotnet-install 스크립트 참조](../../tools/dotnet-install-script.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8ad1-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
