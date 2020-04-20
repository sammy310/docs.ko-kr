---
title: dotnet nuget update source 명령
description: dotnet nuget update source 명령은 NuGet 구성 파일의 기존 소스를 업데이트합니다.
ms.date: 03/20/2020
ms.openlocfilehash: 42b1aec95cdd57e53f966400f6692a3d0150c16c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463486"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**이 문서의 적용 대상:** ✔️ .NET Core 3.1.200 SDK 이상 버전

## <a name="name"></a>속성

`dotnet nuget update source` - NuGet 소스를 업데이트합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a>Description

`dotnet nuget update source` 명령은 NuGet 구성 파일의 기존 소스를 업데이트합니다.

## <a name="arguments"></a>인수

- **`NAME`**

  소스 이름입니다.

## <a name="options"></a>옵션

- **`--configfile <FILE>`**

  NuGet 구성 파일입니다. 지정된 경우 이 파일의 설정만 사용됩니다. 지정되지 않으면 현재 디렉터리의 구성 파일의 계층 구조가 사용됩니다. 자세한 내용은 [일반적인 NuGet 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.

- **`-p|--password <PASSWORD>`**

  인증된 소스에 연결할 때 사용할 암호입니다.

- **`-s|--source <SOURCE>`**

  패키지 소스의 경로입니다.

- **`--store-password-in-clear-text`**

  암호 암호화를 사용하지 않도록 설정하여 이식 가능한 패키지 소스 자격 증명을 저장할 수 있게 합니다.

- **`-u|--username <USER>`**

  인증된 소스에 연결할 때 사용할 사용자 이름입니다.

- **`--valid-authentication-types <TYPES>`**

  이 소스에 대한 유효한 인증 형식의 쉼표로 구분된 목록입니다. 서버에서 NTLM 또는 Negotiate를 보급하고 기본 메커니즘을 사용하여 자격 증명을 전송해야 하는 경우(예를 들어 온-프레미스 Azure DevOps Server에서 PAT를 사용하는 경우) `basic`으로 설정합니다. 다른 유효한 값은 `negotiate`, `kerberos`, `ntlm` 및 `digest`이지만 이러한 값은 유용하지 않을 수 있습니다.

## <a name="examples"></a>예

- `mySource` 이름을 가진 소스를 업데이트합니다.

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>참고 항목

- [NuGet.config 파일의 패키지 소스 섹션](/nuget/reference/nuget-config-file#package-source-sections)

- [소스 명령(nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
