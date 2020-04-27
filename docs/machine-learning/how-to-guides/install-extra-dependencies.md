---
title: 추가 ML.NET 종속성 설치
description: ML.NET 패키지가 종속되지만 NuGet 패키지와 함께 설치되지 않는 네이티브 라이브러리를 설치하는 방법을 알아봅니다.
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: c427439d0950bfea38f1d6d11af84216e0f1965f
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021851"
---
# <a name="install-extra-mlnet-dependencies"></a>추가 ML.NET 종속성 설치

대부분 모든 운영 체제에서 ML.NET을 설치하는 것은 적절한 NuGet 패키지를 참조하는 것만큼 간단합니다.

```bash
dotnet add package Microsoft.ML
```

경우에 따라 특히 네이티브 구성 요소가 필요한 경우 추가 설치 요구 사항이 있습니다. 이 문서에서는 해당 경우의 설치 요구 사항에 대해 설명합니다. 섹션은 추가 종속성이 있는 특정 `Microsoft.ML.*` NuGet 패키지로 구분됩니다.

## <a name="microsoftmltimeseries-microsoftmlautoml"></a>Microsoft.ML.TimeSeries, Microsoft.ML.AutoML

이 패키지는 둘 다 `libiomp`에 대한 종속성이 있는 `Microsoft.ML.MKL.Redist`에 대한 종속성을 포함합니다.

### <a name="windows"></a>Windows

추가 설치 단계가 필요하지 않습니다. 라이브러리는 NuGet 패키지가 프로젝트에 추가될 때 설치됩니다.

### <a name="linux"></a>Linux

1. 리포지토리의 GPG 키 설치

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

2. MKL용 APT 리포지토리 추가

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. 패키지 업데이트

    ```bash
    sudo apt-get update
    ```

4. MKL 설치

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    예를 들어:

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    `libiomp.so`의 위치 확인

    ```bash
    find /opt -name "libiomp5.so"
    ```

    예를 들어:

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. 다음 위치를 로드 라이브러리 경로에 추가:

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin
    ```

### <a name="mac"></a>Mac

1. `Homebrew`를 사용하여 라이브러리 설치

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```
