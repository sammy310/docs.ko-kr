---
title: dotnet list reference 명령
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 06/26/2019
ms.openlocfilehash: 496cbcd8fa4d921e30b363904ad0273bd5ebacd5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733228"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**이 문서의 적용 대상:**  ✔️ .NET Core 1.x SDK 이상 버전

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>이름

`dotnet list reference` - 프로젝트 간 참조를 나열합니다.

## <a name="synopsis"></a>개요

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a>설명

`dotnet list reference` 명령은 지정된 프로젝트 또는 솔루션에 대한 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.

## <a name="arguments"></a>인수

* **`PROJECT | SOLUTION`**

  참조를 나열하기 위해 사용할 프로젝트 또는 솔루션 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 파일을 검색합니다.

## <a name="options"></a>옵션

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예

* 지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* 현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.

  ```dotnetcli
  dotnet list reference
  ```
