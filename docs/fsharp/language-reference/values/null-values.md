---
title: Null 값
description: Null 값 사용 되는 방식을 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 03/22/2019
ms.openlocfilehash: 93ac48eddf36981b9df550e76405c3175ae92e0a
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409642"
---
# <a name="null-values"></a>Null 값

이 항목의 null 값은 사용 하는 방법을 설명 합니다. F#입니다.

## <a name="null-value"></a>Null 값

에 null 값은 일반적으로 사용 되지 F# 값 또는 변수입니다. 그러나 null 특정 상황에서 비정상적인 값으로 표시 됩니다. 형식에 정의 된 경우 F#, 하지 않는 한 일반 값으로 null 허용 되지 않습니다 합니다 [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) 특성 형식에 적용 됩니다. Null은 가능한 값 형식을 정의 하는 몇 가지 다른.NET 언어로, 하는 경우 이러한 형식과 상호 작용 하는 경우에 F# 코드는 null 값을 발견할 수 있습니다.

에 정의 된 형식에 대 한 F# 에서 엄격 하 게 사용 F#, 유일한 방법은 사용 하 여 null 값에는 F# 라이브러리는 직접 사용 하는 [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) 또는 [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). 그러나는 F# 다른.NET 언어에서 사용 되는 형식에 작성 되지 않은 API를 사용 하 여 해당 형식을 사용 하는 경우 또는 F#,.NET Framework 같은 null 값이 발생할 수 있습니다.

사용할 수는 `option` 입력 F# 경우 다른.NET 언어를 사용할 수 있는 null 값을 사용 하 여 참조 변수를 사용할 수 있습니다. Null을 대신 사용 하 여는 F# `option` 형식 옵션 값을 사용 하면 `None` 개체가 없는 경우. 옵션 값을 사용 하면 `Some(obj)` 개체를 사용 하 여 `obj` 개체인 경우. 자세한 내용은 [옵션](../options.md)을 참조하세요. 계속을 압축할 수는 `null` 옵션으로 값 경우에 대 한 `Some x`, `x` 일 수 `null`입니다. 이 때문에 사용할 중요 한 것 `None` 값이 `null`합니다.

합니다 `null` 키워드는 유효한 키워드를 F# 하면 언어 및.NET Framework Api 또는 다른.NET 언어로 작성 된 다른 Api를 사용 하 여 작업할 때 사용 해야 합니다. Null 값을 해야 할 수도 있습니다는 두 가지 경우.NET API를 호출 하 고 null 값을 인수로 전달 하는 경우 반환 값 또는.NET 메서드 호출에서 출력 매개 변수를 해석할 때 되며.

Null 값에는.NET 메서드를 전달 하려면 사용 된 `null` 호출 코드의 키워드입니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

.NET 메서드에서 가져온 null 값을 해석할 수 있는 경우 패턴 일치를 사용 합니다. 다음 코드 예제에서 반환 되는 null 값을 해석 하 패턴 일치를 사용 하는 방법을 보여 줍니다 `ReadLine` 입력 스트림의 끝을 넘어 읽으려고 시도할 때.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

Null 값에 대 한 F# 형식을 사용 하는 경우와 같이 다른 방법으로 생성할 수도 있습니다 `Array.zeroCreate`를 호출 하는 `Unchecked.defaultof`합니다. 캡슐화 된 null 값을 유지 하는 이러한 코드를 사용 하 여 주의 해야 합니다. 만 위한 라이브러리에서 F#에서 모든 함수에서 null 값을 확인할 필요가 없습니다. 다른.NET 언어와의 상호 운용성에 대 한 라이브러리를 작성 하는 것이 있으면 null 검사 입력 매개 변수 및 throw를 추가 하는 `ArgumentNullException`, C# 또는 Visual Basic 코드에서와 마찬가지로 합니다.

임의의 값을 null 인지 확인 하려면 다음 코드를 사용할 수 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>참고자료

- [값](index.md)
- [일치 식](../match-expressions.md)
