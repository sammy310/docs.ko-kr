---
title: dotnet tool run 명령
description: dotnet tool run 명령은 로컬 도구를 호출합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543829"
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
