---
title: 추가 ML.NET 종속성 설치
description: ML.NET 패키지가 종속되지만 NuGet 패키지와 함께 설치되지 않는 네이티브 라이브러리를 설치하는 방법을 알아봅니다.
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: 0b870542706c065295d48205b7780e568e267ab6
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888277"
---
# <a name="install-extra-mlnet-dependencies"></a><span data-ttu-id="5d4c5-103">추가 ML.NET 종속성 설치</span><span class="sxs-lookup"><span data-stu-id="5d4c5-103">Install extra ML.NET dependencies</span></span>

<span data-ttu-id="5d4c5-104">대부분 모든 운영 체제에서 ML.NET을 설치하는 것은 적절한 NuGet 패키지를 참조하는 것만큼 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4c5-104">In most cases, on all operating systems, installing ML.NET is as simple as referencing the appropriate NuGet package.</span></span>

```bash
dotnet add package Microsoft.ML
```

<span data-ttu-id="5d4c5-105">경우에 따라 특히 네이티브 구성 요소가 필요한 경우 추가 설치 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d4c5-105">In some cases though, there are additional installation requirements, particularly when native components are required.</span></span> <span data-ttu-id="5d4c5-106">이 문서에서는 해당 경우의 설치 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4c5-106">This document describes the installation requirements for those cases.</span></span> <span data-ttu-id="5d4c5-107">섹션은 추가 종속성이 있는 특정 `Microsoft.ML.*` NuGet 패키지로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d4c5-107">The sections are broken down by the specific `Microsoft.ML.*` NuGet package that has the additional dependency.</span></span>

## <a name="microsoftmltimeseries-microsoftmlautoml"></a><span data-ttu-id="5d4c5-108">Microsoft.ML.TimeSeries, Microsoft.ML.AutoML</span><span class="sxs-lookup"><span data-stu-id="5d4c5-108">Microsoft.ML.TimeSeries, Microsoft.ML.AutoML</span></span>

<span data-ttu-id="5d4c5-109">이 패키지는 둘 다 `libiomp`에 대한 종속성이 있는 `Microsoft.ML.MKL.Redist`에 대한 종속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4c5-109">Both of these packages have a dependency on `Microsoft.ML.MKL.Redist`, which has a dependency on `libiomp`.</span></span>

### <a name="windows"></a><span data-ttu-id="5d4c5-110">Windows</span><span class="sxs-lookup"><span data-stu-id="5d4c5-110">Windows</span></span>

<span data-ttu-id="5d4c5-111">추가 설치 단계가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d4c5-111">No extra installation steps required.</span></span> <span data-ttu-id="5d4c5-112">라이브러리는 NuGet 패키지가 프로젝트에 추가될 때 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d4c5-112">The library is installed when the NuGet package is added to the project.</span></span>

### <a name="linux"></a><span data-ttu-id="5d4c5-113">Linux</span><span class="sxs-lookup"><span data-stu-id="5d4c5-113">Linux</span></span>

1. <span data-ttu-id="5d4c5-114">리포지토리의 GPG 키 설치</span><span class="sxs-lookup"><span data-stu-id="5d4c5-114">Install the GPG key for the repository</span></span>

    ```bash
    sudo bash
    # <type your user password when prompted.  this will put you in a root shell>
    # cd to /tmp where this shell has write permission
    cd /tmp
    # now get the key:
    wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now install that key
    apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now remove the public key file exit the root shell
    rm GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    exit
    ```

2. <span data-ttu-id="5d4c5-115">MKL용 APT 리포지토리 추가</span><span class="sxs-lookup"><span data-stu-id="5d4c5-115">Add the APT Repository for MKL</span></span>

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. <span data-ttu-id="5d4c5-116">패키지 업데이트</span><span class="sxs-lookup"><span data-stu-id="5d4c5-116">Update packages</span></span>

    ```bash
    sudo apt-get update
    ```

4. <span data-ttu-id="5d4c5-117">MKL 설치</span><span class="sxs-lookup"><span data-stu-id="5d4c5-117">Install MKL</span></span>

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    <span data-ttu-id="5d4c5-118">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="5d4c5-118">For example:</span></span>

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    <span data-ttu-id="5d4c5-119">`libiomp.so`의 위치 확인</span><span class="sxs-lookup"><span data-stu-id="5d4c5-119">Determine the location of `libiomp.so`</span></span>

    ```bash
    find /opt -name "libiomp5.so"
    ```

    <span data-ttu-id="5d4c5-120">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="5d4c5-120">For example:</span></span>

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. <span data-ttu-id="5d4c5-121">다음 위치를 로드 라이브러리 경로에 추가:</span><span class="sxs-lookup"><span data-stu-id="5d4c5-121">Add this location to the load library path:</span></span>

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_li
    ```

### <a name="mac"></a><span data-ttu-id="5d4c5-122">Mac</span><span class="sxs-lookup"><span data-stu-id="5d4c5-122">Mac</span></span>

1. <span data-ttu-id="5d4c5-123">`Homebrew`를 사용하여 라이브러리 설치</span><span class="sxs-lookup"><span data-stu-id="5d4c5-123">Install the library with `Homebrew`</span></span>

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```
