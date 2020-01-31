---
title: 안쪽 여백, 여백 및 AutoSize 속성을 사용 하 여 컨트롤 레이아웃
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ca7942c04434592f2541252c47ac3dd17e03dbac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742377"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>연습: 패딩, 여백 및 AutoSize 속성을 사용 하 여 컨트롤 레이아웃

폼의 정확한 컨트롤 배치는 많은 애플리케이션에서 우선 순위가 높습니다. Visual Studio의 **Windows Forms 디자이너** 는이를 위해 다양 한 레이아웃 도구를 제공 합니다. 가장 중요 한 세 가지는 모든 Windows Forms 컨트롤에 있는 <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>및 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.

<xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.

<xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.

다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.

![Windows Forms 컨트롤의 여백 및 안쪽 여백](./media/vs-winformpadmargin.gif)

<xref:System.Windows.Forms.Control.AutoSize%2A> 속성은 컨트롤이 내용에 맞게 자동으로 크기를 조정 하도록 지시 합니다. 원래 <xref:System.Windows.Forms.Control.Size%2A> 속성 값 보다 작은 크기로 크기를 조정 하지 않으며 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 값을 고려 합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료 하려면 Visual Studio가 필요 합니다.

## <a name="create-the-project"></a>프로젝트를 만듭니다.

1. Visual Studio에서 `LayoutExample`라는 **Windows 응용 프로그램** 프로젝트를 만듭니다.

2. **Windows Forms 디자이너**에서 양식을 선택 합니다.

## <a name="set-margins-for-controls"></a>컨트롤의 여백 설정

<xref:System.Windows.Forms.Control.Margin%2A> 속성을 사용 하 여 컨트롤 간의 기본 거리를 설정할 수 있습니다. 컨트롤을 다른 컨트롤에 가까이 이동할 때 두 컨트롤의 여백을 보여 주는 맞춤선이 표시 됩니다. 이동 하는 컨트롤은 여백으로 정의 된 거리에도 맞춰집니다.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Margin 속성을 사용 하 여 폼에 컨트롤을 정렬 합니다.

1. 두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 **도구 상자** 에서 폼으로 끌어 옵니다.

2. <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택 하 고 거의 닿을 때까지 다른 컨트롤 가까이로 이동 합니다.

   두 항목 사이에 나타나는 맞춤선을 관찰 합니다. 이 거리는 두 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 값 합계입니다. 이동 하는 컨트롤이이 거리에 맞춰집니다. 자세한 내용은 [연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조 하세요.

3. **속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **20**으로 설정 하 여 컨트롤 중 하나의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경 합니다.

4. <xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택 하 고 다른 컨트롤 가까이로 이동 합니다.

   여백 값의 합을 정의 하는 맞춤선이 더 길고 컨트롤이 다른 컨트롤에서 더 큰 거리에 맞춰집니다.

5. **속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.Top%2A> 속성을 **5**로 설정 하 여 선택한 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경 합니다.

6. 선택한 컨트롤을 다른 컨트롤 아래로 이동 하 여 맞춤선이 더 짧아 지는 지 확인 합니다. 선택한 컨트롤을 다른 컨트롤의 왼쪽으로 이동 하 고 4 단계에서 관찰 된 값이 맞춤선에 유지 되는지 확인 합니다.

7. <xref:System.Windows.Forms.Control.Margin%2A> 속성의 각 측면 (<xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>을 다른 값으로 설정 하거나 <xref:System.Windows.Forms.Padding.All%2A> 속성을 사용 하 여 모두 동일한 값으로 설정할 수 있습니다.

## <a name="set-padding-for-controls"></a>컨트롤의 안쪽 여백 설정

응용 프로그램에 필요한 정확한 레이아웃을 얻기 위해 컨트롤에는 종종 자식 컨트롤이 포함 됩니다. 자식 컨트롤의 테두리를 부모 컨트롤의 테두리에 근접 하 게 지정 하려는 경우 부모 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 함께 사용 합니다. <xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 콘텐츠 (예: <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성)가 해당 테두리에 근접 하는 것을 제어 하는 데도 사용 됩니다.

### <a name="arrange-controls-on-your-form-using-padding"></a>안쪽 여백을 사용 하 여 폼에 컨트롤 정렬

1. <xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.

2. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 변경 합니다.

3. **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **5**로 설정 하 여 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경 합니다.

   컨트롤이 확장 되어 새 안쪽 여백을 위한 공간을 제공 합니다.

4. <xref:System.Windows.Forms.GroupBox> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다. **도구 상자** 의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤로 끌어 옵니다. <xref:System.Windows.Forms.GroupBox> 컨트롤의 오른쪽 아래 모퉁이에 <xref:System.Windows.Forms.Button> 컨트롤의 위치를 조정 합니다.

   <xref:System.Windows.Forms.Button> 컨트롤이 <xref:System.Windows.Forms.GroupBox> 컨트롤의 아래쪽 및 오른쪽 테두리에 도달할 때 나타나는 맞춤선을 관찰 합니다. 이러한 맞춤선은 <xref:System.Windows.Forms.Button>의 <xref:System.Windows.Forms.Control.Margin%2A> 속성에 해당 합니다.

5. **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **20**으로 설정 하 여 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경 합니다.

6. <xref:System.Windows.Forms.GroupBox> 컨트롤 내에서 <xref:System.Windows.Forms.Button> 컨트롤을 선택 하 고 <xref:System.Windows.Forms.GroupBox>의 가운데로 이동 합니다.

   맞춤선은 <xref:System.Windows.Forms.GroupBox> 컨트롤의 테두리에서 더 큰 거리에 표시 됩니다. 이 거리는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 합입니다.

## <a name="size-controls-automatically"></a>컨트롤 자동 크기 조정

일부 응용 프로그램에서는 컨트롤의 크기가 디자인 타임에와 동일 하 게 실행 되지 않습니다. 예를 들어 <xref:System.Windows.Forms.Button> 컨트롤의 텍스트는 데이터베이스에서 가져올 수 있으며 해당 길이는 미리 알 수 없습니다.

<xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 `true`으로 설정 되 면 컨트롤은 해당 내용에 맞게 크기가 조정 됩니다. 자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)를 참조 하세요.

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>AutoSize 속성을 사용 하 여 폼에 컨트롤 정렬

1. <xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.

2. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 변경 합니다.

3. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 **이 단추로 텍스트 속성에 대 한 긴 문자열로**변경 합니다.

   변경 내용을 커밋하면 <xref:System.Windows.Forms.Button> 컨트롤의 크기가 새 텍스트에 맞게 자동으로 조정 됩니다.

4. 다른 <xref:System.Windows.Forms.Button> 컨트롤을 **도구 상자** 에서 폼으로 끌어 놓습니다.

5. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추에는 텍스트 속성에 대 한 긴 문자열이 있습니다.** "로 변경 합니다.

   변경을 커밋하면 <xref:System.Windows.Forms.Button> 컨트롤의 크기가 자동으로 조정 되지 않으며 텍스트가 컨트롤의 오른쪽 가장자리에 의해 잘립니다.

6. **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **5**로 설정 하 여 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경 합니다.

   컨트롤의 내부에 있는 텍스트는 네 면 모두 잘립니다.

7. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 **true**로 변경 합니다.

   <xref:System.Windows.Forms.Button> 컨트롤은 전체 문자열을 포함 하도록 크기를 조정 합니다. 또한 텍스트 주위에 안쪽 여백이 추가 되어 <xref:System.Windows.Forms.Button> 컨트롤이 4 방향으로 모두 확장 됩니다.

8. <xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다. 폼의 오른쪽 아래 모퉁이 근처에 배치 합니다.

9. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 변경 합니다.

10. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>로 설정 합니다.

11. <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추에는 텍스트 속성에 대 한 긴 문자열이 있습니다.** "로 변경 합니다.

   변경 내용을 커밋하는 경우 <xref:System.Windows.Forms.Button> 컨트롤은 왼쪽 방향으로 크기를 조정 합니다. 일반적으로 자동 크기 조정은 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 설정과 반대 방향으로 컨트롤의 크기를 증가 시킵니다.

## <a name="autosize-and-autosizemode-properties"></a>AutoSize 및 AutoSizeMode 속성

 일부 컨트롤은 컨트롤의 자동 크기 조정 동작에 대 한 보다 세분화 된 제어를 제공 하는 `AutoSizeMode` 속성을 지원 합니다.

### <a name="use-the-autosizemode-property"></a>AutoSizeMode 속성 사용

1. <xref:System.Windows.Forms.Panel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.

2. <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 설정 합니다.

3. **도구 상자** 의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤로 끌어 옵니다.

4. <xref:System.Windows.Forms.Panel> 컨트롤의 오른쪽 아래 모퉁이 근처에 <xref:System.Windows.Forms.Button> 컨트롤을 놓습니다.

5. <xref:System.Windows.Forms.Panel> 컨트롤을 선택 하 고 오른쪽 아래 크기 조정 핸들을 가져옵니다. <xref:System.Windows.Forms.Panel> 컨트롤의 크기를 더 크거나 작게 조정 합니다.

   > [!NOTE]
   > <xref:System.Windows.Forms.Panel> 컨트롤의 크기를 자유롭게 조정할 수 있지만 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 아래 모퉁이의 위치 보다 작게 크기를 조정할 수 없습니다. 이 동작은 <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>되는 `AutoSizeMode` 속성의 기본값으로 지정 됩니다.

6. <xref:System.Windows.Forms.Panel> 컨트롤의 `AutoSizeMode` 속성 값을 <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>로 설정 합니다.

   <xref:System.Windows.Forms.Panel> 컨트롤의 크기는 <xref:System.Windows.Forms.Button> 컨트롤을 둘러쌉니다. <xref:System.Windows.Forms.Panel> 컨트롤의 크기를 조정할 수 없습니다.

7. <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤의 왼쪽 위 모퉁이를 향해 끌어 옵니다.

   <xref:System.Windows.Forms.Panel> 컨트롤은 <xref:System.Windows.Forms.Button> 컨트롤의 새 위치로 크기가 조정 됩니다.

## <a name="next-steps"></a>다음 단계

Windows Forms 응용 프로그램에서 컨트롤을 정렬 하는 다양 한 레이아웃 기능이 있습니다. 다음은 시도해 볼 수 있는 몇 가지 조합입니다.

- <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용 하 여 양식을 작성 합니다. 자세한 내용은 [연습: TableLayoutPanel를 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조 하세요. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값 뿐만 아니라 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경해 봅니다.

- <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤을 사용 하 여 동일한 실험을 시도 합니다. 자세한 내용은 [연습: FlowLayoutPanel를 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)을 참조 하세요.

- <xref:System.Windows.Forms.Panel> 컨트롤의 도킹 자식 컨트롤을 사용 하 여 실험 합니다. <xref:System.Windows.Forms.Control.Padding%2A> 속성은 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> 속성을 보다 일반적으로 인식 하며, 자식 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤에 배치 하 고 자식 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정 하 여이를 구현할 수 있습니다. <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 다양 한 값으로 설정 하 고 효과를 확인 합니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [AutoSize 속성 개요](autosize-property-overview.md)
- [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
