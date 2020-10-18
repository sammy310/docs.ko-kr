---
title: 문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 4fd7577accd0b312ee1e3d2d990d256514d5f5f6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161337"
---
# <a name="bc32005-statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>BC32005: 문이 ' If ' 문 줄 외부의 블록에서 끝날 수 없습니다.

한 줄 문에는 `If` 콜론 (:)으로 구분 된 여러 문이 포함 되어 있습니다 .이 중 하나는 `End` 한 줄 외부의 제어 블록에 대 한 문입니다 `If` . 한 줄 `If` 문은 문을 사용 하지 않습니다 `End If` .

 **오류 ID:** BC32005

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- `If`문이 포함 된 제어 블록 밖으로 한 줄로 된 문을 이동 합니다 `End If` .

## <a name="see-also"></a>참고 항목

- [If...Then...Else 문](../statements/if-then-else-statement.md)
