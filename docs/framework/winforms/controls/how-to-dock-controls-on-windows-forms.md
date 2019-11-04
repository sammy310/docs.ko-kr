---
title: '방법: Windows Forms에 컨트롤 도킹'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 82aef0ae9abacad33b21920f88591c0e4c33dfcb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460553"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>방법: Windows Forms에 컨트롤 도킹

컨트롤을 폼의 가장자리에 도킹 하거나 컨트롤의 컨테이너 (폼 또는 컨테이너 컨트롤)에 채울 수 있습니다. 예를 들어 Windows 탐색기는 창의 왼쪽에 <xref:System.Windows.Forms.TreeView> 컨트롤을 도킹 하 고 창의 오른쪽에 <xref:System.Windows.Forms.ListView> 컨트롤을 도킹 합니다. 표시 되는 모든 Windows Forms 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 사용 하 여 도킹 모드를 정의 합니다.

> [!NOTE]
> 컨트롤은 역방향 z 순서로 도킹 됩니다.

<xref:System.Windows.Forms.Control.Dock%2A> 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성과 상호 작용 합니다. 자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)를 참조 하세요.

## <a name="to-dock-a-control"></a>컨트롤을 도킹 하려면

1. Visual Studio에서 도킹 하려는 컨트롤을 선택 합니다.

2. **속성** 창에서 <xref:System.Windows.Forms.Control.Dock%2A> 속성의 오른쪽에 있는 화살표를 클릭 합니다.

   폼의 가장자리와 중심을 나타내는 일련의 상자가 표시 된 편집기가 표시 됩니다.

3. 컨트롤을 도킹할 폼의 가장자리를 나타내는 단추를 클릭 합니다. 컨트롤의 폼 이나 컨테이너 컨트롤의 내용을 채우려면 가운데 상자를 클릭 합니다. **(없음)** 을 클릭 하 여 도킹을 해제 합니다.

   도킹 된 가장자리의 경계에 맞게 컨트롤의 크기가 자동으로 조정 됩니다.

   > [!NOTE]
   > 상속 된 컨트롤은 도킹할 수 있도록 `Protected` 해야 합니다. 컨트롤의 액세스 수준을 변경 하려면 **속성** 창에서 해당 **Modifier** 속성을 설정 합니다.

## <a name="see-also"></a>참조

- [Windows Forms 컨트롤](index.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
- [방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [AutoSize 속성 개요](autosize-property-overview.md)
- [방법: Windows Forms에서 컨트롤 고정](how-to-anchor-controls-on-windows-forms.md)
