---
title: '방법: 차단을 방지하는 사용자 지정 이벤트 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 8d73d9c4590afb33e7176f647069cafcb3a9d7d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345143"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>방법: 차단을 방지하는 사용자 지정 이벤트 선언(Visual Basic)
한 이벤트 처리기가 후속 이벤트 처리기를 차단 하지 않는 것이 중요 한 여러 가지 상황이 있습니다. 사용자 지정 이벤트를 사용 하면 이벤트에서 이벤트 처리기를 비동기적으로 호출할 수 있습니다.  
  
 기본적으로 이벤트 선언의 백업 저장소 필드는 모든 이벤트 처리기를 순차적으로 결합 하는 멀티 캐스트 대리자입니다. 즉, 한 처리기를 완료 하는 데 시간이 오래 걸리면 다른 처리기가 완료 될 때까지 차단 됩니다. 잘 작동 하는 이벤트 처리기는 긴 작업 또는 잠재적으로 차단 되는 작업을 수행 하지 않아야 합니다.  
  
 Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하는 대신 사용자 지정 이벤트를 사용 하 여 이벤트 처리기를 비동기적으로 실행할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서 `AddHandler` 접근자는 `Click` 이벤트의 각 처리기에 대 한 대리자를 `EventHandlerList` 필드에 저장 된 <xref:System.Collections.ArrayList>에 추가 합니다.  
  
 코드가 `Click` 이벤트를 발생 시키면 `RaiseEvent` 접근자는 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> 메서드를 사용 하 여 모든 이벤트 처리기 대리자를 비동기적으로 호출 합니다. 이 메서드는 작업자 스레드의 각 처리기를 호출 하 고 즉시 반환 하므로 처리기는 서로를 차단할 수 없습니다.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [방법: 메모리를 절약하는 사용자 지정 이벤트 선언](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
