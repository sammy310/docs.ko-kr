---
title: SplitContainer 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 5cb5240ed4ebe3e27c20844681068711c222e9a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742914"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>SplitContainer 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.SplitContainer> 컨트롤은 복합으로 간주될 수 있습니다. 이동 가능한 막대로 구분된 두 개의 패널입니다. 마우스 포인터가 막대 위에 있으면 포인터 모양이 변경되어 막대를 이동할 수 있음을 표시합니다.  
  
> [!IMPORTANT]
> **도구 상자**에서 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 이전 버전의 Visual Studio에 있던 <xref:System.Windows.Forms.Splitter> 컨트롤을 대체 합니다. <xref:System.Windows.Forms.SplitContainer> 컨트롤이 <xref:System.Windows.Forms.Splitter> 컨트롤보다 훨씬 선호됩니다. 기존 애플리케이션과의 호환성을 위해 <xref:System.Windows.Forms.Splitter> 클래스도 .NET Framework에 여전히 포함되어 있지만 새 프로젝트에는 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용하는 것이 좋습니다.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용 하면 복잡 한 사용자 인터페이스를 만들 수 있습니다. 대개 한 패널에서 선택 하면 다른 패널에 표시 되는 개체가 결정 됩니다. 이 정렬은 정보를 표시하고 찾는 데 매우 효율적입니다. 두 개의 패널을 사용 하면 영역의 정보를 집계할 수 있으며, 막대 또는 "분할자"를 사용 하면 사용자가 패널 크기를 쉽게 조정할 수 있습니다.  
  
 두 개 이상의 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 중첩 하 여 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 가로 방향으로 만들어 위쪽 및 아래쪽 패널을 만들 수도 있습니다.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 기본적으로 키보드에 액세스할 수 있어야 합니다. <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성이 `false`로 설정 된 경우 사용자는 화살표 키를 눌러 분할자를 이동할 수 있습니다.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성은 컨트롤 자체가 아닌 분할자의 방향을 결정 합니다. 따라서이 속성을 <xref:System.Windows.Forms.Orientation.Vertical>로 설정 하면 분할자는 위쪽에서 아래쪽으로 실행 되어 왼쪽 및 오른쪽 패널을 만듭니다.  
  
 또한 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성의 값은 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성의 값에 따라 달라 집니다. 자세한 내용은 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성을 참조 하세요.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기와 움직임을 제한할 수도 있습니다. <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성은 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기를 조정 하 고 나 서 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성이 분할자를 키보드 또는 마우스로 이동할 수 있는지 여부를 결정 하는 데 사용할 패널을 결정 합니다.  
  
> [!NOTE]
> <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성이 `true`로 설정 된 경우에도 분할자는 프로그래밍 방식으로 계속 이동 될 수 있습니다. 예를 들어 <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성을 사용 합니다.  
  
 마지막으로, <xref:System.Windows.Forms.SplitContainer> 컨트롤의 각 패널에는 개별 크기를 결정 하는 속성이 있습니다.  
  
## <a name="commonly-used-properties-methods-and-events"></a>일반적으로 사용되는 속성, 메서드 및 이벤트  
  
|이름|설명|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성|<xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기가 조정 된 후에 동일한 크기를 유지할 패널을 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성|분할자를 키보드 또는 마우스로 이동할 수 있는지 여부를 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성|분할자를 가로 또는 세로로 정렬할지 여부를 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성|왼쪽 또는 위쪽 가장자리에서 이동할 수 있는 분할자 막대 까지의 거리 (픽셀 단위)를 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성|사용자가 분할자를 이동할 수 있는 최소 거리 (픽셀)를 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> 속성|분할자의 두께 (픽셀 단위)를 결정 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> 이벤트|분할자를 이동할 때 발생 합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> 이벤트|분할자를 이동할 때 발생 합니다.|  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 컨트롤](splitcontainer-control-windows-forms.md)
- [SplitContainer 컨트롤 샘플](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
