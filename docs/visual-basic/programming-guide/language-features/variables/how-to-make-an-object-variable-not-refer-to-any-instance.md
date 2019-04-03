---
title: '방법: 변수 개체를 만듭니다. 모든 인스턴스 (Visual Basic)를 참조 하지'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 373d4ae84c44b212ad02b0b4266af75921e40423
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818691"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>방법: 변수 개체를 만듭니다. 모든 인스턴스 (Visual Basic)를 참조 하지
로 설정 하 여 개체 변수에 개체 인스턴스에서 분리할 수 있습니다 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>연결을 끊을 개체 인스턴스에서 모든 개체 변수  
  
-   변수를 설정 합니다 `Nothing` 대입문에서.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 코드에 설정 된 개체 변수의 멤버에 액세스 하려고 `Nothing`, <xref:System.NullReferenceException> 발생 합니다. 개체 변수를 설정 하는 경우 `Nothing` 자주 또는 변수가 초기화 되지 않았습니다 가능한 경우 멤버 액세스에 것이 좋습니다는 `Try...Catch...Finally` 블록입니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 기밀 또는 중요 한 데이터가 포함 된 개체에 대 한 개체 변수를 사용 하는 경우는 변수를 설정할 수 있습니다 `Nothing` 경우 처리 하지 않을 적극적으로 이러한 개체 중 하나를 사용 하 여 합니다. 이 데이터에 액세스 하는 악성 코드의 가능성을 줄일 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.NullReferenceException>
- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
