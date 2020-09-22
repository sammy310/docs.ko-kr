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
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전

## <a name="name"></a>속성

`dotnet nuget list source` - 구성된 NuGet 소스를 모두 나열합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a>Description

`dotnet nuget list source` 명령은 NuGet 구성 파일의 기존 소스를 모두 나열합니다.

## <a name="options"></a>옵션

- **`--configfile <FILE>`**

  NuGet 구성 파일입니다. 지정된 경우 이 파일의 설정만 사용됩니다. 지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다. 자세한 내용은 [일반적인 NuGet 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.

- **`--format [Detailed|Short]`**

  list 명령 출력의 형식은 `Detailed`(기본값) 및 `Short`입니다.

## <a name="examples"></a>예

- 현재 디렉터리에서 구성된 소스를 나열합니다.

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>참고 항목

- [NuGet.config 파일의 패키지 소스 섹션](/nuget/reference/nuget-config-file#package-source-sections)

- [소스 명령(nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
