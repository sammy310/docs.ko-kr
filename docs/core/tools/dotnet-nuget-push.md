---
title: dotnet nuget push 명령
description: dotnet nuget push 명령은 서버에 패키지를 푸시하고 게시합니다.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 92e2593633343bda6990ca51d593455ff13f0df7
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478189"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전

## <a name="name"></a>이름

`dotnet nuget push` - 서버에 패키지를 푸시하고 게시합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a>설명

`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다. push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다. 구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요. NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config* 를 로드하여 가져올 수 있습니다.

이 명령은 기존 패키지를 푸시합니다. 패키지를 만들지 않습니다. 패키지를 만들려면 [`dotnet pack`](dotnet-pack.md)을 사용합니다.

## <a name="arguments"></a>인수

- **`ROOT`**

  푸시되는 패키지에 대한 파일 경로를 지정합니다.

## <a name="options"></a>옵션

- **`-d|--disable-buffering`**

  메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.

- **`--force-english-output`**

  고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--interactive`**

  명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다. .NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.

- **`-k|--api-key <API_KEY>`**

  서버에 대한 API 키입니다.

- **`-n|--no-symbols`**

  기호를 푸시하지 않습니다(있는 경우).

- **`--no-service-endpoint`**

  소스 URL에 “api/v2/package”를 추가하지 마세요. .NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.

- **`-s|--source <SOURCE>`**

  서버 URL을 지정합니다. NuGet은 UNC 또는 로컬 폴더 소스를 식별하며, HTTP를 사용하여 파일을 푸시하는 대신 단순히 파일을 복사합니다.
  > [!IMPORTANT]
  > NuGet 3.4.2부터는 NuGet 구성 파일이 `DefaultPushSource` 값을 지정하지 않는 한 이것이 필수 매개 변수입니다. 자세한 내용은 참조 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.

- **`--skip-duplicate`**

  여러 패키지를 HTTP(S) 서버로 푸시할 때 푸시를 계속할 수 있도록 409 충돌 응답을 경고로 처리합니다. .NET Core 3.1 SDK부터 사용할 수 있습니다.

- **`-sk|--symbol-api-key <API_KEY>`**

  기호 서버에 대한 API 키입니다.

- **`-ss|--symbol-source <SOURCE>`**

  기호 서버 URL을 지정합니다.

- **`-t|--timeout <TIMEOUT>`**

  서버에 푸시하기 위한 제한 시간(초)을 지정합니다. 기본값은 300 초(5 분)입니다. 0(0초)을 지정하면 기본값이 적용됩니다.

## <a name="examples"></a>예

- API 키를 사용하여 NuGet 구성 파일에 지정된 기본 푸시 소스에 *foo.nupkg* 를 푸시합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- 공식 NuGet 서버에 *foo.nupkg* 를 푸시하여 API 키를 지정합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * 사용자 지정 푸시 소스 `https://customsource`에 *foo.nupkg* 를 푸시하여 API 키를 지정합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- NuGet 구성 파일에 지정된 기본 푸시 소스에 *foo.nupkg* 를 푸시합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- 기본 기호 소스에 *foo.symbols.nupkg* 를 푸시합니다.

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- 360초 시간 제한을 사용하여 NuGet 구성 파일에 지정된 기본 푸시 소스에 *foo.nupkg* 를 푸시합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- NuGet 구성 파일에 지정된 기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.

  ```dotnetcli
  dotnet nuget push "*.nupkg"
  ```

  > [!NOTE]
  > 이 명령이 작동하지 않는 경우 이전 버전의 SDK(.NET Core 2.1 SDK 및 이전 버전)에 존재했던 버그 때문일 수 있습니다.
  > 이 문제를 해결하려면 SDK 버전을 업그레이드하거나 대신 `dotnet nuget push "**/*.nupkg"` 명령을 실행합니다.
  
  > [!NOTE]
  > 파일 와일드카드 사용을 수행하는 bash와 같은 셸에는 묶는 따옴표를 사용해야 합니다. 자세한 내용은 [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120)을 참조하세요.

- HTTP(S) 서버에서 409 충돌 응답이 반환되는 경우에도 NuGet 구성 파일에 지정된 기본 푸시 소스에 모든 *.nupkg* 파일을 푸시합니다.

  ```dotnetcli
  dotnet nuget push "*.nupkg" --skip-duplicate
  ```

- 로컬 피드 디렉터리에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.

  ```dotnetcli
  dotnet nuget push "*.nupkg" -s c:\mydir
  ```

  이 명령은 성능 최적화를 위해 권장되는 계층 구조 폴더 구조로 패키지를 저장하지 않습니다. 자세한 내용은 [로컬 피드](/nuget/hosting-packages/local-feeds)를 참조하세요.  
