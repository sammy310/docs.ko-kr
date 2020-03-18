---
title: dotnet tool run 명령
description: dotnet tool run 명령은 로컬 도구를 호출합니다.
ms.date: 02/14/2020
ms.openlocfilehash: a088cd0b7f4bba014234a8189a42a63aa6d88f4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847848"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전

## <a name="name"></a>이름

`dotnet tool run` - 로컬 도구를 호출합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run <-h|--help>
```

## <a name="description"></a>설명

`dotnet tool run` 명령은 현재 디렉터리에 대한 범위에 있는 도구 매니페스트 파일을 검색합니다. 지정된 도구에 대한 참조를 찾으면 해당 도구를 실행합니다. 자세한 내용은 [로컬 도구 호출](global-tools.md#invoke-a-local-tool)을 참조하세요.

## <a name="arguments"></a>인수

- **`COMMAND_NAME`**

  실행할 도구의 명령 이름입니다.

## <a name="options"></a>옵션

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="example"></a>예제

- **`dotnet tool run dotnetsay`**

  `dotnetsay` 로컬 도구를 실행합니다.

## <a name="see-also"></a>참조

- [.NET Core 도구](global-tools.md)
- [자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용](local-tools-how-to-use.md)
