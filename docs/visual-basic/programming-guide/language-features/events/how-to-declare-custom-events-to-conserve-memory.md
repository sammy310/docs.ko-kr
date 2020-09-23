---
title: '방법: 메모리를 절약하는 사용자 지정 이벤트 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 78934e3e5ae7d5a3f5867c99a9f1db760c65ecbf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075124"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>방법: 메모리를 절약하는 사용자 지정 이벤트 선언(Visual Basic)

응용 프로그램에서 메모리 사용량을 낮게 유지 하는 것이 중요 한 여러 가지 상황이 있습니다. 사용자 지정 이벤트를 사용 하면 응용 프로그램에서 처리 하는 이벤트에 대해서만 메모리를 사용할 수 있습니다.  
  
 기본적으로 클래스가 이벤트를 선언할 때 컴파일러는 이벤트 정보를 저장 하는 필드에 대 한 메모리를 할당 합니다. 클래스에 사용 되지 않는 이벤트가 많이 있는 경우에는 불필요 하 게 메모리를 사용 합니다.  
  
 Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하는 대신 사용자 지정 이벤트를 사용 하 여 메모리 사용을 보다 신중 하 게 관리할 수 있습니다.  
  
## <a name="example"></a>예제  

 이 예제에서 클래스는 필드에 저장 된 클래스의 인스턴스 하나를 사용 하 여 <xref:System.ComponentModel.EventHandlerList> `Events` 사용 중인 이벤트에 대 한 정보를 저장 합니다. <xref:System.ComponentModel.EventHandlerList>클래스는 대리자를 포함 하도록 디자인 된 최적화 된 목록 클래스입니다.  
  
 클래스의 모든 이벤트는 필드를 사용 `Events` 하 여 각 이벤트를 처리 하는 메서드를 추적 합니다.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>참조

- <xref:System.ComponentModel.EventHandlerList>
- [이벤트](index.md)
- [방법: 차단을 방지하는 사용자 지정 이벤트 선언](how-to-declare-custom-events-to-avoid-blocking.md)
