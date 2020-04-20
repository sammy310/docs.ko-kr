---
title: dotnet nuget remove source 명령
description: dotnet nuget remove source 명령은 NuGet 구성 파일에서 기존 소스를 제거합니다.
ms.date: 03/20/2020
ms.openlocfilehash: b259873e1885644b272136fa31414410bdfd9f27
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463497"
---
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="9ee71-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="9ee71-103">dotnet nuget remove source</span></span>

<span data-ttu-id="9ee71-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="9ee71-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9ee71-105">속성</span><span class="sxs-lookup"><span data-stu-id="9ee71-105">Name</span></span>

<span data-ttu-id="9ee71-106">`dotnet nuget remove source` - NuGet 소스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee71-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9ee71-107">개요</span><span class="sxs-lookup"><span data-stu-id="9ee71-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="9ee71-108">Description</span><span class="sxs-lookup"><span data-stu-id="9ee71-108">Description</span></span>

<span data-ttu-id="9ee71-109">`dotnet nuget remove source` 명령은 NuGet 구성 파일에서 기존 소스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee71-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="9ee71-110">인수</span><span class="sxs-lookup"><span data-stu-id="9ee71-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="9ee71-111">소스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee71-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="9ee71-112">옵션</span><span class="sxs-lookup"><span data-stu-id="9ee71-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="9ee71-113">NuGet 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee71-113">The NuGet configuration file.</span></span> <span data-ttu-id="9ee71-114">지정된 경우 이 파일의 설정만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee71-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="9ee71-115">지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee71-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="9ee71-116">자세한 내용은 [일반적인 NuGet 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ee71-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="9ee71-117">예</span><span class="sxs-lookup"><span data-stu-id="9ee71-117">Examples</span></span>

- <span data-ttu-id="9ee71-118">`mySource` 이름을 가진 소스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee71-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="9ee71-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ee71-119">See also</span></span>

- [<span data-ttu-id="9ee71-120">NuGet.config 파일의 패키지 소스 섹션</span><span class="sxs-lookup"><span data-stu-id="9ee71-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="9ee71-121">소스 명령(nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="9ee71-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
