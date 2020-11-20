---
title: dotnet tool search 명령
description: dotnet tool search 명령은 NuGet.org에 게시된 .NET 도구를 검색합니다.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634144"
---
# <a name="dotnet-tool-search"></a>dotnet tool search

**이 문서의 적용 대상:** ✔️ .NET 5.0 SDK 이상 버전

## <a name="name"></a>Name

`dotnet tool search` - NuGet에 게시된 모든 [.NET 도구](global-tools.md)를 검색합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a>Description

`dotnet tool search` 명령은 NuGet에서 .NET 전역 도구, 도구 경로 또는 로컬 도구로 사용할 수 있는 도구를 검색하는 방법을 제공합니다. 이 명령은 도구 이름 및 메타데이터(예: 제목, 설명, 태그)를 검색합니다.

이 명령은 [NuGet 검색 API](/nuget/api/search-query-service-resource#search-for-packages)를 사용합니다. `packageType=dotnettool`을 필터링하여 .NET 도구 패키지만 선택합니다.

## <a name="options"></a>옵션

- **`--detail`**

  쿼리에서 자세한 결과를 표시합니다.

- **`--prerelease`**

  시험판 패키지를 포함합니다.

- **`--skip <NUMBER>`**

  건너뛸 쿼리 결과 수를 지정합니다. 페이지 매김에 사용됩니다.

- **`--take <NUMBER>`**

  표시할 쿼리 결과 수를 지정합니다. 페이지 매김에 사용됩니다.

- **`-h|--help`**

  명령줄 도움말을 표시합니다.

## <a name="examples"></a>예

- NuGet.org에서 패키지 이름 또는 설명에 “format”이 포함된 .NET 도구를 검색합니다.

  ```dotnetcli
  dotnet tool search format
  ```

  출력은 다음 예와 같습니다.

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- NuGet.org에서 패키지 이름 또는 메타데이터에 “format”이 포함된 .NET 도구를 검색하고 첫 번째 결과만 표시하고 자세한 보기를 표시합니다.

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  출력은 다음 예와 같습니다.

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a>참조

- [.NET 도구](global-tools.md)
- [자습서: .NET CLI를 사용하여 .NET 전역 도구 설치 및 사용](global-tools-how-to-use.md)
- [자습서: .NET CLI를 사용하여 .NET 로컬 도구 설치 및 사용](local-tools-how-to-use.md)
