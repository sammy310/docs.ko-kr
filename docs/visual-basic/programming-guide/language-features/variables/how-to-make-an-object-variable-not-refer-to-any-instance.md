---
title: '방법: 개체 변수가 인스턴스를 참조하지 않도록 설정'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352890"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>방법: 개체 변수가 인스턴스를 참조하지 않도록 설정(Visual Basic)
개체 변수를 [Nothing](../../../../visual-basic/language-reference/nothing.md)으로 설정 하 여 개체 인스턴스의 연관을 해제할 수 있습니다.  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>개체 인스턴스에서 개체 변수를 분리 하려면  
  
- 대입문에서 변수를 `Nothing` 설정 합니다.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 코드가 `Nothing`로 설정 된 개체 변수의 멤버에 액세스 하려고 하면 <xref:System.NullReferenceException> 발생 합니다. 개체 변수를 자주 `Nothing` 설정 하거나 변수가 초기화 되지 않은 경우 멤버 액세스를 `Try...Catch...Finally` 블록에 포함 하는 것이 좋습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 기밀 데이터 나 중요 한 데이터가 포함 된 개체에 대해 개체 변수를 사용 하는 경우 해당 개체 중 하나를 사용 하 여 적극적으로 처리 하지 않을 때 변수를 `Nothing` 설정할 수 있습니다. 이렇게 하면 악의적인 코드가 데이터에 액세스 하는 가능성을 줄일 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.NullReferenceException>
- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
