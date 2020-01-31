---
title: 마우스 입력이 작동 하는 방식
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 1164974e65ca1e96c0650569626ad4140baf004e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739628"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Windows Forms에서 마우스 입력이 작동하는 방식
마우스 입력 수신 및 처리는 모든 Windows 응용 프로그램에서 중요 한 부분입니다. 마우스 이벤트를 처리 하 여 응용 프로그램에서 작업을 수행 하거나 마우스 위치 정보를 사용 하 여 적중 테스트 또는 기타 작업을 수행할 수 있습니다. 또한 응용 프로그램의 컨트롤이 마우스 입력을 처리 하는 방식을 변경할 수 있습니다. 이 항목에서는 이러한 마우스 이벤트에 대해 자세히 설명 하 고 마우스에 대 한 시스템 설정을 가져오고 변경 하는 방법을 설명 합니다. 마우스 이벤트와 함께 제공 되는 데이터 및 마우스 클릭 이벤트가 발생 하는 순서에 대 한 자세한 내용은 [Windows Forms의 마우스 이벤트](mouse-events-in-windows-forms.md)를 참조 하세요.  
  
## <a name="mouse-location-and-hit-testing"></a>마우스 위치 및 적중 테스트  
 사용자가 마우스를 움직이면 운영 체제가 마우스 포인터를 이동 합니다. 마우스 포인터에는 운영 체제가 추적 하 고 포인터의 위치로 인식 하는 핫 스폿 이라고 하는 단일 픽셀이 있습니다. 사용자가 마우스를 이동 하거나 마우스 단추를 누르면 <xref:System.Windows.Forms.Cursor.HotSpot%2A>를 포함 하는 <xref:System.Windows.Forms.Control>에서 적절 한 마우스 이벤트를 발생 시킵니다. 마우스 이벤트를 처리할 때 또는 <xref:System.Windows.Forms.Cursor> 클래스의 <xref:System.Windows.Forms.Cursor.Position%2A> 속성을 사용 하 여 <xref:System.Windows.Forms.MouseEventArgs>의 <xref:System.Windows.Forms.MouseEventArgs.Location%2A> 속성을 사용 하 여 현재 마우스 위치를 가져올 수 있습니다. 이후에는 마우스 위치 정보를 사용 하 여 적중 테스트를 수행한 다음 마우스 위치에 따라 동작을 수행할 수 있습니다. 적중 테스트 기능은 <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> 및 <xref:System.Windows.Forms.DataGridView> 컨트롤과 같은 Windows Forms의 여러 컨트롤에 기본 제공 됩니다. 적절 한 마우스 <xref:System.Windows.Forms.Control.MouseHover> 이벤트와 함께 사용 됩니다. 예를 들어 적중 테스트는 응용 프로그램에서 특정 작업을 수행 해야 하는 시기를 결정 하는 데 매우 유용 합니다.  
  
## <a name="mouse-events"></a>마우스 이벤트  
 마우스 입력에 응답 하는 기본적인 방법은 마우스 이벤트를 처리 하는 것입니다. 다음 표에서는 마우스 이벤트를 보여 주고 이벤트가 발생 하는 시기를 설명 합니다.  
  
|마우스 이벤트|설명|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|이 이벤트는 마우스 단추를 놓을 때, 일반적으로 <xref:System.Windows.Forms.Control.MouseUp> 이벤트 이전에 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다. 클릭이 발생 한 경우를 결정 해야 하는 경우이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.MouseClick>|이 이벤트는 사용자가 마우스로 컨트롤을 클릭할 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다. 클릭이 발생할 때 마우스에 대 한 정보를 가져와야 하는 경우이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|이 이벤트는 컨트롤을 두 번 클릭할 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다. 두 번 클릭이 발생 한 경우를 결정 해야 하는 경우이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|이 이벤트는 사용자가 마우스로 컨트롤을 두 번 클릭할 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다. 두 번 클릭이 발생할 때 마우스에 대 한 정보를 가져와야 할 때이 이벤트를 처리 합니다.|  
|<xref:System.Windows.Forms.Control.MouseDown>|이 이벤트는 마우스 포인터가 컨트롤 위에 있을 때 사용자가 마우스 단추를 누를 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|이 이벤트는 컨트롤의 형식에 따라 마우스 포인터가 컨트롤의 테두리 또는 클라이언트 영역에 들어가면 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseHover>|이 이벤트는 마우스 포인터를 컨트롤 위에 놓았을 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|이 이벤트는 컨트롤의 형식에 따라 마우스 포인터가 컨트롤의 테두리 또는 클라이언트 영역을 벗어날 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseMove>|이 이벤트는 컨트롤 위에 있는 동안 마우스 포인터를 움직이면 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseUp>|이 이벤트는 마우스 포인터가 컨트롤 위에 있을 때 사용자가 마우스 단추를 놓을 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|이 이벤트는 컨트롤에 포커스가 있는 동안 사용자가 마우스 휠을 돌릴 때 발생 합니다. 이 이벤트의 처리기는 <xref:System.Windows.Forms.MouseEventArgs> 형식의 인수를 받습니다. <xref:System.Windows.Forms.MouseEventArgs>의 <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> 속성을 사용 하 여 마우스가 스크롤 된 정도를 확인할 수 있습니다.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>마우스 입력 변경 및 시스템 설정 검색  
 컨트롤에서 파생 하 고 <xref:System.Windows.Forms.Control.GetStyle%2A> 및 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 사용 하 여 컨트롤에서 마우스 입력을 처리 하는 방법을 검색 하 고 변경할 수 있습니다. <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드는 <xref:System.Windows.Forms.ControlStyles> 값의 비트 조합을 사용 하 여 컨트롤이 표준 클릭 또는 두 번 클릭 동작을 수행 하거나 컨트롤이 자체 마우스 처리를 처리할지 여부를 결정 합니다. 또한 <xref:System.Windows.Forms.SystemInformation> 클래스에는 마우스의 기능을 설명 하 고 마우스가 운영 체제와 상호 작용 하는 방식을 지정 하는 속성이 포함 되어 있습니다. 다음 표에서는 이러한 속성을 요약 합니다.  
  
|속성|설명|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|운영 체제에서 두 번 클릭을 두 번 클릭 하는 것으로 간주 하도록 사용자가 두 번 클릭 해야 하는 영역의 크기 (픽셀 단위)를 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|마우스 작업을 두 번 클릭 하는 것으로 간주 하기 위해 운영 체제에서 첫 번째 클릭과 두 번째 클릭 사이에 경과할 수 있는 최대 시간 (밀리초)을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|마우스의 단추 수를 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|마우스 왼쪽 단추와 오른쪽 단추의 기능이 바뀌었는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|마우스 호버 메시지가 생성되기 전에 마우스 포인터가 마우스 호버 시간 동안 머물러야 하는 사각형의 크기를 픽셀 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|마우스 호버 메시지가 생성되기 전에 마우스 포인터가 호버 사각형에 머물러야 하는 시간을 밀리초 단위로 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|마우스가 설치 되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|현재 마우스 속도를 나타내는 값 (1 ~ 20)을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|휠 마우스가 설치되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|단일 마우스 휠 회전의 증가값에 대 한 델타 값 크기를 가져옵니다.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|마우스 휠을 돌릴 때 스크롤되는 줄 수를 가져옵니다.|  
  
## <a name="see-also"></a>참조

- [Windows Forms 애플리케이션의 마우스 입력](mouse-input-in-a-windows-forms-application.md)
- [Windows Forms의 마우스 캡처](mouse-capture-in-windows-forms.md)
- [Windows Forms의 마우스 포인터](mouse-pointers-in-windows-forms.md)
