---
title: 람다 식은 'Select Case' 문의 첫 번째 식에 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 9f200ea44e7505c407c7df56e596435024394875
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873872"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>람다 식은 'Select Case' 문의 첫 번째 식에 사용할 수 없습니다.

문에서는 테스트 식에 람다 식을 사용할 수 없습니다 `Select Case` . 람다 식 정의에서 함수를 반환 하 고 문의 테스트 식이 `Select Case` 기본 데이터 형식 이어야 합니다.  
  
 다음 코드는이 오류를 발생 시킵니다.  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **오류 ID:** BC36635  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 코드를 검사하여 `If...Then...Else` 문과 같은 다른 조건부 생성이 적합한지 결정합니다.  
  
- 다음 코드와 같이 함수를 호출 하려고 했을 수 있습니다.  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>참조

- [람다 식](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [If...Then...Else 문](../statements/if-then-else-statement.md)
- [Select...Case 문](../statements/select-case-statement.md)
