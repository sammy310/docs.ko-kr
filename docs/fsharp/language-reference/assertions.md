---
title: 어설션
description: "' Assert ' 식을 F# 프로그래밍 언어에서 식을 테스트 하는 데 사용 하는 디버깅 기능으로 사용 하는 방법에 대해 알아봅니다."
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799066"
---
# <a name="assertions"></a>어설션

`assert` 식은 식을 테스트 하는 데 사용할 수 있는 디버깅 기능입니다. 디버그 모드에서 실패 시 어설션에서 시스템 오류 대화 상자를 생성합니다.

## <a name="syntax"></a>구문

```fsharp
assert condition
```

## <a name="remarks"></a>주의

`assert` 식의 형식이 `bool -> unit`입니다.

`assert` 함수는 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>으로 확인 됩니다. 즉, 해당 동작은 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>를 직접 호출 하는 것과 동일 합니다.

디버그 모드에서 컴파일할 때만 어설션 검사가 활성화 됩니다. 즉, 상수 `DEBUG` 정의 된 경우입니다. 프로젝트 시스템에서 기본적으로 `DEBUG` 상수는 디버그 구성에 정의 되어 있지만 릴리스 구성에는 정의 되어 있지 않습니다.

예외 처리를 사용 하 F# 여 어설션 실패 오류를 catch 할 수 없습니다.

## <a name="example"></a>예제

다음 코드 예제에서는 `assert` 식을 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>참조

- [F# 언어 참조](index.md)
