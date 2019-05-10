---
title: '연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 9f72d6d560f82d7d80036f07ec865d78a4ab9955
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606409"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬
일부 애플리케이션에는 폼 크기가 조정되거나 내용의 크기가 변경될 때 적절하게 정렬되는 레이아웃을 가진 폼이 필요합니다. 동적 레이아웃이 필요하며 코드에서 명시적으로 <xref:System.Windows.Forms.Control.Layout> 이벤트를 처리하지 않으려는 경우 레이아웃 패널을 사용하는 것이 좋습니다.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 폼에서 컨트롤을 정렬하는 직관적인 방법을 제공합니다. 둘 다 포함된 자식 컨트롤의 상대 위치를 제어하는 구성 가능한 자동 기능을 제공하며, 둘 다 런타임에 동적 레이아웃 기능을 제공하므로 부모 폼의 크기가 변경될 때 자식 컨트롤의 크기를 조정하고 위치를 변경할 수 있습니다. 레이아웃 패널을 레이아웃 패널 내에 중첩하여 정교한 사용자 인터페이스를 구현할 수 있습니다.  
  
 <xref:System.Windows.Forms.FlowLayoutPanel> 은 특정 흐름 방향(수평 또는 수직)으로 내용을 정렬합니다. 컨트롤 내용을 한 행에서 다음 행으로 또는 한 열에서 다음 열로 줄 바꿈할 수 있습니다. 또는 컨트롤 내용이 줄 바꿈되는 대신 잘릴 수 있습니다. 자세한 내용은 [연습: FlowLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)합니다.  
  
 합니다 <xref:System.Windows.Forms.TableLayoutPanel> HTML과 비슷한 기능을 제공 하는 눈금으로 내용을 정렬 \<테이블 > 요소입니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용 하면 각 개별 컨트롤의 위치를 정확 하 게 지정 하지 않고도 모눈 레이아웃에서 컨트롤을 배치할 수 있습니다. 해당 셀은 행과 열로 정렬되며 크기가 서로 다를 수 있습니다. 행 및 열에서 셀을 병합할 수 있습니다. 셀 폼을 포함 하 고 컨테이너와 다른 대부분의 측면에서 동작 하는 모든 항목을 포함할 수 있습니다.  
  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서는 가변 크기 조정 기능을 런타임에 폼 크기를 조정할 때 레이아웃 원활 하 게 변경할 수 있도록 합니다. 이렇게 하면는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 데이터 입력 폼과 지역화 된 응용 프로그램 등의 용도로 적합 합니다. 자세한 내용은 [연습: 데이터 항목에 대 한 크기 조정 가능한 Windows Form 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) 고 [연습: 지역화 가능한 Windows Form 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))합니다.  
  
 사용 되지 해야 일반적으로 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 전체 레이아웃에 대 한 컨테이너입니다. 사용 하 여 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 레이아웃의 부분에 비례하여 크기 조정 기능을 제공 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
- Windows Forms 프로젝트 만들기  
  
- 행 및 열에서 컨트롤 정렬  
  
- 설정 행 및 열 속성  
  
- 행 및 열 컨트롤을 사용 하 여 확장  
  
- 오버플로 자동 처리  
  
- 도구 상자에서 두 번 클릭하여 컨트롤 삽입  
  
- 윤곽선을 그려 컨트롤 삽입  
  
- 다른 부모에 기존 컨트롤 다시 할당  
  
 작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1. "TableLayoutPanelExample" 라는 Windows 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 합니다.  
  
2. 폼을 선택 합니다 **Windows** **Forms 디자이너**합니다.  
  
## <a name="arranging-controls-in-rows-and-columns"></a>행 및 열에서 컨트롤 정렬  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용 하면 쉽게 컨트롤 행과 열으로 정렬할 수 있습니다.  
  
#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>행 및 열을 TableLayoutPanel을 사용 하 여 컨트롤을 정렬 하려면  
  
1. <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다. 기본적으로 있는지 확인 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 4 개의 셀입니다.  
  
2. 끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 에 <xref:System.Windows.Forms.TableLayoutPanel> 제어 셀 중 하나에 놓습니다. <xref:System.Windows.Forms.Button> 선택한 셀 내의 컨트롤이 만들어집니다.  
  
3. 세 개 이상 끌어 <xref:System.Windows.Forms.Button> 에서 제어를 **도구 상자** 에 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 각 셀에 단추가 포함 되도록 합니다.  
  
4. 두 열 사이 있는 세로 크기 조정 핸들을 잡고 왼쪽으로 이동 합니다. 합니다 <xref:System.Windows.Forms.Button> 첫 번째 열에 있는 컨트롤의 크기 중 더 작은 너비를 크기가 조정 되는 <xref:System.Windows.Forms.Button> 컨트롤 두 번째 열에서은 변경 되지 않습니다.  
  
5. 두 열 사이 있는 세로 크기 조정 핸들을 잡고 오른쪽으로 이동 합니다. 합니다 <xref:System.Windows.Forms.Button> 하는 동안 컨트롤 첫 번째 열에 원래 크기로 돌아갑니다는 <xref:System.Windows.Forms.Button> 컨트롤 두 번째 열의 오른쪽으로 이동 됩니다.  
  
6. 가로 크기 조정 핸들 패널에서 컨트롤에 미치는 영향을 위아래로 이동 합니다.  
  
## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>컨트롤 도킹 및 고정 기능을 사용 하 여 셀 내에서 위치 지정  
 자식 컨트롤의 앵커 동작을 <xref:System.Windows.Forms.TableLayoutPanel> 다른 컨테이너 컨트롤의 동작과에서 다릅니다. 자식 컨트롤의 도킹 동작을 다른 컨테이너 컨트롤와 같습니다.  
  
#### <a name="positioning-controls-within-cells"></a>셀에서 컨트롤을 위치 지정  
  
1. 첫 번째 선택 <xref:System.Windows.Forms.Button> 제어 합니다. <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 변경합니다. <xref:System.Windows.Forms.Button> 컨트롤의 셀을 채우도록 확장 합니다.  
  
2. 다른 하나를 선택 <xref:System.Windows.Forms.Button> 컨트롤입니다. <xref:System.Windows.Forms.Control.Anchor%2A> 속성의 값을 <xref:System.Windows.Forms.AnchorStyles.Right>로 변경합니다. 오른쪽 테두리 셀의 오른쪽 테두리 거의 되도록 이동 note 합니다. 테두리 사이의 거리의 합계인 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 패널의 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.  
  
3. 값을 변경 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.Right> 고 <xref:System.Windows.Forms.AnchorStyles.Left>입니다. 컨트롤은 사용 하 여 셀의 너비의 크기는 합니다 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 고려 하는 값입니다.  
  
4. 사용 하 여 2-3 단계를 반복 합니다 <xref:System.Windows.Forms.AnchorStyles.Top> 고 <xref:System.Windows.Forms.AnchorStyles.Bottom> 스타일입니다.  
  
## <a name="setting-row-and-column-properties"></a>설정 행 및 열 속성  
 사용 하 여 행 및 열의 개별 속성을 설정할 수 있습니다 합니다 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 고 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션입니다.  
  
#### <a name="to-set-row-and-column-properties"></a>행 및 열 속성을 설정 하려면  
  
1. 선택 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어 합니다 **Windows Forms 디자이너**합니다.  
  
2. 에 **속성** 창을 열어 합니다 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 줄임표를 클릭 하 여 컬렉션 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 단추 다음에 **열** 항목입니다.  
  
3. 첫 번째 열을 선택 하 고 값을 변경 해당 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성을 <xref:System.Windows.Forms.SizeType.AutoSize>입니다. 클릭 **확인** 하 여 변경 내용을 적용 합니다. 첫 번째 열의 너비에 맞게 축소 되는 참고를 <xref:System.Windows.Forms.Button> 제어 합니다. 열의 너비를 조정할 수 있는지 참고도 합니다.  
  
4. 에 **속성** 창을 열려면는 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션과 첫 번째 열을 선택 합니다. <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성의 값을 <xref:System.Windows.Forms.SizeType.Percent>로 변경합니다. 클릭 **확인** 하 여 변경 내용을 적용 합니다. 크기를 조정 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 큰 너비를 제어 하 고 첫 번째 열의 너비를 확장 한다는 점에 유의 합니다. 크기를 조정 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 너비를 제어 하 고 첫 번째 열에서 단추 셀에 맞게 크기가 조정 되는 참고 합니다. 열의 너비를 조정할 수 있는지 참고도 합니다.  
  
5. 에 **속성** 창을 열려면는 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 컬렉션과 나열된 된 모든 열을 선택 합니다. 값을 설정할 때마다 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성을 <xref:System.Windows.Forms.SizeType.Percent>입니다. 클릭 **확인** 하 여 변경 내용을 적용 합니다. 사용 하 여 반복을 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 컬렉션입니다.  
  
6. 크기 조정 핸들의 모서리 중 하나를 잡고 너비와 높이 조정 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. 행과 열으로 크기가 조정 되는 참고를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 크기를 변경 합니다. 행과 열은 가로 크기를 조정할 수 및 크기 조정 핸들이 세로 note도 합니다.  
  
## <a name="spanning-rows-and-columns-with-a-control"></a>행 및 열 컨트롤을 사용 하 여 확장  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 디자인 타임에 컨트롤에 몇 가지 새 속성을 추가 합니다. 이러한 속성 중 두 가지 `RowSpan` 고 `ColumnSpan`입니다. 컨트롤 범위 둘 이상의 행 또는 열을 확인 하려면 이러한 속성을 사용할 수 있습니다.  
  
#### <a name="to-span-rows-and-columns-with-a-control"></a>행과 컨트롤을 사용 하 여 열에 걸쳐  
  
1. 선택 된 <xref:System.Windows.Forms.Button> 첫 번째 행과 첫째 열에는 컨트롤입니다.  
  
2. 에 **속성** 의 값을 변경 하는 windows 합니다 `ColumnSpan` 속성을 **2**합니다. <xref:System.Windows.Forms.Button> 컨트롤에서 첫 번째 열과 두 번째 열을 채웁니다. 이러한 변경에 추가한 행을 추가 하는 보다 note도 합니다.  
  
3. 에 대 한 2 단계를 반복 합니다 `RowSpan` 속성입니다.  
  
## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>도구 상자에서 두 번 클릭하여 컨트롤 삽입  
 <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서 컨트롤을 두 번 클릭하여**컨트롤을 채울 수 있습니다.  
  
#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>도구 상자에서 두 번 클릭하여 컨트롤을 삽입하려면  
  
1. <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
2. <xref:System.Windows.Forms.Button> 도구 상자 **에서**컨트롤 아이콘을 두 번 클릭합니다. 새 단추 컨트롤에 표시 되는 참고를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀입니다.  
  
3. **도구 상자**에서 컨트롤을 몇 개 더 두 번 클릭합니다. 새 컨트롤에 연속 해 서 표시 된 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 빈된 셀입니다. 또한는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 열기 셀 사용 가능한 경우 새 컨트롤에 맞게 확장 됩니다.  
  
## <a name="automatic-handling-of-overflows"></a>오버플로 자동 처리  
 에 컨트롤을 삽입 하는 경우는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 부족 해질 수 있습니다 빈 셀에 새 컨트롤에 대 한 합니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 자동으로 셀의 수를 늘려 합니다.  
  
#### <a name="to-observe-automatic-handling-of-overflows"></a>오버플로 자동 처리를 관찰 하기  
  
1. 에 빈 셀이 없으면 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 새 삽입을 계속 <xref:System.Windows.Forms.Button> 까지 제어는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 가득 합니다.  
  
2. 한 번를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 전체를 두 번 클릭 합니다 <xref:System.Windows.Forms.Button> 아이콘에는 **도구 상자** 다른 삽입할 <xref:System.Windows.Forms.Button> 컨트롤. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 새 컨트롤을 수용 하기 위해 새 셀을 만듭니다. 몇 가지 더 많은 컨트롤을 삽입 하 고 크기 조정 동작을 관찰 합니다.  
  
3. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 속성 값을 <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>로 변경합니다. 두 번 클릭 합니다 <xref:System.Windows.Forms.Button> 아이콘에는 **도구 상자** 삽입할 <xref:System.Windows.Forms.Button> 까지 제어는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 가득. 두 번 클릭 합니다 <xref:System.Windows.Forms.Button> 아이콘에는 **도구 상자** 다시 합니다. 오류 메시지가 나타납니다 합니다 **Windows Forms 디자이너** 알리는 추가 행과 열을 만들 수 없습니다.  
  
## <a name="inserting-a-control-by-drawing-its-outline"></a>윤곽선을 그려 컨트롤 삽입  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 컨트롤을 삽입하고 셀에서 해당 윤곽선을 그려 크기를 지정합니다.  
  
#### <a name="to-insert-a-control-by-drawing-its-outline"></a>윤곽선을 그려 컨트롤을 삽입하려면  
  
1. <xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
2. **도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 클릭합니다. 폼으로 끌어다 놓지 마세요.  
  
3. 마우스 포인터를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 위로 이동합니다. 포인터가 <xref:System.Windows.Forms.Button> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다.  
  
4. 마우스 단추를 길게 클릭합니다.  
  
5. 마우스 포인터를 끌어 <xref:System.Windows.Forms.Button> 컨트롤의 윤곽선을 그립니다. 원하는 크기가 되면 마우스 단추를 놓습니다. <xref:System.Windows.Forms.Button> 컨트롤이 컨트롤의 윤곽선을 그린 셀에 만들어집니다.  
  
## <a name="multiple-controls-within-cells-are-not-permitted"></a>셀 내에서 여러 컨트롤 금지 됩니다.  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 셀 당 하나의 자식 컨트롤을 포함할 수 있습니다.  
  
#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>셀 내에서 여러 컨트롤은 허용 되지 않음을 보여 줍니다.  
  
- 끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 에 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 사용 된 셀 중 하나에 놓습니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 삭제할 수 없습니다는 <xref:System.Windows.Forms.Button> 셀으로 끌 제어 합니다.  
  
## <a name="swapping-controls"></a>교환 컨트롤  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용 하면 두 개의 다른 셀 컨트롤을 교환할 수 있습니다.  
  
#### <a name="to-swap-controls"></a>컨트롤을 바꾸려면  
  
- 중 하나를 끌어는 <xref:System.Windows.Forms.Button> 점유 셀 및 놓습니다 점유 창의 다른 셀에서 컨트롤입니다. 참고로 다른 두 개의 하나의 셀에서 이동 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 레이아웃 패널 및 컨트롤의 조합을 사용하여 복잡한 레이아웃을 얻을 수 있습니다. 다음과 같은 사항을 더 살펴보는 것이 좋습니다.  
  
- 크기 조정 중 하나를 시도 <xref:System.Windows.Forms.Button> 컨트롤 크기 및 레이아웃에 미치는 영향을 확인 합니다.  
  
- 다양 한 여러 컨트롤에 붙여 넣습니다는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 컨트롤을 삽입 하는 방법을 확인 합니다.  
  
- 레이아웃 패널에 다른 레이아웃 패널을 포함할 수 있습니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 기존 컨트롤에 끌어다 놓습니다.  
  
- <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 부모 폼에 도킹합니다. 폼의 크기를 조정하고 레이아웃에 미치는 영향을 확인합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [연습: FlowLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Microsoft Windows 사용자 환경, 사용자 인터페이스 개발자 및 디자이너를 위한 공식 지침. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
- [연습: 데이터 항목에 대 한 크기 조정 가능한 Windows Form 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [연습: 지역화 가능한 Windows Form 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [TableLayoutPanel 컨트롤에 대한 모범 사례](best-practices-for-the-tablelayoutpanel-control.md)
- [AutoSize 속성 개요](autosize-property-overview.md)
- [방법: Windows Forms에 컨트롤 도킹](how-to-dock-controls-on-windows-forms.md)
- [방법: Windows Forms에서 컨트롤 고정](how-to-anchor-controls-on-windows-forms.md)
- [연습: Windows Forms 컨트롤 Padding, Margins 및 AutoSize 속성을 사용 하 여 레이아웃](windows-forms-controls-padding-autosize.md)
