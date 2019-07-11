---
title: AddressOf 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 098ca95687d8b0e9f4ac90d5c7e0df9a9a0ad950
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760380"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf 연산자(Visual Basic)
특정 절차를 참조 하는 대리자 인스턴스를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>요소  
 `procedurename`  
 필수 요소. 새로 만든된 대리자가 참조 하는 절차를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 합니다 `AddressOf` 연산자는 하위 또는 지정 된 함수를 가리키는 대리자를 만듭니다 `procedurename`합니다. 지정된 된 프로시저 경우 인스턴스 메서드가 대리자 다음 인스턴스와 메서드를 가리킵니다. 그런 다음 대리자가 호출 되 면 지정 된 인스턴스의 지정된 된 메서드 호출 됩니다.  
  
 `AddressOf` 연산자는 대리자 생성자의 피연산자로 사용할 수 있습니다 또는 컴파일러에서 대리자의 형식 결정 될 수 있는 컨텍스트에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 합니다 `AddressOf` 처리 하는 대리자를 지정 하는 연산자는 `Click` 단추의 이벤트입니다.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `AddressOf` 스레드에 대 한 시작 함수를 지정 하는 연산자입니다.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>참고자료

- [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)
