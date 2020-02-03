---
title: 컨트롤 개발에 대 한 기본 사항
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: fab0a76e2f9fdb7e2f89e9d6a10dd9c522a6d8e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739913"
---
# <a name="windows-forms-control-development-basics"></a>Windows Forms 컨트롤 개발 기본 사항
Windows Forms 컨트롤은 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>에서 직접 또는 간접적으로 파생 되는 클래스입니다. 다음 목록에서는 Windows Forms 컨트롤을 개발 하는 일반적인 시나리오에 대해 설명 합니다.  
  
- 기존 컨트롤을 결합 하 여 복합 컨트롤을 작성 합니다.  
  
     복합 컨트롤은 컨트롤로 재사용할 수 있는 사용자 인터페이스를 캡슐화 합니다. 복합 컨트롤의 예로는 텍스트 상자와 다시 설정 단추를 구성 하는 컨트롤이 있습니다. 시각적 디자이너는 복합 컨트롤을 만들기 위한 다양 한 지원을 제공 합니다. 복합 컨트롤을 작성 하려면 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>에서 파생 합니다. 기본 클래스 <xref:System.Windows.Forms.UserControl> 자식 컨트롤에 대 한 키보드 라우팅을 제공 하 고 자식 컨트롤이 그룹으로 작동할 수 있도록 합니다. 자세한 내용은 [Windows Forms 복합 컨트롤 개발](developing-a-composite-windows-forms-control.md)을 참조하세요.  
  
- 기존 컨트롤을 확장 하 여 사용자 지정 하거나 해당 기능에 추가  
  
     색을 변경할 수 없는 단추와 클릭 한 횟수를 추적 하는 추가 속성이 있는 단추는 확장 된 컨트롤의 예입니다. 클래스에서 파생 하 고 속성, 메서드 및 이벤트를 재정의 하거나 추가 하 여 Windows Forms 컨트롤을 사용자 지정할 수 있습니다.  
  
- 기존 컨트롤을 결합 하거나 확장 하지 않는 컨트롤 제작  
  
     이 시나리오에서는 기본 클래스 <xref:System.Windows.Forms.Control>에서 컨트롤을 파생 시킵니다. 기본 클래스의 속성, 메서드 및 이벤트를 추가 하 고 재정의할 수 있습니다. 시작 하려면 [방법: 간단한 Windows Forms 컨트롤 개발](how-to-develop-a-simple-windows-forms-control.md)을 참조 하세요.  
  
 Windows Forms 컨트롤의 기본 클래스인 <xref:System.Windows.Forms.Control>는 클라이언트 쪽 Windows 기반 응용 프로그램에서 시각적 표시에 필요한 통로를 제공 합니다. <xref:System.Windows.Forms.Control> 창 핸들을 제공 하 고, 메시지 라우팅을 처리 하 고, 마우스 및 키보드 이벤트와 기타 많은 사용자 인터페이스 이벤트를 제공 합니다. 고급 레이아웃을 제공 하 고 시각적 표시와 관련 된 속성 (예: <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>등)을 제공 합니다. 또한 보안, 스레딩 지원 및 ActiveX 컨트롤과의 상호 운용성을 제공 합니다. 인프라의 상당 부분이 기본 클래스에서 제공되므로 비교적 쉽게 사용자 고유의 Windows Forms 컨트롤을 개발할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [방법: 간단한 Windows Forms 컨트롤 개발](how-to-develop-a-simple-windows-forms-control.md)
- [합성 Windows Forms 컨트롤 개발](developing-a-composite-windows-forms-control.md)
- [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)
