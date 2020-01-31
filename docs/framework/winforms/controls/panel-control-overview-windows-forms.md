---
title: Panel 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744309"
---
# <a name="panel-control-overview-windows-forms"></a>Panel 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤에 대해 식별 가능한 그룹화를 제공 하는 데 사용 됩니다. 일반적으로 패널을 사용 하 여 폼을 기능별로 나눕니다. 예를 들어 사용할 야간 운송 업체와 같은 메일 옵션을 지정 하는 주문 양식이 있을 수 있습니다. 패널의 모든 옵션 그룹화는 사용자에 게 논리적 시각적 표시를 제공 합니다. 디자인 타임에 모든 컨트롤을 쉽게 이동할 수 있습니다. <xref:System.Windows.Forms.Panel> 컨트롤을 이동 하면 포함 된 컨트롤도 모두 이동 합니다. 패널에 그룹화 된 컨트롤은 <xref:System.Windows.Forms.Control.Controls%2A> 속성을 통해 액세스할 수 있습니다. 이 속성은 <xref:System.Windows.Forms.Control> 인스턴스의 컬렉션을 반환 하므로 일반적으로 이러한 방식으로 검색 된 컨트롤을 특정 형식으로 캐스팅 해야 합니다.  
  
## <a name="panel-versus-groupbox"></a>패널 및 GroupBox  
 <xref:System.Windows.Forms.Panel> 컨트롤은 <xref:System.Windows.Forms.GroupBox> 컨트롤과 비슷합니다. 그러나 <xref:System.Windows.Forms.Panel> 컨트롤에만 스크롤 막대가 있을 수 있으며 <xref:System.Windows.Forms.GroupBox> 컨트롤에만 캡션이 표시 됩니다.  
  
## <a name="key-properties"></a>키 속성  
 스크롤 막대를 표시 하려면 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 속성을 `true`로 설정 합니다. <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>및 <xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성을 설정 하 여 패널의 모양을 사용자 지정할 수도 있습니다. <xref:System.Windows.Forms.Control.BackColor%2A> 및 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성에 대 한 자세한 내용은 [방법: 패널의 배경 설정](how-to-set-the-background-of-a-windows-forms-panel.md)을 참조 하세요. <xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성은 패널이 표시 되지 않는 테두리 (<xref:System.Windows.Forms.BorderStyle.None>), 일반 선 (<xref:System.Windows.Forms.BorderStyle.FixedSingle>) 또는 숨겨진 줄 (<xref:System.Windows.Forms.BorderStyle.Fixed3D>)을 사용 하 여 윤곽선으로 표시 되는지를 결정 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Panel>
- [GroupBox 컨트롤](groupbox-control-windows-forms.md)
- [방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화](group-controls-with-wf-panel-control-using-the-designer.md)
- [방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
