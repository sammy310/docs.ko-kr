---
ms.openlocfilehash: ea2883912907843e4b6d65db5ba186af43f27aaa
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85805417"
---

<!-- Note, this content is copied in ../macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="98106-101">패키지 관리자의 대안으로, SDK와 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98106-101">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="98106-102">수동 설치는 일반적으로 연속 통합 테스트의 일부로서 또는 지원되지 않는 Linux 배포에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="98106-102">Manual install is usually performed as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="98106-103">개발자 또는 사용자의 경우 일반적으로 패키지 관리자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="98106-103">For a developer or user, it's generally better to use a package manager.</span></span>

<span data-ttu-id="98106-104">.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98106-104">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="98106-105">먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 **이진** 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="98106-105">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="98106-106">✔️ [.NET 5.0 미리보기 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="98106-106">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="98106-107">✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="98106-107">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="98106-108">✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="98106-108">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="98106-109">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="98106-109">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="98106-110">그런 다음, 다운로드된 파일을 추출하고 `export` 명령을 사용하여 .NET Core에서 사용된 변수를 설정하고 .NET Core가 경로에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="98106-110">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="98106-111">런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="98106-111">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="98106-112">그런 다음, 터미널을 열고 파일이 저장된 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="98106-112">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="98106-113">보관 파일 이름은 다운로드한 항목에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98106-113">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="98106-114">**다음 명령을 사용하여 런타임을 추출합니다.**</span><span class="sxs-lookup"><span data-stu-id="98106-114">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="98106-115">**다음 명령을 사용하여 SDK를 추출합니다.**</span><span class="sxs-lookup"><span data-stu-id="98106-115">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="98106-116">이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET Core CLI 명령을 사용할 수 있도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98106-116">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="98106-117">셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98106-117">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="98106-118">몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="98106-118">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="98106-119">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="98106-119">For example:</span></span>
>
> - <span data-ttu-id="98106-120">**Bash 셸**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="98106-120">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="98106-121">**Korn 셸**: *~/.kshrc* 또는 *.profile*</span><span class="sxs-lookup"><span data-stu-id="98106-121">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="98106-122">**Z 셸**: *~/.zshrc* 또는 *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="98106-122">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="98106-123">셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98106-123">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="98106-124">포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98106-124">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="98106-125">또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98106-125">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="98106-126">이 방법을 사용하면 서로 다른 버전을 별도의 위치에 설치하고 애플리케이션에서 사용할 수 있도록 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98106-126">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>
