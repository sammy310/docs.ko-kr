---
title: ProgressBar 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: 24b47669cdf8ed0a8f0f936b0b3b9c354e62445f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227498"
---
# <a name="progressbar-control-overview-windows-forms"></a>ProgressBar 컨트롤 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.ProgressBar> 컨트롤의 가로 막대에 정렬 된 사각형으로 적절 한 수를 표시 하 여 프로세스의 진행률을 나타냅니다. 프로세스가 완료 되 면 막대가 채워집니다. 진행률 표시줄 사용자 방법 이해할 수 있도록 일반적으로 사용 되는 프로세스가 완료 되기를 기다렸다가 수 예를 들어 경우 큰 파일 되 고 로드 됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ProgressBar> 양식의 컨트롤 가로 방향을 수 있습니다.  
  
## <a name="key-properties-and-methods"></a>키 속성 및 메서드  
 키 속성을 <xref:System.Windows.Forms.ProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A>합니다. 합니다 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성 진행률 표시줄에 표시할 수 있습니다 최대 및 최소 값을 설정 합니다. <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성은 작업 이루어졌습니다 진행률을 나타냅니다. 컨트롤에 표시 되는 표시줄 블록으로 구성 된 값으로 표시 합니다 <xref:System.Windows.Forms.ProgressBar> 제어 대략적는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 현재 값입니다. 크기를 기준으로 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 다음 블록에 표시할 시기를 결정 합니다.  
  
 현재 진행률 값을 업데이트 하는 가장 일반적인 방법은 설정 하는 코드를 작성 하는 것은 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다. 큰 파일을 로드 하는 예제에서는 최대 (킬로바이트)에서 파일의 크기를 설정할 수 있습니다. 예를 들어 경우는 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 100으로 설정 합니다 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 10 속성 및 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성이 설정 되어 50, 5 사각형이 표시 됩니다. 이것이 표시 될 수 있는 수의 절반입니다.  
  
 그러나 표시 되는 값을 수정할 수 있는 방법이 가지는 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 설정 하는 것 외를 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 직접. 합니다 <xref:System.Windows.Forms.ProgressBar.Step%2A> 속성을 증가 시킬 값을 지정 하려면 사용할 수 있습니다는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다. 그런 다음 호출을 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 메서드 값을 증가 됩니다. 증가값 다를 사용할 수 있습니다는 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 메서드는 증가 하는 데 사용할 값을 지정 합니다 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다.  
  
 그래픽 방식으로 현재 작업에 대 한 사용자에 게 알려 주는 또 다른 컨트롤로 <xref:System.Windows.Forms.StatusBar> 제어 합니다.  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 대체 컨트롤과 기능을 추가 합니다 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나를 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤 하는 경우 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다 있습니다 이 옵션을 선택 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar 컨트롤](progressbar-control-windows-forms.md)
