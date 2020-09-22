---
title: 명시적 대리자 형식 없이 선언된 이벤트에는 'Custom' 한정자를 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 88cdeccd7a3411b57a77116bde64d0a2cf8e537d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874538"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>명시적 대리자 형식 없이 선언된 이벤트에는 'Custom' 한정자를 사용할 수 없습니다.

사용자 지정 이벤트가 아닌 이벤트와 달리 선언에는 이벤트 `Custom Event` `As` 의 대리자 형식을 명시적으로 지정 하는 이벤트 이름 다음에 절이 필요 합니다.  
  
 사용자 지정이 아닌 이벤트는 `As` 절과 명시적 대리자 형식을 사용 하 여 정의 하거나 이벤트 이름 바로 뒤에 매개 변수 목록을 사용 하 여 정의할 수 있습니다.  
  
 **오류 ID:** BC31122  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 사용자 지정 이벤트와 동일한 매개 변수 목록을 사용 하 여 대리자를 정의 합니다.  
  
     예를 들어 `Custom Event` 가로 정의 된 경우 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` 해당 대리자는 다음과 같습니다.  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. 사용자 지정 이벤트의 매개 변수 목록을 `As` 대리자 형식을 지정 하는 절로 바꿉니다.  
  
     예제를 계속 하면 `Custom Event` 선언이 다음과 같이 다시 작성 됩니다.  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a>예제  

 이 예제에서는을 선언 `Custom Event` 하 고 `As` 대리자 형식을 사용 하 여 필수 절을 지정 합니다.  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a>참조

- [Event 문](../statements/event-statement.md)
- [Delegate 문](../statements/delegate-statement.md)
- [이벤트](../../programming-guide/language-features/events/index.md)
