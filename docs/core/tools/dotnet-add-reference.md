---
title: dotnet add reference 명령
description: dotnet add reference 명령은 프로젝트 간 참조를 추가하는 편리한 옵션을 제공합니다.
ms.date: 06/26/2019
ms.openlocfilehash: dc8bc01a2bff4f2cf3a8af9efb233448d7de337f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733275"
---
# <a name="dotnet-add-reference"></a>dotnet add reference

**이 문서의 적용 대상:**  ✔️ .NET Core 1.x SDK 이상 버전

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>이름

`dotnet add reference` - 프로젝트 간(P2P) 참조를 추가합니다.

## <a name="synopsis"></a>개요

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a>설명

`dotnet add reference` 명령은 프로젝트에 프로젝트 참조를 추가하는 편리한 옵션을 제공합니다. 명령을 실행한 후 `<ProjectReference>` 요소가 프로젝트 파일에 추가됩니다.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>인수

- **`PROJECT`**

  프로젝트 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.

- **`PROJECT_REFERENCES`**

  추가할 프로젝트 간(P2P) 참조입니다. 하나 이상의 프로젝트를 지정합니다. Unix/Linux 기반 시스템에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.

## <a name="options"></a>옵션

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`-f|--framework <FRAMEWORK>`**

  특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 프로젝트 참조를 추가합니다.

- **`--interactive`**

  명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료). .NET Core 3.0 SDK 이후 사용할 수 있습니다.

## <a name="examples"></a>예

- 프로젝트 참조 추가:

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- 현재 디렉터리의 프로젝트에 여러 프로젝트 참조를 추가합니다.

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Linux/Unix에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조 추가:

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
