---
title: Windows Forms 및 WPF 속성 매핑
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: 45d86ac1b65306c8f404f9cea1e663b67128ebc4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794067"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Windows Forms 및 WPF 속성 매핑
Windows Forms 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술에는 두 가지 유사한 속성과 다른 속성 모델이 있습니다. *속성 매핑은* 두 아키텍처 간의 상호 운용을 지원 하 고 다음과 같은 기능을 제공 합니다.  
  
- 를 사용 하면 호스트 환경의 관련 속성 변경 내용을 호스팅된 컨트롤이 나 요소에 쉽게 매핑할 수 있습니다.  
  
- 가장 일반적으로 사용 되는 속성을 매핑하기 위한 기본 처리를 제공 합니다.  
  
- 기본 속성을 쉽게 제거, 재정의 또는 확장할 수 있습니다.  
  
- 호스트의 속성 값 변경 내용이 자동으로 검색 되어 호스팅된 컨트롤이 나 요소로 변환 되는지 확인 합니다.  
  
> [!NOTE]
> 속성 변경 이벤트는 호스팅 컨트롤이 나 요소 계층 구조로 전파 되지 않습니다. 직접 설정, 스타일, 상속, 데이터 바인딩 또는 속성의 값을 변경 하는 기타 메커니즘으로 인해 속성의 로컬 값이 변경 되지 않는 경우 속성 변환이 수행 되지 않습니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 속성 및 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 속성을 사용 하 여 속성 매핑에 액세스 합니다.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>WindowsFormsHost 요소가 포함 된 속성 매핑  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 변환 표를 사용 하 여 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성을 해당 Windows Forms로 변환 합니다.  
  
|Windows Presentation Foundation 호스팅|Windows Forms|상호 운용 동작|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성과 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성을 설정 합니다. 매핑은 다음 규칙을 사용 하 여 수행 됩니다.<br /><br /> -<xref:System.Windows.Controls.Control.Background%2A> 단색 인 경우 변환 되어 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 설정 하는 데 사용 됩니다. 호스팅된 컨트롤이 <xref:System.Windows.Forms.Control.BackColor%2A> 속성의 값을 상속할 수 있기 때문에 <xref:System.Windows.Forms.Control.BackColor%2A> 속성이 호스팅된 컨트롤에 설정 되어 있지 않습니다. **참고:**  호스팅된 컨트롤은 투명성을 지원 하지 않습니다. <xref:System.Windows.Forms.Control.BackColor%2A>에 할당 된 모든 색은 완전히 불투명 해야 하며 알파 값은 0xFF입니다. <br /><br /> -<xref:System.Windows.Controls.Control.Background%2A>가 단색이 아니면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 <xref:System.Windows.Controls.Control.Background%2A> 속성에서 비트맵을 만듭니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은이 비트맵을 호스트 된 컨트롤의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성에 할당 합니다. 이는 투명도와 비슷한 효과를 제공 합니다. **참고:**  이 동작을 재정의 하거나 <xref:System.Windows.Controls.Control.Background%2A> 속성 매핑을 제거할 수 있습니다.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|기본 매핑이 다시 할당 되지 않은 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 해당 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성이 설정 된 상위 항목을 찾을 때까지 상위 계층 구조를 트래버스 합니다. 이 값은 가장 가까운 해당 Windows Forms 커서로 변환 됩니다.<br /><br /> <xref:System.Windows.FrameworkElement.ForceCursor%2A> 속성에 대 한 기본 매핑이 재할당 되지 않은 경우 <xref:System.Windows.FrameworkElement.ForceCursor%2A>를 `true`로 설정 하 여 첫 번째 상위 항목에서 트래버스를 중지 합니다.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight>은 <xref:System.Windows.Forms.RightToLeft.No>에 매핑됩니다.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft>은 <xref:System.Windows.Forms.RightToLeft.Yes>에 매핑됩니다.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> 매핑되지 않았습니다.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType>은 <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>에 매핑됩니다.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|호스팅된 컨트롤의 <xref:System.Drawing.Font?displayProperty=nameWithType>에 대 한 <xref:System.Drawing.Font.Style%2A>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 집합은 해당 <xref:System.Drawing.Font>으로 변환 됩니다. 이러한 속성 중 하나가 변경 되 면 새 <xref:System.Drawing.Font> 만들어집니다. <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic>를 사용할 수 없습니다. <xref:System.Windows.FontStyles.Italic%2A> 또는 <xref:System.Windows.FontStyles.Oblique%2A>의 경우: <xref:System.Drawing.FontStyle.Italic>를 사용할 수 있습니다.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|호스팅된 컨트롤의 <xref:System.Drawing.Font?displayProperty=nameWithType>에 대 한 <xref:System.Drawing.Font.Style%2A>|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 집합은 해당 <xref:System.Drawing.Font>으로 변환 됩니다. 이러한 속성 중 하나가 변경 되 면 새 <xref:System.Drawing.Font> 만들어집니다. <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>또는 <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold>을 사용할 수 있습니다. <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>또는 <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold>을 사용할 수 없습니다.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 집합은 해당 <xref:System.Drawing.Font>으로 변환 됩니다. 이러한 속성 중 하나가 변경 되 면 새 <xref:System.Drawing.Font> 만들어집니다. 호스팅된 Windows Forms 컨트롤은 글꼴 크기에 따라 크기를 조정 합니다.<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 글꼴 크기는 1 인치의 90-6 인치, Windows Forms는 1 인치의 1 seventy로 표시 됩니다. 해당 변환은 다음과 같습니다.<br /><br /> Windows Forms 글꼴 크기 = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 글꼴 크기 * 72.0/96.0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Foreground%2A> 속성 매핑은 다음 규칙을 사용 하 여 수행 됩니다.<br /><br /> -<xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.SolidColorBrush>경우 <xref:System.Windows.Forms.Control.ForeColor%2A>에 대 한 <xref:System.Windows.Media.SolidColorBrush.Color%2A>를 사용 합니다.<br />-<xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.GradientBrush>경우 <xref:System.Windows.Forms.Control.ForeColor%2A>에 대 한 가장 낮은 오프셋 값을 가진 <xref:System.Windows.Media.GradientStop> 색을 사용 합니다.<br />-다른 <xref:System.Windows.Media.Brush> 형식의 경우 <xref:System.Windows.Forms.Control.ForeColor%2A> 변경 되지 않은 상태로 둡니다. 이는 기본값이 사용 됨을 의미 합니다.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>를 설정 하면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Enabled%2A> 속성을 설정 합니다.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|호스팅된 Windows Forms 컨트롤에서 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 네 가지 값은 모두 동일한 <xref:System.Windows.Thickness> 값으로 설정 됩니다.<br /><br /> -<xref:System.Int32.MaxValue> 보다 큰 값은 <xref:System.Int32.MaxValue>로 설정 됩니다.<br />-<xref:System.Int32.MinValue> 보다 작은 값은 <xref:System.Int32.MinValue>로 설정 됩니다.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> <xref:System.Windows.Forms.Control.Visible%2A> = `true`에 매핑됩니다. 호스팅된 Windows Forms 컨트롤이 표시 됩니다. 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 `false`로 명시적으로 설정 하는 것은 권장 되지 않습니다.<br />-   <xref:System.Windows.Visibility.Collapsed> <xref:System.Windows.Forms.Control.Visible%2A> = `true` 또는 `false`에 매핑됩니다. 호스팅된 Windows Forms 컨트롤은 그려지지 않으며 영역을 축소 합니다.<br />-   <xref:System.Windows.Visibility.Hidden>: 호스팅된 Windows Forms 컨트롤은 레이아웃의 공간을 차지 하지만 표시 되지 않습니다. 이 경우 <xref:System.Windows.Forms.Control.Visible%2A> 속성이 `true`로 설정 됩니다. 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 `false`로 명시적으로 설정 하는 것은 권장 되지 않습니다.|  
  
 컨테이너 요소의 연결 된 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 의해 완벽 하 게 지원 됩니다.  
  
 자세한 내용은 [연습: WindowsFormsHost 요소를 사용 하 여 속성 매핑](walkthrough-mapping-properties-using-the-windowsformshost-element.md)을 참조 하세요.  
  
## <a name="updates-to-parent-properties"></a>부모 속성에 대 한 업데이트  
 대부분의 부모 속성을 변경 하면 호스팅된 자식 컨트롤에 알림이 발생 합니다. 다음 목록에서는 값이 변경 될 때 알림을 발생 시 키 지 않는 속성에 대해 설명 합니다.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 예를 들어 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 변경 하는 경우 호스트 된 컨트롤의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성이 변경 되지 않습니다.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>ElementHost 컨트롤을 사용 하 여 속성 매핑  
 다음 속성은 기본 제공 변경 알림을 제공 합니다. 이러한 속성을 매핑할 때 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 메서드를 호출 하지 마십시오.  
  
- 자동 크기 조정  
  
- 배경색  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- CausesValidation  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Cursor  
  
- 도킹  
  
- Enabled  
  
- 글꼴  
  
- ForeColor  
  
- Location  
  
- 여백  
  
- 안쪽 여백  
  
- 부모  
  
- Region  
  
- RightToLeft  
  
- 크기  
  
- TabIndex  
  
- TabStop  
  
- 텍스트  
  
- 표시 가능  
  
 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 다음 변환 표를 사용 하 여 기본 Windows Forms 속성을 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]로 변환 합니다.  
  
 자세한 내용은 [연습: ElementHost 컨트롤을 사용 하 여 속성 매핑](walkthrough-mapping-properties-using-the-elementhost-control.md)합니다.  
  
|Windows Forms 호스팅|Windows Presentation Foundation|상호 운용 동작|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 호스팅된 요소의 (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|이 속성을 설정 하면 <xref:System.Windows.Media.ImageBrush>강제로 다시 그려집니다. <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 속성이 `false` (기본값)로 설정 된 경우이 <xref:System.Windows.Media.ImageBrush>은 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 속성 및 연결 된 모든 그리기 처리기를 포함 하 여 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 모양을 기반으로 합니다.<br /><br /> <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 속성이 `true`로 설정 된 경우 <xref:System.Windows.Media.ImageBrush>는 부모의 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> 속성 및 연결 된 모든 그리기 처리기를 포함 하 여 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 부모 모양에 따라 됩니다.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 호스팅된 요소의 (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|이 속성을 설정 하면 <xref:System.Windows.Forms.Control.BackColor%2A> 매핑에 대해 설명한 것과 동일한 동작이 발생 합니다.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> 호스팅된 요소의 (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|이 속성을 설정 하면 <xref:System.Windows.Forms.Control.BackColor%2A> 매핑에 대해 설명한 것과 동일한 동작이 발생 합니다.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Windows Forms 표준 커서는 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 표준 커서로 변환 됩니다. Windows Forms 표준 커서가 아니면 기본값이 할당 됩니다.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A> 설정 되 면 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 호스팅된 요소에 대해 <xref:System.Windows.UIElement.IsEnabled%2A> 속성을 설정 합니다.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A> 값은 해당 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] font 속성 집합으로 변환 됩니다.|  
|<xref:System.Drawing.Font.Bold%2A>|호스팅된 요소의 <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Bold%2A>이`true`이면 <xref:System.Windows.Controls.Control.FontWeight%2A>가 <xref:System.Windows.FontWeights.Bold%2A>로 설정됩니다.<br /><br /> <xref:System.Drawing.Font.Bold%2A>이`false`이면 <xref:System.Windows.Controls.Control.FontWeight%2A>가 <xref:System.Windows.FontWeights.Normal%2A>로 설정됩니다.|  
|<xref:System.Drawing.Font.Italic%2A>|호스팅된 요소의 <xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Italic%2A>이`true`이면 <xref:System.Windows.Controls.Control.FontStyle%2A>가 <xref:System.Windows.FontStyles.Italic%2A>로 설정됩니다.<br /><br /> <xref:System.Drawing.Font.Italic%2A>이`false`이면 <xref:System.Windows.Controls.Control.FontStyle%2A>가 <xref:System.Windows.FontStyles.Normal%2A>로 설정됩니다.|  
|<xref:System.Drawing.Font.Strikeout%2A>|호스팅된 요소의 <xref:System.Windows.TextDecorations>|<xref:System.Windows.Controls.TextBlock> 컨트롤을 호스트 하는 경우에만 적용 됩니다.|  
|<xref:System.Drawing.Font.Underline%2A>|호스팅된 요소의 <xref:System.Windows.TextDecorations>|<xref:System.Windows.Controls.TextBlock> 컨트롤을 호스트 하는 경우에만 적용 됩니다.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No>은 <xref:System.Windows.FlowDirection.LeftToRight>에 매핑됩니다.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes>은 <xref:System.Windows.FlowDirection.RightToLeft>에 매핑됩니다.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 다음 규칙을 사용 하 여 호스팅된 요소의 <xref:System.Windows.UIElement.Visibility%2A> 속성을 설정 합니다.<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` <xref:System.Windows.Visibility.Visible>에 매핑됩니다.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` <xref:System.Windows.Visibility.Hidden>에 매핑됩니다.|  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
- [WPF 및 Windows Forms 상호 운용성](wpf-and-windows-forms-interoperation.md)
- [연습: WindowsFormsHost 요소를 사용하여 속성 매핑](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [연습: ElementHost 컨트롤을 사용하여 속성 매핑](walkthrough-mapping-properties-using-the-elementhost-control.md)
