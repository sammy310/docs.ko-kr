---
title: 마우스 포인터
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: 4e8349effcd9b59045e39b763b4cb8b7d2fceb91
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740962"
---
# <a name="mouse-pointers-in-windows-forms"></a>Windows Forms의 마우스 포인터
커서 라고도 하는 마우스 *포인터*는 마우스를 사용 하 여 사용자 입력에 대 한 화면에 포커스 지점을 지정 하는 비트맵입니다. 이 항목에서는 Windows Forms의 마우스 포인터에 대 한 개요를 제공 하 고 마우스 포인터를 수정 하 고 제어 하는 몇 가지 방법에 대해 설명 합니다.  
  
## <a name="accessing-the-mouse-pointer"></a>마우스 포인터에 액세스  
 마우스 포인터는 <xref:System.Windows.Forms.Cursor> 클래스로 표시 되 고 각 <xref:System.Windows.Forms.Control>에는 해당 컨트롤에 대 한 포인터를 지정 하는 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 속성이 있습니다. <xref:System.Windows.Forms.Cursor> 클래스에는 포인터를 설명 하는 속성 (예: <xref:System.Windows.Forms.Cursor.Position%2A> 및 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 속성)과 포인터의 모양 (예: <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>및 <xref:System.Windows.Forms.Cursor.DrawStretched%2A> 메서드)을 수정할 수 있는 메서드가 포함 되어 있습니다.  
  
## <a name="controlling-the-mouse-pointer"></a>마우스 포인터 제어  
 마우스 포인터를 사용할 수 있는 영역을 제한 하거나 마우스 위치를 변경 하는 경우가 있습니다. <xref:System.Windows.Forms.Cursor>의 <xref:System.Windows.Forms.Cursor.Position%2A> 속성을 사용 하 여 마우스의 현재 위치를 가져오거나 설정할 수 있습니다. 또한 마우스 포인터를 사용 하 여 <xref:System.Windows.Forms.Cursor.Clip%2A> 속성을 설정할 수 있는 영역을 제한할 수 있습니다. 기본적으로 클립 영역은 전체 화면입니다.  
  
## <a name="changing-the-mouse-pointer"></a>마우스 포인터 변경  
 마우스 포인터를 변경 하는 것은 사용자에 게 피드백을 제공 하는 중요 한 방법입니다. 예를 들어 <xref:System.Windows.Forms.Control.MouseEnter> 처리기에서 마우스 포인터를 수정 하 고 <xref:System.Windows.Forms.Control.MouseLeave> 이벤트를 사용 하 여 사용자에 게 계산을 알리고 컨트롤에서 사용자 상호 작용을 제한할 수 있습니다. 경우에 따라 응용 프로그램이 끌어서 놓기 작업에 관여 하는 경우와 같은 시스템 이벤트로 인해 마우스 포인터가 변경 됩니다.  
  
 마우스 포인터를 변경 하는 기본 방법은 컨트롤의 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.Control.DefaultCursor%2A> 속성을 새 <xref:System.Windows.Forms.Cursor>설정 하는 것입니다. 마우스 포인터를 변경 하는 예제는 <xref:System.Windows.Forms.Cursor> 클래스의 코드 예제를 참조 하세요. 또한 <xref:System.Windows.Forms.Cursors> 클래스는 손 모양의 포인터와 같이 다양 한 형식의 포인터에 대 한 <xref:System.Windows.Forms.Cursor> 개체 집합을 노출 합니다. 마우스 포인터가 컨트롤에 있을 때마다 모래 시계와 유사한 대기 포인터를 표시 하려면 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> 속성을 사용 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Cursor>
- [Windows Forms 애플리케이션의 마우스 입력](mouse-input-in-a-windows-forms-application.md)
- [Windows Forms에서의 끌어서 놓기 기능](drag-and-drop-functionality-in-windows-forms.md)
