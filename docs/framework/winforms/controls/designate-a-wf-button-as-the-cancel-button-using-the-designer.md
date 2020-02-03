---
title: 디자이너를 사용 하 여 단추를 취소 단추로 지정
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746057"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정
Windows Form에서 <xref:System.Windows.Forms.Button> 컨트롤이 취소 단추가 되도록 지정할 수 있습니다. 폼의 다른 컨트롤에 포커스가 있는지 여부에 관계 없이 사용자가 ESC 키를 누를 때마다 취소 단추를 클릭 합니다. 이러한 단추는 일반적으로 사용자가 작업을 커밋하지 않고도 신속 하 게 작업을 종료할 수 있도록 프로그래밍 됩니다.

## <a name="to-designate-the-cancel-button"></a>취소 단추를 지정 하려면

1. 단추가 있는 폼을 선택 합니다.

2. **속성** 창에서 양식의 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 <xref:System.Windows.Forms.Button> 컨트롤의 이름으로 설정 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 컨트롤 개요](button-control-overview-windows-forms.md)
- [Windows Forms Button 컨트롤 선택 방법](ways-to-select-a-windows-forms-button-control.md)
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Button 컨트롤](button-control-windows-forms.md)
