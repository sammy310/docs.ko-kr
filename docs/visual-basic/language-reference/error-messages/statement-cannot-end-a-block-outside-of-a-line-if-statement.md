---
title: 문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825796"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.
한 줄 `If` 문에서 여러 개의 문이 콜론 (:), 그 중 하나는 `End` 문을 한 줄의 외부 컨트롤 블록용 `If`합니다. 한 줄 `If` 문을 사용 하지 마십시오는 `End If` 문입니다.  
  
 **오류 ID:** BC32005  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   단일 줄으로 이동 `If` 문을 포함 하는 컨트롤 블록 밖의 `End If` 문입니다.  
  
## <a name="see-also"></a>참고자료

- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
