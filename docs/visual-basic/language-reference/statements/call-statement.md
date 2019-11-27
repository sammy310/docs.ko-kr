---
title: Call 문
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 7de194ea23827e08c49f4519c1000708a4bd91b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350155"
---
# <a name="call-statement-visual-basic"></a>Call 문(Visual Basic)

`Function`, `Sub`또는 DLL (동적 연결 라이브러리) 프로시저로 제어를 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>요소  

|||
|---|---|
|`procedureName`|필수입니다. 호출할 프로시저의 이름입니다.|
|`argumentList`|(선택 사항) 프로시저를 호출할 때 프로시저에 전달 되는 인수를 나타내는 변수나 식의 목록입니다. 여러 인수를 쉼표로 구분 합니다. `argumentList`를 포함 하는 경우 괄호로 묶어야 합니다.|
|||
  
## <a name="remarks"></a>주의

 프로시저를 호출할 때 `Call` 키워드를 사용할 수 있습니다. 대부분의 프로시저 호출의 경우에는이 키워드를 사용할 필요가 없습니다.

 일반적으로 호출 된 식이 식별자로 시작 하지 않는 경우 `Call` 키워드를 사용 합니다. 다른 용도로는 `Call` 키워드를 사용 하지 않는 것이 좋습니다.

 프로시저에서 값을 반환 하는 경우 `Call` 문은 해당 값을 삭제 합니다.

## <a name="example"></a>예제

 다음 코드에서는 `Call` 키워드가 프로시저를 호출 하는 데 필요한 두 가지 예를 보여 줍니다. 두 예제에서 호출 된 식은 식별자로 시작 하지 않습니다.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>참고 항목

- [Function 문](function-statement.md)
- [Sub 문](sub-statement.md)
- [Declare Statement](declare-statement.md)
- [람다 식](../../programming-guide/language-features/procedures/lambda-expressions.md)
