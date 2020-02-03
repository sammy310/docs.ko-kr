---
title: 단추 컨트롤을 선택 하는 방법
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740010"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Windows Forms Button 컨트롤 선택 방법
다음과 같은 방법으로 Windows Forms 단추를 선택할 수 있습니다.  
  
- 마우스를 사용 하 여 단추를 클릭 합니다.  
  
- 코드에서 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트를 호출 합니다.  
  
- TAB 키를 눌러 포커스를 단추로 이동한 다음 스페이스바 또는 ENTER 키를 눌러 단추를 선택 합니다.  
  
- 단추에 대 한 액세스 키 (ALT + 밑줄 친 문자)를 누릅니다. 액세스 키에 대 한 자세한 내용은 [방법: Windows Forms 컨트롤에 대 한 선택 키 만들기](how-to-create-access-keys-for-windows-forms-controls.md)를 참조 하세요.  
  
- 단추가 폼의 "수락" 단추인 경우 ENTER 키를 누르면 다른 컨트롤이 포커스를가지고 있는 경우에도 단추를 선택 합니다. 단, 다른 컨트롤이 다른 단추, 여러 줄 텍스트 상자 또는 ENTER 키를 트래핑 하는 사용자 지정 컨트롤인 경우는 제외 됩니다.  
  
- 단추가 폼의 "취소" 단추인 경우 ESC 키를 누르면 다른 컨트롤에 포커스가 있더라도 단추가 선택 됩니다.  
  
- <xref:System.Windows.Forms.Button.PerformClick%2A> 메서드를 호출 하 여 프로그래밍 방식으로 단추를 선택 합니다.  
  
## <a name="see-also"></a>참고 항목

- [Button 컨트롤 개요](button-control-overview-windows-forms.md)
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [Button 컨트롤](button-control-windows-forms.md)
