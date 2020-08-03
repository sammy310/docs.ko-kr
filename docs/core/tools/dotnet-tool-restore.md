---
title: dotnet tool restore 명령
description: dotnet tool restore 명령은 현재 디렉터리에 대한 범위에 있는 .NET Core 로컬 도구를 컴퓨터에 설치합니다.
ms.date: 02/14/2020
ms.openlocfilehash: ceef3274ec9d337f8c51009d5a8c27e808b14035
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302674"
---
# <a name="dotnet-tool-restore"></a>dotnet tool restore

**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전

## <a name="name"></a>이름

`dotnet tool restore` - 현재 디렉터리에 대한 범위에 있는 .NET Core 로컬 도구를 컴퓨터에 설치합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a>설명

`dotnet tool restore` 명령은 현재 디렉터리에 대한 범위에 있는 도구 매니페스트 파일을 찾아 여기에 나열된 도구를 설치합니다. 매니페스트 파일에 대한 자세한 내용은 [로컬 도구 설치](global-tools.md#install-a-local-tool) 및 [로컬 도구 호출](global-tools.md#invoke-a-local-tool)을 참조하세요.

## <a name="options"></a>옵션

- **`--configfile <FILE>`**

  사용할 NuGet 구성(*nuget.config*) 파일입니다.

- **`--add-source <SOURCE>`**

  설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.

- **`--tool-manifest <PATH>`**

  매니페스트 파일 경로입니다.

- **`--disable-parallel`**

  여러 프로젝트를 병렬로 복원하지 않습니다.

- **`--ignore-failed-sources`**

  패키지 소스 오류를 경고로 처리합니다.

- **`--no-cache`**

  패키지 및 http 요청을 캐시하지 않습니다.

- **`--interactive`**

  명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`-v|--verbosity <LEVEL>`**

  명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="example"></a>예제

- **`dotnet tool restore`**

  현재 디렉터리에 대한 로컬 도구를 복원합니다.

## <a name="see-also"></a>참조

- [.NET Core 도구](global-tools.md)
- [자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용](local-tools-how-to-use.md)
