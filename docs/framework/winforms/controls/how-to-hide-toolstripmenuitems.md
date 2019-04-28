---
title: '방법: ToolStripMenuItems 숨기기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: dc9daa945f2a546548f2cc6ea033378bd9ceff93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941226"
---
# <a name="how-to-hide-toolstripmenuitems"></a>방법: ToolStripMenuItems 숨기기
메뉴 항목 숨기기는 응용 프로그램의 사용자 인터페이스를 제어 하 고 사용자 명령을 제한 하는 방법입니다. 종종 전체 메뉴에 메뉴 항목을 모두 사용할 수 없는 경우 숨기려면 해야 합니다. 이 사용자에 대해 더 적은 방해 요소를 표시합니다. 또한 하려는 숨기고 메뉴 또는 메뉴 항목을 사용 하지 않도록 설정으로 숨기는 것 만으로도 사용자 바로 가기 키를 사용 하 여 메뉴 명령에 액세스 하는 것을 금지 하지 않습니다.  
  
### <a name="to-hide-any-menu-item-programmatically"></a>프로그래밍 방식으로 모든 메뉴 항목을 숨기려면  
  
- 메뉴 항목의 속성을 설정한 메서드 내에서 설정 하는 코드를 추가 합니다 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`입니다.  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
- [방법: ToolStripMenuItems 사용 안 함](how-to-disable-toolstripmenuitems.md)
