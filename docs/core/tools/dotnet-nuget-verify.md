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
# <a name="dotnet-nuget-verify"></a>dotnet nuget verify

**이 문서의 적용 대상:** ✔️ .NET 5.0.100-rc.2.x SDK 이상 버전

## <a name="name"></a>Name

`dotnet nuget verify` - 서명된 NuGet 패키지를 확인합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a>Description

`dotnet nuget verify` 명령은 서명된 NuGet 패키지를 확인합니다.

## <a name="arguments"></a>인수

- **`package-path(s)`**

  확인할 패키지의 파일 경로를 지정합니다. 여러 패키지를 확인하기 위해 위치 인수를 여러 개 전달할 수 있습니다.

## <a name="options"></a>옵션

- **`--all`**

  패키지에 대해 가능한 모든 확인을 수행하도록 지정합니다. 기본적으로 `signatures`만 확인됩니다.

> [!NOTE]
> 이 명령은 현재 `signature` 확인만 지원합니다.

- **`--certificate-fingerprint <FINGERPRINT>`**

  서명자 인증서가 지정한 `SHA256` 지문 중 하나와 일치하는지 확인합니다. 여러 지문을 제공하기 위해 이 옵션을 여러 번 지정할 수 있습니다.

* **`-v|--verbosity <LEVEL>`**

  MSBuild의 자세한 정도 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `normal`입니다.

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예

- *foo.nupkg* 확인:

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- 여러 NuGet 패키지(*foo.nupkg* 및 ‘지정한 디렉터리에 있는 모든 .nupkg 파일’) 확인:

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- *foo.nupkg* 시그니처가 지정한 인증서 지문과 일치하는지 확인:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- *foo.nupkg* 시그니처가 지정한 인증서 지문 중 하나와 일치하는지 확인:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
