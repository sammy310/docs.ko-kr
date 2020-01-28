---
title: '방법: 단일 이벤트 처리기에 여러 이벤트 연결'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739600"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결
응용 프로그램 디자인에서 여러 이벤트에 대해 단일 이벤트 처리기를 사용 해야 하거나 여러 이벤트에서 동일한 절차를 수행 해야 하는 경우가 있을 수 있습니다. 예를 들어, 동일한 기능을 노출 하는 경우 메뉴 명령에서 폼의 단추와 동일한 이벤트를 발생 시 키도 록 하는 것이 효과적입니다. 이 작업을 수행 하려면에서 C# 속성 창의 이벤트 뷰를 사용 하거나 Visual Basic 코드 편집기의 **클래스 이름** 및 **메서드 이름** 드롭다운 상자를 `Handles` 사용 합니다.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Visual Basic에서 단일 이벤트 처리기에 여러 이벤트를 연결 하려면  
  
1. 폼을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기**를 선택 합니다.  
  
2. **클래스 이름** 드롭다운 상자에서 이벤트 처리기를 처리 하려는 컨트롤 중 하나를 선택 합니다.  
  
3. **메서드 이름** 드롭다운 상자에서 이벤트 처리기가 처리할 이벤트 중 하나를 선택 합니다.  
  
4. 코드 편집기는 적절 한 이벤트 처리기를 삽입 하 고 메서드 내에 삽입 지점을 배치 합니다. 아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤에 대 한 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. 처리 하려는 다른 이벤트를 `Handles` 절에 추가 합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. 이벤트 처리기에 적절 한 코드를 추가 합니다.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>C\#에서 단일 이벤트 처리기에 여러 이벤트를 연결 하려면
  
1. 이벤트 처리기를 연결 하려는 컨트롤을 선택 합니다.  
  
2. 속성 창에서 **이벤트** 단추 (![이벤트 단추](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow"))를 클릭 합니다.  
  
3. 처리 하려는 이벤트의 이름을 클릭 합니다.  
  
4. 이벤트 이름 옆의 값 섹션에서 드롭다운 단추를 클릭 하 여 처리 하려는 이벤트의 메서드 시그니처와 일치 하는 기존 이벤트 처리기의 목록을 표시 합니다.  
  
5. 목록에서 적절 한 이벤트 처리기를 선택 합니다.  
  
     기존 이벤트 처리기에 이벤트를 바인딩하기 위해 코드를 폼에 추가 합니다.  
  
## <a name="see-also"></a>참조

- [Windows Forms에서 이벤트 처리기 만들기](creating-event-handlers-in-windows-forms.md)
- [이벤트 처리기 개요](event-handlers-overview-windows-forms.md)
