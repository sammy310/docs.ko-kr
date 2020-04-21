---
title: 레코드 식 복사 및 업데이트
description: 기존 레코드 또는 익명 레코드를 복사하고 지정된 필드를 업데이트하고 업데이트된 레코드 또는 익명 레코드를 반환하는 '복사 및 업데이트 식'을 작성하는 방법에 대해 알아봅니다.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739280"
---
# <a name="copy-and-update-record-expressions"></a>레코드 식 복사 및 업데이트

*복사 및 업데이트 레코드 표현식은* 기존 레코드를 복사하고 지정된 필드를 업데이트하고 업데이트된 레코드를 반환하는 표현식입니다.

## <a name="syntax"></a>구문

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>설명

레코드 및 익명 레코드는 기본적으로 변경할 수 없으므로 기존 레코드를 업데이트할 수 없습니다. 업데이트된 레코드를 만들려면 레코드의 모든 필드를 다시 지정해야 합니다. 이 작업을 단순화하기 위해 *복사 및 업데이트 식을* 사용할 수 있습니다. 이 식은 기존 레코드를 사용하고 식에서 지정된 필드와 식에서 지정한 누락된 필드를 사용하여 동일한 형식의 새 필드를 만듭니다.

이 기능은 기존 레코드를 복사하고 일부 필드 값을 변경해야 하는 경우에 유용할 수 있습니다.

예를 들어 새로 만든 레코드를 예로 들어 보세요.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

해당 레코드에서 두 필드만 업데이트하려면 *복사 및 업데이트 레코드 식을*사용할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>참고 항목

- [레코드](records.md)
- [익명 레코드](anonymous-records.md)
- [F # 언어 참조](index.md)
