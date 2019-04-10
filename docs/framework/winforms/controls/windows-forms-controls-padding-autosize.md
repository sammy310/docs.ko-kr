---
title: '연습: Padding, Margin 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃'
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
ms.openlocfilehash: 230c7cb80ce6b8a29f7334ed0f8d297fd829faf9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302467"
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a>연습: Padding, Margin 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃
폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다. 합니다 **Windows Forms 디자이너** 이렇게 하려면 여러 레이아웃 도구를 제공 합니다. 가장 중요 한 세 가지는 <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 모든 Windows Forms 컨트롤에 있는 합니다.  
  
 <xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.  
  
 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.  
  
 다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.  
  
 ![안쪽 여백 및 여백을 Windows Forms 컨트롤](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성은 자동으로 크기를 자동으로 해당 내용에 컨트롤을 나타냅니다. 원래 값 보다 더 작게 할 자체 조정 되지는 <xref:System.Windows.Forms.Control.Size%2A> 속성과 값을 고려 합니다 해당 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   컨트롤에 대 한 여백 설정  
  
-   컨트롤에 대 한 안쪽 여백 설정  
  
-   자동으로 컨트롤 크기 조정  
  
 작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   만들고 Visual Studio를 설치한 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행 하는 일을 할 수 있는 충분 한 권한입니다.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1. 만들기는 **Windows 응용 프로그램** 라는 프로젝트 `LayoutExample`합니다. 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 합니다.  
  
2. 폼을 선택 합니다 **Windows Forms 디자이너**합니다.  
  
## <a name="setting-margins-for-your-controls"></a>컨트롤에 대 한 여백 설정  
 사용 하 여 컨트롤 사이의 기본 거리를 설정할 수 있습니다는 <xref:System.Windows.Forms.Control.Margin%2A> 속성입니다. 컨트롤을 이동 하면 다른 컨트롤을 닫을 경우 두 컨트롤의 여백 맞춤선이 표시 됩니다. 이동 하는 컨트롤의 여백으로 정의 된 거리도 맞춰집니다.  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a>Margin 속성을 사용 하 여 폼의 컨트롤을 정렬 하려면  
  
1. 두 끌어 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 폼입니다.  
  
2. 중 하나를 선택 합니다 <xref:System.Windows.Forms.Button> 컨트롤과 거의 닿게 됩니다 될 때까지 다른 가깝게 이동 합니다.  
  
     서로 표시 되는 맞춤선을 확인 합니다. 이 거리는 두 컨트롤의 합계인 <xref:System.Windows.Forms.Control.Margin%2A> 값입니다. 이동 하는이 간격에 맞춰집니다. 세부 정보를 참조 하세요. [연습: Snaplines를 사용 하 여 Forms Windows에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.  
  
3. 변경을 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 확장 하 여 컨트롤 중 하나는 <xref:System.Windows.Forms.Control.Margin%2A> 항목에는 **속성** 창과 설정을 <xref:System.Windows.Forms.Padding.All%2A> 20 속성.  
  
4. 중 하나를 선택 합니다 <xref:System.Windows.Forms.Button> 컨트롤과 다른 가깝게 이동 합니다.  
  
     맞춤선 여백 값의 합을 정의 하는 것이 긴와 맞춰집니다 더 먼 거리에 다른에서 제어 합니다.  
  
5. 변경을 <xref:System.Windows.Forms.Control.Margin%2A> 확장 하 여 선택한 컨트롤의 속성을 <xref:System.Windows.Forms.Control.Margin%2A> 에서 항목은 **속성** 창과 설정을 <xref:System.Windows.Forms.Padding.Top%2A> 속성을 5로.  
  
6. 다른 컨트롤 아래 선택한 컨트롤을 이동 하 고 맞춤선 짧은 관찰 합니다. 선택한 컨트롤을 다른 컨트롤의 왼쪽으로 이동 하 고 맞춤선에서 4 단계에서 관찰 된 값을 유지 하는 관찰 합니다.  
  
7. 각각의 측면을 설정할 수 있습니다는 <xref:System.Windows.Forms.Control.Margin%2A> 속성인 <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, 서로 다른 값에 모두 동일한 값을 설정할 수는 <xref:System.Windows.Forms.Padding.All%2A> 속성.  
  
## <a name="setting-padding-for-your-controls"></a>컨트롤에 대 한 안쪽 여백 설정  
 응용 프로그램에 필요한 정확한 레이아웃을 달성 하려면 컨트롤에 자식 컨트롤이 포함 종종 됩니다. 사용 하 여 부모 컨트롤의 자식 컨트롤의 테두리의 근접도 부모 컨트롤의 테두리를 지정 하려는 경우 <xref:System.Windows.Forms.Control.Padding%2A> 속성과 함께 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성입니다. <xref:System.Windows.Forms.Control.Padding%2A> 속성은 또한 근접 한 컨트롤의 콘텐츠 컨트롤을 사용 (예를 들어를 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성) 해당 테두리입니다.  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a>패딩을 사용 하 여 폼의 컨트롤을 정렬 하려면  
  
1. <xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
2. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.  
  
3. 변경을 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 확장 하 여는 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정을 <xref:System.Windows.Forms.Padding.All%2A> 속성을 5로 합니다.  
  
     새 안쪽 여백에 대 한 공간을 제공 하는 컨트롤이 확장 됩니다.  
  
4. <xref:System.Windows.Forms.GroupBox> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다. 끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 에 <xref:System.Windows.Forms.GroupBox> 컨트롤입니다. 위치는 <xref:System.Windows.Forms.Button> 의 오른쪽 아래 모퉁이에 맞도록 제어는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.  
  
     으로 표시 되는 맞춤선을 관찰 합니다 <xref:System.Windows.Forms.Button> 제어 방법 아래쪽 및 오른쪽 테두리의는 <xref:System.Windows.Forms.GroupBox> 컨트롤입니다. 이러한 맞춤선에 해당 하는 <xref:System.Windows.Forms.Control.Margin%2A> 의 속성을 <xref:System.Windows.Forms.Button>.  
  
5. 변경을 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 확장 하 여는 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 20 속성.  
  
6. 선택 합니다 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤과의 중심을 향해 이동는 <xref:System.Windows.Forms.GroupBox>.  
  
     맞춤선의 테두리에서 더 먼 거리에 표시 된 <xref:System.Windows.Forms.GroupBox> 컨트롤입니다. 이 거리의 합계인 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성 및 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.  
  
## <a name="automatically-sizing-your-controls"></a>자동으로 컨트롤 크기 조정  
 일부 응용 프로그램에서 컨트롤의 크기가 됩니다 동일한 런타임에 디자인 타임으로. 텍스트를 <xref:System.Windows.Forms.Button> 데이터베이스에서 수행할 수 있습니다 예를 들어, 컨트롤 및 해당 길이 미리 알 수 없게 됩니다.  
  
 경우는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 `true`, 컨트롤 콘텐츠에 맞게 크기를 합니다. 자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)합니다.  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a>AutoSize 속성을 사용 하 여 폼의 컨트롤을 정렬 하려면  
  
1. <xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
2. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.  
  
3. 변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추가 텍스트 속성에 대 한 긴 문자열**."  
  
     변경 내용을 커밋하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤의 새 텍스트를 사용자에 맞게 크기를 조정 합니다.  
  
4. 다른 끌어 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 폼입니다.  
  
5. 변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추가 텍스트 속성에 대 한 긴 문자열.**"  
  
     변경 내용을 커밋하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤 크기가 조정 되지 않습니다 자체 및 컨트롤의 오른쪽 가장자리에서 텍스트가 잘립니다.  
  
6. 변경을 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 확장 하 여는 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정을 <xref:System.Windows.Forms.Padding.All%2A> 속성을 5로 합니다.  
  
     컨트롤의 내부에 있는 텍스트 네 면 모두 잘립니다.  
  
7. 변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`입니다.  
  
     <xref:System.Windows.Forms.Button> 컨트롤 크기를 조정 하는 전체 문자열을 포함 하도록 합니다. 텍스트 주위의 안쪽 여백도, 추가 되었습니다 발생는 <xref:System.Windows.Forms.Button> 네 방향 모두에서 확장을 제어 합니다.  
  
8. <xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다. 폼의 오른쪽 아래 모서리 근처에 배치 합니다.  
  
9. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.  
  
10. 설정 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>합니다.  
  
11. 변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추가 텍스트 속성에 대 한 긴 문자열.**"  
  
     변경 내용을 커밋하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤 왼쪽 방향으로 크기를 조정 합니다. 일반적으로 자동 크기 조정 반대 방향으로 컨트롤의 크기가 늘어납니다 해당 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 설정 합니다.  
  
## <a name="autosize-and-autosizemode-properties"></a>자동 크기 조정 및 AutoSizeMode 속성  
 일부 컨트롤은 지원 된 `AutoSizeMode` 컨트롤의 자동 크기 조정 동작을 보다 세부적으로 제어를 제공 하는 속성입니다.  
  
#### <a name="to-use-the-autosizemode-property"></a>AutoSizeMode 속성을 사용 하려면  
  
1. <xref:System.Windows.Forms.Panel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.  
  
2. 값을 설정 합니다 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`입니다.  
  
3. 끌어서를 <xref:System.Windows.Forms.Button> 에서 제어 합니다 **도구 상자** 에 <xref:System.Windows.Forms.Panel> 컨트롤입니다.  
  
4. 위치는 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 아래 모서리를 <xref:System.Windows.Forms.Panel> 제어 합니다.  
  
5. 선택 된 <xref:System.Windows.Forms.Panel> 제어 하 고 오른쪽 크기 조정 핸들을 선택 합니다. 크기를 조정 합니다 <xref:System.Windows.Forms.Panel> 크고 작은 수를 제어 합니다.  
  
    > [!NOTE]
    >  자유롭게 조정할 수 있습니다 합니다 <xref:System.Windows.Forms.Panel> 컨트롤 이지만 있습니다 수 없습니다. 크기의 위치 보다 작은 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 아래 모퉁이. 기본 값을 기준으로이 동작을 지정 합니다 `AutoSizeMode` 속성, 즉 <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>합니다.  
  
6. 값을 설정 합니다 <xref:System.Windows.Forms.Panel> 컨트롤의 `AutoSizeMode` 속성을 <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>입니다.  
  
     합니다 <xref:System.Windows.Forms.Panel> 묶을 자체 컨트롤 크기를 <xref:System.Windows.Forms.Button> 컨트롤입니다. 크기를 변경할 수는 <xref:System.Windows.Forms.Panel> 제어 합니다.  
  
7. 끌어서 합니다 <xref:System.Windows.Forms.Button> 컨트롤의 왼쪽 위 모서리 쪽으로 <xref:System.Windows.Forms.Panel> 제어 합니다.  
  
     합니다 <xref:System.Windows.Forms.Panel> 컨트롤 크기를 조정 하는 <xref:System.Windows.Forms.Button> 컨트롤의 새 위치입니다.  
  
## <a name="next-steps"></a>다음 단계  
 Windows Forms 응용 프로그램에서 컨트롤 정렬에 대 한 여러 레이아웃 기능이 있습니다. 보십시오 일부 조합은 다음과 같습니다.  
  
-   사용 하 여 양식 작성을 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. 세부 정보를 참조 하세요. [연습: TableLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)합니다. 값을 변경 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성인 뿐만 <xref:System.Windows.Forms.Control.Margin%2A> 해당 자식 컨트롤의 속성.  
  
-   사용 하 여 동일한 실험 시도 <xref:System.Windows.Forms.FlowLayoutPanel> 제어 합니다. 세부 정보를 참조 하세요. [연습: FlowLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)합니다.  
  
-   자식 컨트롤을 도킹 하 여 실험을 <xref:System.Windows.Forms.Panel> 제어 합니다. 합니다 <xref:System.Windows.Forms.Control.Padding%2A> 속성이의 보다 일반적인 인식 합니다 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> 속성을 수행할 수는 경우에는 자식 컨트롤을 배치 하 여를 <xref:System.Windows.Forms.Panel> 컨트롤과 자식 컨트롤의 설정 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>. 설정 된 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 다양 한 값을 미치는 영향을 확인 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [AutoSize 속성 개요](autosize-property-overview.md)
- [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
