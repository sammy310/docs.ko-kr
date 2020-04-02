---
title: dotnet nuget enable source 명령
description: dotnet nuget enable source 명령은 NuGet 구성 파일의 기존 소스를 사용하도록 설정합니다.
ms.date: 03/20/2020
ms.openlocfilehash: 1f18e7db6a6c8631bb432676dd97dabfad5b0ab8
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148485"
---
# <a name="dotnet-nuget-enable-source"></a>dotnet nuget enable source

**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전

## <a name="name"></a>속성

`dotnet nuget enable source` - NuGet 소스를 사용하도록 설정합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet nuget enable source <NAME> [--configfile]
dotnet nuget enable source [-h|--help]
```

## <a name="description"></a>Description

`dotnet nuget enable source` 명령은 NuGet 구성 파일의 기존 소스를 사용하도록 설정합니다.

## <a name="arguments"></a>인수

- **`NAME`**

  소스 이름입니다.

## <a name="options"></a>옵션

- **`--configfile`**

  NuGet 구성 파일입니다. 지정된 경우 이 파일의 설정만 사용됩니다. 지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다. 자세한 내용은 [일반적인 NuGet 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.

## <a name="examples"></a>예

- `mySource` 이름을 가진 소스를 사용하도록 설정합니다.

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a>참고 항목

- [NuGet.config 파일의 패키지 소스 섹션](/nuget/reference/nuget-config-file#package-source-sections)

- [소스 명령(nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
