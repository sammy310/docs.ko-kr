---
title: 디자이너를 사용 하 여 패널의 배경 설정
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731925"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>방법: 디자이너를 사용 하 여 Windows Forms 패널의 배경 설정

Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 배경색과 배경 이미지를 모두 표시할 수 있습니다. <xref:System.Windows.Forms.Control.BackColor%2A> 속성은 레이블 및 라디오 단추와 같이 패널에 포함 된 컨트롤의 배경색을 설정 합니다. <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되지 않은 경우 <xref:System.Windows.Forms.Control.BackColor%2A> 선택이 모든 패널을 채웁니다. <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있으면 패널에 포함 된 컨트롤 뒤에 이미지가 표시 됩니다.

다음 절차에는 <xref:System.Windows.Forms.Panel> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다. Visual Studio에서 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.

## <a name="set-the-background-in-the-windows-forms-designer"></a>Windows Forms 디자이너의 배경 설정

1. Visual Studio에서 프로젝트를 열고 <xref:System.Windows.Forms.Panel> 컨트롤을 선택 합니다.

2. **속성** 창에서 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 옆의 화살표 단추를 클릭 하 여 세 개의 탭이 포함 된 창을 표시 합니다.

3. **사용자 지정** 탭을 선택 하 여 색의 색상표를 표시 합니다.

4. **웹** 또는 **시스템** 탭을 선택 하 여 색의 미리 정의 된 이름 목록을 표시 하 고 색을 선택 합니다.

5. **속성** 창에서 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성 옆의 화살표 단추를 클릭 합니다.

6. **열기** 대화 상자에서 표시 하려는 파일을 선택 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel 컨트롤](panel-control-windows-forms.md)
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
- [방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화](group-controls-with-wf-panel-control-using-the-designer.md)
