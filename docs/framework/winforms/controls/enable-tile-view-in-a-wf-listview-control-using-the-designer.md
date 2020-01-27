---
title: 디자이너를 사용 하 여 ListView 컨트롤에서 Tile 보기 사용
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745809"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 Tile 보기 사용
<xref:System.Windows.Forms.ListView> 컨트롤의 바둑판식 뷰 기능을 통해 그래픽 정보와 텍스트 정보 간의 시각적 균형을 제공할 수 있습니다. 바둑판식 뷰에서 항목에 대해 표시되는 텍스트 정보는 세부 정보 뷰에 대해 정의된 열 정보와 같습니다. <xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 또는 삽입 표시 기능과 함께 바둑판식 뷰 함수를 사용 합니다.

 다음 그림에 표시 된 것 처럼 타일 보기는 32 x 32 아이콘과 여러 줄의 텍스트를 사용 합니다.

 ![ListView 컨트롤의 타일 보기](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "바둑판식 뷰 아이콘 및 텍스트")

 바둑판식 뷰 속성 및 메서드를 사용 하면 각 항목에 대해 표시할 열 필드를 지정 하 고 타일 보기 창에서 모든 항목의 크기와 모양을 전체적으로 제어할 수 있습니다. 쉽게 이해할 수 있도록 타일에서 텍스트의 첫 번째 줄은 항상 항목의 이름입니다. 변경할 수 없습니다.

 다음 절차에는 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다. 이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.

## <a name="to-set-tile-view-in-the-designer"></a>디자이너에서 바둑판식 뷰를 설정 하려면

1. Visual Studio에서 폼의 <xref:System.Windows.Forms.ListView> 컨트롤을 선택 합니다.

2. **속성** 창에서 <xref:System.Windows.Forms.ListView.View%2A> 속성을 선택 하 고 **타일**을 선택 합니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
