---
title: 레코드 식 복사 및 업데이트
description: 필드를 지정 된 '복사 및 업데이트 하는 식' 기존 레코드 또는 익명 레코드, 업데이트를 복사를 작성 하는 업데이트 된 레코드 또는 익명 레코드를 반환 하는 방법에 알아봅니다.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: d16f5ca337047ab2eecc8828b21d8a423bf39a1f
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041735"
---
# <a name="copy-and-update-record-expressions"></a>레코드 식 복사 및 업데이트

A *복사 및 업데이트 레코드 식* 은 기존 레코드를 복사 하 고, 지정 된 필드를 업데이트, 업데이트 된 레코드를 반환 하는 식입니다.

## <a name="syntax"></a>구문

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>설명

이 가능 기존 레코드는 업데이트 되지 및 익명 레코드가 기본적으로 변경할 수 없습니다. 업데이트 된 레코드는 레코드의 모든 필드를 만들려면 해야 다시 지정 해야 합니다. 이 작업을 간소화 하는 *복사 및 업데이트 식* 사용할 수 있습니다. 이 식은 기존 레코드를 사용, 식에서 지정 된 필드와 식으로 지정 된 누락 된 필드를 사용 하 여 동일한 유형의 새 항목을 만듭니다.

기존 레코드를 복사 하 고 필드 값의 일부 변경 해야 할 경우에 유용할 수 있습니다.

사용 예를 들어 새로 만든된 레코드입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

사용 하 여 해당 레코드의 필드에만 업데이트 하는 경우는 *복사 및 업데이트 레코드 식* 다음과 같이 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>참고자료

- [레코드](records.md)
- [익명 기록](anonymous-records.md)
- [F# 언어 참조](index.md)
