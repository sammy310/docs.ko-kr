---
title: For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: 9f24dd2a20dc3a4935cd288a20a0e12c1d47bee1
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912349"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다.
A `For Each` 루프에으로 배열을 사용 하 여 해당 *요소* 반복 변수는 하지만 해당 배열을 초기화 합니다.  
  
 다음 문은이 오류를 생성할 수 있습니다 하는 방법을 보여 줍니다.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 첫 번째 `For Each` 문에 요소에 액세스 하는 올바른 방법은 `arrayList`합니다. 두 번째 `For Each` 문은이 오류를 생성 합니다.  
  
 **오류 ID:** BC32039  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 선언에서 초기화를 제거 합니다 *요소* 반복 변수입니다.  
  
## <a name="see-also"></a>참고자료

- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [컬렉션](../../../standard/collections/index.md)
