---
title: 선택적 매개 변수는 기본값을 지정해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 01c0abb366e8605a9b153333e645fc3276b6bd16
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821727"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>선택적 매개 변수는 기본값을 지정해야 합니다.
선택적 매개 변수는 매개 변수가 없는 호출 프로시저에서 제공 하는 경우 사용할 수 있는 기본 값을 제공 해야 합니다.  
  
 **오류 ID:** BC30812  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   선택적 매개 변수; 기본값 지정 예를 들어:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고자료

- [선택 사항](../../../visual-basic/language-reference/modifiers/optional.md)
