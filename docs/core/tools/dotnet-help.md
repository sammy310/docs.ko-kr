---
title: dotnet help 명령
description: dotnet help 명령은 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.
ms.date: 08/08/2019
ms.openlocfilehash: 9bb4e54d2634c000707752edf53b38af43c4344e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734238"
---
# <a name="dotnet-help-reference"></a>dotnet help reference

**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a>이름

`dotnet help` - 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.

## <a name="synopsis"></a>개요

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>설명

`dotnet help` 명령은 docs.microsoft.com에서 지정된 명령에 대한 자세한 정보를 제공하는 참조 페이지를 엽니다.

## <a name="arguments"></a>인수

* **`COMMAND_NAME`**

  .NET Core CLI 명령의 이름입니다. 유효한 CLI 명령 목록은 [CLI 명령](index.md#cli-commands)을 참조하세요.

## <a name="options"></a>옵션

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예

* [dotnet new](dotnet-new.md) 명령에 대한 설명서 페이지를 엽니다.

  ```dotnetcli
  dotnet help new
  ```
