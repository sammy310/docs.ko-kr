---
title: dotnet nuget disable source 명령
description: dotnet nuget disable source 명령은 NuGet 구성 파일의 기존 소스를 사용하지 않도록 설정합니다.
ms.date: 03/20/2020
ms.openlocfilehash: 5aa16c842bcddeead180fdeec3d9dcdda33f7ed9
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148479"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="c45b1-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="c45b1-103">dotnet nuget disable source</span></span>

<span data-ttu-id="c45b1-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="c45b1-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c45b1-105">속성</span><span class="sxs-lookup"><span data-stu-id="c45b1-105">Name</span></span>

<span data-ttu-id="c45b1-106">`dotnet nuget disable source` - NuGet 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c45b1-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c45b1-107">개요</span><span class="sxs-lookup"><span data-stu-id="c45b1-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile]
dotnet nuget disable source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c45b1-108">Description</span><span class="sxs-lookup"><span data-stu-id="c45b1-108">Description</span></span>

<span data-ttu-id="c45b1-109">`dotnet nuget disable source` 명령은 NuGet 구성 파일에서 기존 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c45b1-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="c45b1-110">인수</span><span class="sxs-lookup"><span data-stu-id="c45b1-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="c45b1-111">소스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45b1-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="c45b1-112">옵션</span><span class="sxs-lookup"><span data-stu-id="c45b1-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="c45b1-113">NuGet 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c45b1-113">The NuGet configuration file.</span></span> <span data-ttu-id="c45b1-114">지정된 경우 이 파일의 설정만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c45b1-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="c45b1-115">지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c45b1-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="c45b1-116">자세한 내용은 [일반적인 NuGet 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c45b1-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="c45b1-117">예</span><span class="sxs-lookup"><span data-stu-id="c45b1-117">Examples</span></span>

- <span data-ttu-id="c45b1-118">`mySource` 이름을 가진 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c45b1-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="c45b1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c45b1-119">See also</span></span>

- [<span data-ttu-id="c45b1-120">NuGet.config 파일의 패키지 소스 섹션</span><span class="sxs-lookup"><span data-stu-id="c45b1-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="c45b1-121">소스 명령(nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="c45b1-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
