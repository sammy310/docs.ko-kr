---
title: 좌표
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734670"
---
# <a name="windows-forms-coordinates"></a>Windows Forms 좌표
Windows Form의 좌표계는 장치 좌표를 기반으로 하며 Windows Forms 그릴 때의 기본 측정 단위는 장치 단위 (일반적으로 픽셀)입니다. 화면의 점은 x 좌표와 y 좌표 쌍으로 표현 되며 x 좌표는 오른쪽으로, y 좌표는 위쪽에서 아래쪽으로 늘어납니다. 화면을 기준으로 하는 원본의 위치는 화면 또는 클라이언트 좌표를 지정 하는지 여부에 따라 달라 집니다.  
  
## <a name="screen-coordinates"></a>화면 좌표  
 Windows Forms 응용 프로그램 화면 좌표에서 화면에 있는 창의 위치를 지정 합니다. 화면 좌표의 경우 원점은 화면의 왼쪽 위 모퉁이입니다. 창의 전체 위치는 창의 왼쪽 위 모퉁이와 오른쪽 아래 모퉁이를 정의 하는 두 점의 화면 좌표를 포함 하는 <xref:System.Drawing.Rectangle> 구조로 설명 되는 경우가 많습니다.  
  
## <a name="client-coordinates"></a>클라이언트 좌표  
 Windows Forms 응용 프로그램은 폼 이나 컨트롤에서 클라이언트 좌표를 사용 하 여 지점의 위치를 지정 합니다. 클라이언트 좌표에 대 한 원본은 컨트롤이 나 폼의 클라이언트 영역에 대 한 왼쪽 위 모퉁이입니다. 클라이언트 좌표는 화면에 폼 이나 컨트롤의 위치에 관계 없이 응용 프로그램에서 폼 이나 컨트롤을 그릴 때 일관 된 좌표 값을 사용할 수 있도록 합니다.  
  
 클라이언트 영역의 차원은 영역에 대 한 클라이언트 좌표를 포함 하는 <xref:System.Drawing.Rectangle> 구조에도 설명 되어 있습니다. 모든 경우에서 사각형의 왼쪽 위 좌표는 클라이언트 영역에 포함 되 고, 오른쪽 아래 좌표는 제외 됩니다. 그래픽 작업에는 클라이언트 영역의 오른쪽 및 아래쪽 가장자리가 포함 되지 않습니다. 예를 들어 <xref:System.Drawing.Graphics.FillRectangle%2A> 메서드는 지정 된 사각형의 오른쪽 및 아래쪽 가장자리에만 채워지고 이러한 가장자리를 포함 하지는 않습니다.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>한 좌표 유형에 서 다른 유형으로 매핑  
 경우에 따라 화면 좌표에서 클라이언트 좌표로 매핑해야 할 수도 있습니다. <xref:System.Windows.Forms.Control> 클래스에서 사용할 수 있는 <xref:System.Windows.Forms.Control.PointToClient%2A> 및 <xref:System.Windows.Forms.Control.PointToScreen%2A> 메서드를 사용 하 여이를 쉽게 수행할 수 있습니다. 예를 들어 <xref:System.Windows.Forms.Control>의 <xref:System.Windows.Forms.Control.MousePosition%2A> 속성은 화면 좌표로 보고 되지만 이러한 속성을 클라이언트 좌표로 변환 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
