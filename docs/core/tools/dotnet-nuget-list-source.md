---
title: dotnet nuget list source 명령
description: dotnet nuget list source 명령은 NuGet 구성 파일의 기존 소스를 모두 나열합니다.
ms.date: 03/20/2020
ms.openlocfilehash: 071061e32aa1bf888e197ec6bf97f4e4f6859f0b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537899"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="c658c-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="c658c-103">dotnet nuget list source</span></span>

<span data-ttu-id="c658c-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="c658c-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c658c-105">속성</span><span class="sxs-lookup"><span data-stu-id="c658c-105">Name</span></span>

<span data-ttu-id="c658c-106">`dotnet nuget list source` - 구성된 NuGet 소스를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c658c-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c658c-107">개요</span><span class="sxs-lookup"><span data-stu-id="c658c-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a><span data-ttu-id="c658c-108">Description</span><span class="sxs-lookup"><span data-stu-id="c658c-108">Description</span></span>

<span data-ttu-id="c658c-109">`dotnet nuget list source` 명령은 NuGet 구성 파일의 기존 소스를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c658c-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="c658c-110">옵션</span><span class="sxs-lookup"><span data-stu-id="c658c-110">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="c658c-111">NuGet 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c658c-111">The NuGet configuration file.</span></span> <span data-ttu-id="c658c-112">지정된 경우 이 파일의 설정만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c658c-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="c658c-113">지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c658c-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="c658c-114">자세한 내용은 [일반적인 NuGet 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c658c-114">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format [Detailed|Short]`**

  <span data-ttu-id="c658c-115">list 명령 출력의 형식은 `Detailed`(기본값) 및 `Short`입니다.</span><span class="sxs-lookup"><span data-stu-id="c658c-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="c658c-116">예</span><span class="sxs-lookup"><span data-stu-id="c658c-116">Examples</span></span>

- <span data-ttu-id="c658c-117">현재 디렉터리에서 구성된 소스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c658c-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="c658c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c658c-118">See also</span></span>

- [<span data-ttu-id="c658c-119">NuGet.config 파일의 패키지 소스 섹션</span><span class="sxs-lookup"><span data-stu-id="c658c-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="c658c-120">소스 명령(nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="c658c-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
