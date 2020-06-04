---
title: "'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 8e42e0df7b97fb96f468ce37dd4cfc52fad8c596
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358298"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다.
`ReDim` 문에서 `Preserve` 키워드를 사용하여 마지막 차원이 아닌 배열의 차원을 변경하려고 했습니다. `Preserve`를 사용하는 경우 배열의 마지막 차원만 크기를 조정할 수 있습니다. 다른 모든 차원의 경우 기존 배열과 동일한 크기를 지정해야 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `Preserve` 키워드를 제거합니다.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 배열](../programming-guide/language-features/arrays/index.md)
- [Visual Basic의 배열 차원](../programming-guide/language-features/arrays/array-dimensions.md)
- [ReDim 문](../language-reference/statements/redim-statement.md)
- [Dim 문](../language-reference/statements/dim-statement.md)
