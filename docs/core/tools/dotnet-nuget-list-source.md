---
title: dotnet nuget list source 명령
description: dotnet nuget list source 명령은 NuGet 구성 파일의 기존 소스를 모두 나열합니다.
ms.date: 03/20/2020
ms.openlocfilehash: 8b14413949bd60ddeed977d19eec9bb99982da70
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463549"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="96110-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="96110-103">dotnet nuget list source</span></span>

<span data-ttu-id="96110-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="96110-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="96110-105">속성</span><span class="sxs-lookup"><span data-stu-id="96110-105">Name</span></span>

<span data-ttu-id="96110-106">`dotnet nuget list source` - 구성된 NuGet 소스를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="96110-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="96110-107">개요</span><span class="sxs-lookup"><span data-stu-id="96110-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a><span data-ttu-id="96110-108">Description</span><span class="sxs-lookup"><span data-stu-id="96110-108">Description</span></span>

<span data-ttu-id="96110-109">`dotnet nuget list source` 명령은 NuGet 구성 파일의 기존 소스를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="96110-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="96110-110">옵션</span><span class="sxs-lookup"><span data-stu-id="96110-110">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="96110-111">NuGet 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="96110-111">The NuGet configuration file.</span></span> <span data-ttu-id="96110-112">지정된 경우 이 파일의 설정만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96110-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="96110-113">지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96110-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="96110-114">자세한 내용은 [일반적인 NuGet 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96110-114">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format [Detailed|Short]`**

  <span data-ttu-id="96110-115">list 명령 출력의 형식은 `Detailed`(기본값) 및 `Short`입니다.</span><span class="sxs-lookup"><span data-stu-id="96110-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="96110-116">예</span><span class="sxs-lookup"><span data-stu-id="96110-116">Examples</span></span>

- <span data-ttu-id="96110-117">현재 디렉터리에서 구성된 소스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="96110-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="96110-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96110-118">See also</span></span>

- [<span data-ttu-id="96110-119">NuGet.config 파일의 패키지 소스 섹션</span><span class="sxs-lookup"><span data-stu-id="96110-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="96110-120">소스 명령(nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="96110-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
