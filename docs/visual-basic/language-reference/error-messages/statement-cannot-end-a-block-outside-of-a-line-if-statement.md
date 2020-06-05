---
title: 문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400320"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.
한 줄 문에는 `If` 콜론 (:)으로 구분 된 여러 문이 포함 되어 있습니다 .이 중 하나는 `End` 한 줄 외부의 제어 블록에 대 한 문입니다 `If` . 한 줄 `If` 문은 문을 사용 하지 않습니다 `End If` .  
  
 **오류 ID:** BC32005  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `If`문이 포함 된 제어 블록 밖으로 한 줄로 된 문을 이동 합니다 `End If` .  
  
## <a name="see-also"></a>참고 항목

- [If...Then...Else 문](../statements/if-then-else-statement.md)
