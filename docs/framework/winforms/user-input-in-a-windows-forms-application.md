---
title: Windows Forms 앱의 사용자 입력
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 8e82276f14519c4ef54948744c93014232bdff52
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734813"
---
# <a name="user-input-in-a-windows-forms-application"></a>Windows Forms 응용 프로그램의 사용자 입력
Windows Forms에서 사용자 입력은 Windows 메시지 형식으로 응용 프로그램에 전송 됩니다. 일련의 재정의 가능한 메서드는 응용 프로그램, 폼 및 컨트롤 수준에서 이러한 메시지를 처리 합니다. 이러한 메서드는 마우스 및 키보드 메시지를 받을 때 마우스 또는 키보드 입력에 대 한 정보를 가져오기 위해 처리할 수 있는 이벤트를 발생 시킵니다. 대부분의 경우 Windows Forms 응용 프로그램은 이러한 이벤트를 처리 하 여 모든 사용자 입력을 처리할 수 있습니다. 응용 프로그램, 폼 또는 컨트롤이 메시지를 수신 하기 전에 특정 메시지를 가로채기 위해 메시지를 처리 하는 메서드 중 하나를 재정의 해야 하는 경우도 있습니다.  
  
## <a name="mouse-and-keyboard-events"></a>마우스 및 키보드 이벤트  
 모든 Windows Forms 컨트롤은 마우스 및 키보드 입력과 관련 된 이벤트 집합을 상속 합니다. 예를 들어, 컨트롤은 <xref:System.Windows.Forms.Control.KeyPress> 이벤트를 처리 하 여 누른 키의 문자 코드를 확인 하거나 컨트롤이 <xref:System.Windows.Forms.Control.MouseClick> 이벤트를 처리 하 여 마우스 클릭 위치를 확인할 수 있습니다. 마우스 및 키보드 이벤트에 대 한 자세한 내용은 Windows Forms [키보드 이벤트](using-keyboard-events.md) 및 [마우스 이벤트](mouse-events-in-windows-forms.md)사용을 참조 하세요.  
  
## <a name="methods-that-process-user-input-messages"></a>사용자 입력 메시지를 처리 하는 메서드  
 폼과 컨트롤에는 메시지 큐의 서로 다른 지점에서 Windows 메시지를 처리 하는 재정의 가능한 메서드 집합과 <xref:System.Windows.Forms.IMessageFilter> 인터페이스에 대 한 액세스 권한이 있습니다. 이러한 메서드에는 모두 Windows 메시지의 하위 수준 세부 정보를 캡슐화 하는 <xref:System.Windows.Forms.Message> 매개 변수가 있습니다. 이러한 메서드를 구현 하거나 재정의 하 여 메시지를 검사 한 다음 메시지를 사용 하거나 메시지 큐의 다음 소비자에 게 전달할 수 있습니다. 다음 표에서는 Windows Forms의 모든 Windows 메시지를 처리 하는 메서드를 보여 줍니다.  
  
|메서드|참고|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|이 메서드는 응용 프로그램 수준에서 지연 된 (게시 된) Windows 메시지를 가로챕니다.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|이 메서드는 처리 되기 전에 폼 및 컨트롤 수준에서 Windows 메시지를 가로챕니다.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|이 메서드는 폼 및 컨트롤 수준에서 Windows 메시지를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|이 메서드는 폼 및 컨트롤 수준에서 Windows 메시지의 기본 처리를 수행 합니다. 이는 창의 최소 기능을 제공 합니다.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|이 메서드는 처리 된 후 폼 및 컨트롤 수준에서 메시지를 가로챕니다. 이 메서드를 호출 하려면 <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> 스타일 비트를 설정 해야 합니다.|  
  
 키보드 및 마우스 메시지는 이러한 메시지 형식과 관련 된 재정의 가능한 추가 메서드 집합에 의해 처리 됩니다. 자세한 내용은 [키보드 입력 작동 방식](how-keyboard-input-works.md) 및 [Windows Forms에서 마우스 입력이 작동](how-mouse-input-works-in-windows-forms.md)하는 방식을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [Windows Forms에 사용자 입력](user-input-in-windows-forms.md)
- [Windows Forms 애플리케이션의 키보드 입력](keyboard-input-in-a-windows-forms-application.md)
- [Windows Forms 애플리케이션의 마우스 입력](mouse-input-in-a-windows-forms-application.md)
