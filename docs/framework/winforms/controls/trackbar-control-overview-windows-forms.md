---
title: TrackBar 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741459"
---
# <a name="trackbar-control-overview-windows-forms"></a>TrackBar 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.TrackBar> 컨트롤 ("slider" 컨트롤이 라고도 함)은 많은 양의 정보를 탐색 하거나 숫자 설정을 시각적으로 조정 하는 데 사용 됩니다. <xref:System.Windows.Forms.TrackBar> 컨트롤에는 엄지 단추 라고도 하는 두 부분, 즉 슬라이더와 눈금이 있습니다. 엄지 단추는 조정할 수 있는 부분입니다. 해당 위치는 <xref:System.Windows.Forms.TrackBar.Value%2A> 속성에 해당 합니다. 눈금 표시는 일정 한 간격으로 간격을 표시 하는 시각적 표시기입니다. Trackbar은 사용자가 지정 하는 증가분 만큼 이동 하며 가로 또는 세로로 맞출 수 있습니다. 예를 들어 트랙 표시줄을 사용 하 여 시스템에 대 한 커서 깜박임 속도 또는 마우스 속도를 제어할 수 있습니다.  
  
## <a name="key-properties"></a>키 속성  
 <xref:System.Windows.Forms.TrackBar> 컨트롤의 키 속성은 <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>및 <xref:System.Windows.Forms.TrackBar.Maximum%2A>입니다. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> 눈금의 간격입니다. <xref:System.Windows.Forms.TrackBar.Minimum%2A> 및 <xref:System.Windows.Forms.TrackBar.Maximum%2A>는 트랙 표시줄에 표시할 수 있는 가장 작은 값과 가장 큰 값입니다.  
  
 다른 두 가지 중요 한 속성은 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 및 <xref:System.Windows.Forms.TrackBar.LargeChange%2A>입니다. <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 속성의 값은 왼쪽 또는 오른쪽 화살표 키를 누른 상태에서 엄지 단추가 이동 하는 위치 수입니다. <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 속성의 값은 PAGE UP 또는 PAGE DOWN 키를 눌렀을 때 또는 thumb의 한쪽에 있는 트랙 표시줄의 마우스 클릭에 대 한 응답으로 스크롤 막대를 이동 하는 위치 수입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.TrackBar>
- [TrackBar 컨트롤](trackbar-control-windows-forms.md)
