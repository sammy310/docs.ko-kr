---
title: 진입점
description: 진입점으로 설정 하는 방법을 알아봅니다는 F# 실행 공식적으로 시작 하는 실행 파일로 컴파일된 프로그램입니다.
ms.date: 05/16/2016
ms.openlocfilehash: c7aedda5834fb224507bfcecd4688978efa26547
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645447"
---
# <a name="entry-point"></a>진입점

이 설명으로 진입점을 설정 하는 데 사용 하는 메서드는 F# 프로그램입니다.

## <a name="syntax"></a>구문

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>설명

이전 구문에서 *let-함수-바인딩에* 함수의 정의 `let` 바인딩.

실행 파일은 실행 공식적으로 시작 되는 컴파일된 프로그램 진입점입니다. 에 대 한 진입점을 지정는 F# 적용 하 여 응용 프로그램을 `EntryPoint` 프로그램의 특성 `main` 함수입니다. 이 함수 (사용 하 여 만든를 `let` 바인딩) 마지막으로 컴파일된 파일에 마지막 함수 여야 합니다. 마지막으로 컴파일된 파일은 프로젝트에서 마지막 파일 또는 명령줄에 전달 되는 마지막 파일.

진입점 함수 형식이 `string array -> int`합니다. 명령줄에 제공 된 인수에 전달 되는 `main` 문자열 배열에는 함수입니다. 배열의 첫 번째 요소는 첫 번째 인수입니다. 실행 파일의 이름은 다른 언어로 이므로 배열에 포함 되지 않습니다. 반환 값은 프로세스에 대 한 종료 코드로 사용 됩니다. 0에는 일반적으로 성공을 나타냅니다. 0이 아닌 값에 오류가 발생 합니다. 규칙은 없습니다 구체적인 의미를 나타내는 0이 아닌 반환 코드입니다. 반환 코드의 의미는 응용 프로그램 마다 다릅니다.

다음 예제에서는 간단한 `main` 함수입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

명령줄을 사용 하 여이 코드를 실행할 때 `EntryPoint.exe 1 2 3`, 출력은 다음과 같습니다.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>암시적 진입점

프로그램에 없는 **EntryPoint** 진입점을 컴파일해야 하 고 마지막 파일의 최상위 수준 바인딩을 명시적으로 나타내는 특성의 진입점으로 사용 됩니다.

## <a name="see-also"></a>참고자료

- [함수](index.md)
- [let 바인딩](let-bindings.md)
