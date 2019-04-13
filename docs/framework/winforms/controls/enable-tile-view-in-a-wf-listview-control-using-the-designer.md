---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 타일 보기 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: f8c8a1b2e3d2adfa7daadd609051ffc304150efe
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300595"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 타일 보기 사용
바둑판식 뷰 기능을 <xref:System.Windows.Forms.ListView> 컨트롤을 사용 하면 그래픽 및 텍스트 정보 간의 시각적 균형을 제공할 수 있습니다. 바둑판식 뷰에서 항목에 대해 표시되는 텍스트 정보는 세부 정보 뷰에 대해 정의된 열 정보와 같습니다. 타일 보기 함수에 함께 그룹화 또는 삽입 표시 기능에는 <xref:System.Windows.Forms.ListView> 제어 합니다.  
  
 바둑판식 뷰는 다음 이미지에 나와 있는 것 처럼 32x32 아이콘과 여러 줄 텍스트의를 사용 합니다.  
  
 ![ListView 컨트롤의 tile 보기](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "뷰 아이콘 및 텍스트 타일")  
  
 타일 보기 속성 및 메서드를 사용 하면 각 항목에 대해 표시 하 고 전체적으로 타일 보기 창 내에서 모든 항목의 모양과 크기를 제어 하는 열 필드를 지정할 수 있습니다. 이해를 돕기 위해 타일에서 텍스트의 첫 번째 줄은 항상 항목의 이름입니다. 변경할 수 없습니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ListView> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  바둑판식 뷰는 응용 프로그램이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다. 이전 운영 체제에서는 바둑판식 뷰와 관련된 코드가 아무 효과도 없으며, <xref:System.Windows.Forms.ListView> 컨트롤이 큰 아이콘 보기에 표시됩니다. 자세한 내용은 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>을 참조하세요.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-set-tile-view-in-the-designer"></a>바둑판식 뷰 디자이너에서 설정 하려면  
  
1. 선택 된 <xref:System.Windows.Forms.ListView> 양식에 컨트롤입니다.  
  
2. 에 **속성** 창에서 합니다 <xref:System.Windows.Forms.ListView.View%2A> 속성 선택 **타일**합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
