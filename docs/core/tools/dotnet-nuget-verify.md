---
title: dotnet nuget verify 명령
description: dotnet nuget verify 명령은 서명된 패키지를 확인합니다.
author: kartheekp-ms
ms.date: 10/08/2020
ms.openlocfilehash: 6cb368e2b6c203f3774b4450c0831c5d6b2dc0e8
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957102"
---
# <a name="dotnet-nuget-verify"></a><span data-ttu-id="8d518-103">dotnet nuget verify</span><span class="sxs-lookup"><span data-stu-id="8d518-103">dotnet nuget verify</span></span>

<span data-ttu-id="8d518-104">**이 문서의 적용 대상:** ✔️ .NET 5.0.100-rc.2.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="8d518-104">**This article applies to:** ✔️ .NET 5.0.100-rc.2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8d518-105">Name</span><span class="sxs-lookup"><span data-stu-id="8d518-105">Name</span></span>

<span data-ttu-id="8d518-106">`dotnet nuget verify` - 서명된 NuGet 패키지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-106">`dotnet nuget verify` - Verifies a signed NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8d518-107">개요</span><span class="sxs-lookup"><span data-stu-id="8d518-107">Synopsis</span></span>

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a><span data-ttu-id="8d518-108">Description</span><span class="sxs-lookup"><span data-stu-id="8d518-108">Description</span></span>

<span data-ttu-id="8d518-109">`dotnet nuget verify` 명령은 서명된 NuGet 패키지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-109">The `dotnet nuget verify` command verifies a signed NuGet package.</span></span>

## <a name="arguments"></a><span data-ttu-id="8d518-110">인수</span><span class="sxs-lookup"><span data-stu-id="8d518-110">Arguments</span></span>

- **`package-path(s)`**

  <span data-ttu-id="8d518-111">확인할 패키지의 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-111">Specifies the file path to the package(s) to be verified.</span></span> <span data-ttu-id="8d518-112">여러 패키지를 확인하기 위해 위치 인수를 여러 개 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-112">Multiple position arguments can be passed in to verify multiple packages.</span></span>

## <a name="options"></a><span data-ttu-id="8d518-113">옵션</span><span class="sxs-lookup"><span data-stu-id="8d518-113">Options</span></span>

- **`--all`**

  <span data-ttu-id="8d518-114">패키지에 대해 가능한 모든 확인을 수행하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-114">Specifies that all verifications possible should be performed on the package(s).</span></span> <span data-ttu-id="8d518-115">기본적으로 `signatures`만 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-115">By default, only `signatures` are verified.</span></span>

> [!NOTE]
> <span data-ttu-id="8d518-116">이 명령은 현재 `signature` 확인만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-116">This command currently supports only `signature` verification.</span></span>

- **`--certificate-fingerprint <FINGERPRINT>`**

  <span data-ttu-id="8d518-117">서명자 인증서가 지정한 `SHA256` 지문 중 하나와 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-117">Verify that the signer certificate matches with one of the specified `SHA256` fingerprints.</span></span> <span data-ttu-id="8d518-118">여러 지문을 제공하기 위해 이 옵션을 여러 번 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-118">This option can be supplied multiple times to provide multiple fingerprints.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8d518-119">MSBuild의 자세한 정도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-119">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="8d518-120">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-120">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8d518-121">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-121">The default is `normal`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="8d518-122">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8d518-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8d518-123">예</span><span class="sxs-lookup"><span data-stu-id="8d518-123">Examples</span></span>

- <span data-ttu-id="8d518-124">*foo.nupkg* 확인:</span><span class="sxs-lookup"><span data-stu-id="8d518-124">Verify *foo.nupkg*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- <span data-ttu-id="8d518-125">여러 NuGet 패키지(*foo.nupkg* 및 ‘지정한 디렉터리에 있는 모든 .nupkg 파일’) 확인:</span><span class="sxs-lookup"><span data-stu-id="8d518-125">Verify multiple NuGet packages - *foo.nupkg* and *all .nupkg files in the directory specified*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- <span data-ttu-id="8d518-126">*foo.nupkg* 시그니처가 지정한 인증서 지문과 일치하는지 확인:</span><span class="sxs-lookup"><span data-stu-id="8d518-126">Verify *foo.nupkg* signature matches with the specified certificate fingerprint:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- <span data-ttu-id="8d518-127">*foo.nupkg* 시그니처가 지정한 인증서 지문 중 하나와 일치하는지 확인:</span><span class="sxs-lookup"><span data-stu-id="8d518-127">Verify *foo.nupkg* signature matches with one of the specified certificate fingerprints:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
