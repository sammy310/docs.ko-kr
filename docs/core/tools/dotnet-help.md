---
title: dotnet help 명령
description: dotnet help 명령은 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.
ms.date: 02/14/2020
ms.openlocfilehash: a59e74a318118b6fd39d1895df02d76daa6fc9e1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463685"
---
# <a name="dotnet-help-reference"></a>dotnet help reference

**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전

## <a name="name"></a>name

`dotnet help` - 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a>설명

`dotnet help` 명령은 docs.microsoft.com에서 지정된 명령에 대한 자세한 정보를 제공하는 참조 페이지를 엽니다.

## <a name="arguments"></a>인수

- **`COMMAND_NAME`**

  .NET Core CLI 명령의 이름입니다. 유효한 CLI 명령 목록은 [CLI 명령](index.md#cli-commands)을 참조하세요.

## <a name="options"></a>옵션

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예

- [dotnet new](dotnet-new.md) 명령에 대한 설명서 페이지를 엽니다.

  ```dotnetcli
  dotnet help new
  ```
