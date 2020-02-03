---
title: 마우스 캡처
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741024"
---
# <a name="mouse-capture-in-windows-forms"></a>Windows Forms의 마우스 캡처
*마우스 캡처* 는 컨트롤이 모든 마우스 입력의 명령을 사용 하는 경우를 참조 합니다. 컨트롤은 마우스를 캡처 했을 때 포인터가 테두리 내에 있는지 여부에 관계 없이 마우스 입력을 수신 합니다.  
  
## <a name="setting-mouse-capture"></a>마우스 캡처 설정  
 Windows Forms 사용자가 컨트롤에서 마우스 단추를 누를 때 컨트롤이 캡처되고 마우스 단추를 놓을 때 컨트롤이 컨트롤에 의해 해제 됩니다.  
  
 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.Capture%2A> 속성은 컨트롤이 마우스를 캡처 했는지 여부를 지정 합니다. 컨트롤이 마우스 캡처를 손실 하는 경우를 확인 하려면 <xref:System.Windows.Forms.Control.MouseCaptureChanged> 이벤트를 처리 합니다.  
  
 전경 창이 마우스를 캡처할 수 있습니다. 배경 창이 마우스를 캡처하도록 시도 하면 창에서 마우스 포인터가 창의 표시 부분 안에 있을 때 발생 하는 마우스 이벤트에 대 한 메시지만 수신 합니다. 또한 전경 창이 마우스를 캡처한 경우에 여전히 클릭할 수 다른 창 전경으로 상태로 전환 합니다. 마우스를 캡처하면 바로 가기 키가 작동 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [Windows Forms 애플리케이션의 마우스 입력](mouse-input-in-a-windows-forms-application.md)
