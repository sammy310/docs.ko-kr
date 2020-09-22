---
title: dotnet nuget disable source 명령
description: dotnet nuget disable source 명령은 NuGet 구성 파일의 기존 소스를 사용하지 않도록 설정합니다.
ms.date: 03/20/2020
ms.openlocfilehash: af37a6589cebaf0501ee5647ebadb83125d0f56e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537953"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="e21d4-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="e21d4-103">dotnet nuget disable source</span></span>

<span data-ttu-id="e21d4-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="e21d4-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e21d4-105">속성</span><span class="sxs-lookup"><span data-stu-id="e21d4-105">Name</span></span>

<span data-ttu-id="e21d4-106">`dotnet nuget disable source` - NuGet 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e21d4-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e21d4-107">개요</span><span class="sxs-lookup"><span data-stu-id="e21d4-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a><span data-ttu-id="e21d4-108">Description</span><span class="sxs-lookup"><span data-stu-id="e21d4-108">Description</span></span>

<span data-ttu-id="e21d4-109">`dotnet nuget disable source` 명령은 NuGet 구성 파일에서 기존 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e21d4-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="e21d4-110">인수</span><span class="sxs-lookup"><span data-stu-id="e21d4-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="e21d4-111">소스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e21d4-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="e21d4-112">옵션</span><span class="sxs-lookup"><span data-stu-id="e21d4-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="e21d4-113">NuGet 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e21d4-113">The NuGet configuration file.</span></span> <span data-ttu-id="e21d4-114">지정된 경우 이 파일의 설정만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e21d4-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="e21d4-115">지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e21d4-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="e21d4-116">자세한 내용은 [일반적인 NuGet 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e21d4-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="e21d4-117">예</span><span class="sxs-lookup"><span data-stu-id="e21d4-117">Examples</span></span>

- <span data-ttu-id="e21d4-118">`mySource` 이름을 가진 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e21d4-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="e21d4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e21d4-119">See also</span></span>

- [<span data-ttu-id="e21d4-120">NuGet.config 파일의 패키지 소스 섹션</span><span class="sxs-lookup"><span data-stu-id="e21d4-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="e21d4-121">소스 명령(nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="e21d4-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
