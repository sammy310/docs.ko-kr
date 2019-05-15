---
title: '리소스 관리: Use 키워드'
description: 알아봅니다는 F# 키워드 'use' 및 'using' 함수를 초기화 및 리소스의 해제를 제어할 수 있습니다.
ms.date: 05/16/2016
ms.openlocfilehash: 3389f84713ec7cf5459dd0132249970f0e2ef3e0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641701"
---
# <a name="resource-management-the-use-keyword"></a>리소스 관리: Use 키워드

키워드에 설명 `use` 하며 `using` 함수, 초기화 및 리소스의 해제를 제어할 수 있습니다.

## <a name="resources"></a>자료

용어 *리소스* 둘 이상의 방식으로 사용 됩니다. 예, 리소스와 같은 문자열, 그래픽 및 like, 하지만이 컨텍스트에서 응용 프로그램을 사용 하는 데이터를 수 있습니다 *리소스* 그래픽 장치 컨텍스트, 파일 핸들, 네트워크와 같은 소프트웨어 또는 운영 체제 리소스에 대 한 참조 및 데이터베이스 연결, 대기 핸들 등과 같은 동시성 개체입니다. 응용 프로그램에서 이러한 리소스를 사용 하 여 운영 체제 또는 다른 응용 프로그램에 제공 될 수 있도록 풀에 리소스의 이후 릴리스를 뒤에 다른 리소스 공급자에서 리소스를 확보를 해야 합니다. 문제는 응용 프로그램은 공용 풀으로 리소스를 해제 하지 않아 때 발생 합니다.

## <a name="managing-resources"></a>리소스 관리

책임 지 고 효율적으로 응용 프로그램에서 리소스를 관리 하려면 신속 하 게 하 고 예측 가능한 방식으로 리소스를 해제 해야 합니다. .NET Framework를 사용 하면 제공 하 여이 작업을 수행 합니다 `System.IDisposable` 인터페이스입니다. 구현 하는 형식을 `System.IDisposable` 에 `System.IDisposable.Dispose` 메서드를 올바르게 리소스를 해제 합니다. 응용 프로그램을 잘 작성 된 `System.IDisposable.Dispose` 제한 된 리소스를 보유 하는 모든 개체에 더 이상 필요 없는 경우 즉시 호출 됩니다. 다행 스럽게도 대부분의.NET 언어 제공이 쉽게 지원 및 F# 도 예외가 아닙니다. Dispose 패턴을 지 원하는 두 가지 유용한 언어 구문이: 합니다 `use` 바인딩 및 `using` 함수입니다.

## <a name="use-binding"></a>바인딩을 사용합니다

합니다 `use` 키워드에는 유사한 폼을는 `let` 바인딩:

use *value* = *expression*

와 동일한 기능을 제공 하는 `let` 바인딩 하지만 호출을 추가 합니다 `Dispose` 값 범위를 벗어날 때 값에 있습니다. 컴파일러 경우 값은 값의 null 검사를 삽입 하는 참고 `null`에 대 한 호출 `Dispose` 시도 되지 않습니다.

다음 예제에서는 파일을 사용 하 여 자동으로 종결 하는 방법의 `use` 키워드입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> 사용할 수 있습니다 `use` 계산 식에 사용자 지정된 버전의 경우는 `use` 식이 사용 됩니다. 자세한 내용은 [시퀀스](sequences.md)를 [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.

## <a name="using-function"></a>함수를 사용 하 여

`using` 함수는 다음과 같은 형식을 갖습니다.

`using` (*expression1*) *함수 또는 람다*

에 `using` 식을 *expression1* 삭제 해야 하는 개체를 만듭니다. 결과인 *expression1* (삭제 해야 하는 개체)가 인수로 *값*를 *함수 또는 람다*, 단일 필요한 함수 중 하나는 생성 된 값과 일치 하는 형식 인수의 남은 *expression1*, 또는 해당 형식의 인수를 필요로 하는 람다 식입니다. 런타임에서 호출 된 함수의 실행의 끝 `Dispose` 리소스를 해제 (값이 아니라면 `null`, Dispose에 대 한 호출 시도 하지는 경우).

다음 예제는 `using` 람다 식 사용 하 여 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

에서는 다음 예제는 `using` 함수를 사용 하 여 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

일부 인수가 이미 적용 하는 함수 일 수는 참고 합니다. 다음 코드 예제에서는 이 작업을 보여줍니다. 문자열을 포함 하는 파일을 만들면 `XYZ`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

합니다 `using` 함수 및 `use` 바인딩은 거의 같은 방식으로 동일한 작업을 수행 합니다. 합니다 `using` 키워드 좀 더 잘 제어할 때 `Dispose` 라고 합니다. 사용 하는 경우 `using`, `Dispose` 사용 하는 경우, 함수 또는 람다 식의 끝에서 호출 되는 `use` 키워드를 `Dispose` 포함 하는 코드 블록의 끝에 호출 됩니다. 일반적으로 사용 하려는 `use` of를 `using` 함수입니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
