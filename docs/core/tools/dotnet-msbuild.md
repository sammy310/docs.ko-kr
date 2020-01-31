---
title: dotnet msbuild 명령
description: dotnet msbuild 명령은 MSBuild 명령줄에 대한 액세스 권한을 제공합니다.
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733193"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>이름

`dotnet msbuild` - 프로젝트 및 모든 종속성을 빌드합니다.

## <a name="synopsis"></a>개요

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>설명

`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다.

이 명령은 SDK 스타일 프로젝트에 대해서만 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능을 갖습니다. 옵션은 모두 동일합니다. 사용 가능한 옵션에 대한 자세한 내용은 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 확인하세요.

[dotnet build](dotnet-build.md) 명령은 `dotnet msbuild -restore -target:Build`와 같습니다. [dotnet build](dotnet-build.md)는 프로젝트를 빌드하는 데 더욱 일반적으로 사용되지만 빌드 대상을 항상 실행하기 때문에 프로젝트를 빌드하지 않으려는 경우에는 `dotnet msbuild`를 사용할 수 있습니다. 예를 들어 프로젝트를 빌드하지 않고 실행할 특정 대상이 있는 경우 `dotnet msbuild`를 사용하여 대상을 지정합니다.

## <a name="examples"></a>예

* 프로젝트 및 해당 종속성을 빌드합니다.

  ```dotnetcli
  dotnet msbuild
  ```

* 릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* 게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* SDK를 통해 포함된 모든 대상이 있는 전체 프로젝트를 확인합니다.

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
