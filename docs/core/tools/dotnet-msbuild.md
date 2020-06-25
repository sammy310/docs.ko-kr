---
title: dotnet msbuild 명령
description: dotnet msbuild 명령은 MSBuild 명령줄에 대한 액세스 권한을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803170"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전

## <a name="name"></a>이름

`dotnet msbuild` - 프로젝트 및 모든 종속성을 빌드합니다. 참고: 솔루션 또는 프로젝트 파일이 여러 개인 경우 하나를 지정해야 할 수도 있습니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>설명

`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다.

이 명령은 SDK 스타일 프로젝트에 대해서만 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능을 갖습니다. 옵션은 모두 동일합니다. 사용 가능한 옵션에 대한 자세한 내용은 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 확인하세요.

[dotnet build](dotnet-build.md) 명령은 `dotnet msbuild -restore`와 같습니다. 프로젝트를 빌드하지 않고 특정 대상을 실행하려는 경우 `dotnet build` 또는 `dotnet msbuild`를 사용하고 대상을 지정합니다.

## <a name="examples"></a>예

- 프로젝트 및 해당 종속성을 빌드합니다.

  ```dotnetcli
  dotnet msbuild
  ```

- 릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- 게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- SDK를 통해 포함된 모든 대상이 있는 전체 프로젝트를 확인합니다.

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```
