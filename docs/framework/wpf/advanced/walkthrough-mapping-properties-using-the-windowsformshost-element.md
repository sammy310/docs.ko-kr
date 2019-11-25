---
title: '연습: WindowsFormsHost 요소를 사용하여 속성 매핑'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 94d175ec58f35b7e807786c221437d05c605c0bc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974220"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>연습: WindowsFormsHost 요소를 사용하여 속성 매핑

이 연습에서는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 속성을 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성을 호스트 된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 해당 속성에 매핑하는 방법을 보여 줍니다.

이 연습에서 설명하는 작업은 다음과 같습니다.

- 프로젝트 만들기.

- 애플리케이션 레이아웃 정의.

- 새 속성 매핑 정의.

- 기본 속성 매핑 제거.

- 기본 속성 매핑 바꾸기.

- 기본 속성 매핑 확장.

이 연습에서 설명 하는 작업의 전체 코드 목록은 [WindowsFormsHost 요소 샘플을 사용 하 여 속성 매핑](https://go.microsoft.com/fwlink/?LinkID=160019)을 참조 하세요.

작업이 완료 되 면 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 해당 속성에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성을 매핑할 수 있습니다.

## <a name="prerequisites"></a>Prerequisites

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- Visual Studio 2017

## <a name="create-and-set-up-the-project"></a>프로젝트를 만들고 설정 합니다.

1. `PropertyMappingWithWfhSample`이라는 **WPF 앱** 프로젝트를 만듭니다.

2. **솔루션 탐색기**에서 windows integration .Dll 이라는 windows양식 통합 어셈블리에 대 한 참조를 추가 합니다.

3. **솔루션 탐색기**에서 Drawing 및 system.xml 어셈블리에 대 한 참조를 추가 합니다.

## <a name="defining-the-application-layout"></a>애플리케이션 레이아웃 정의

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 사용 하 여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅합니다.

### <a name="to-define-the-application-layout"></a>애플리케이션 레이아웃을 정의하려면

1. WPF 디자이너에서 Window1을 엽니다.

2. 기존 코드를 다음 코드로 바꿉니다.

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. 코드 편집기에서 Window1.xaml.cs를 엽니다.

4. 파일의 맨 위에서 다음 네임스페이스를 가져옵니다.

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a>새 속성 매핑 정의

<xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 몇 가지 기본 속성 매핑을 제공 합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드를 호출 하 여 새 속성 매핑을 추가 합니다.

### <a name="to-define-a-new-property-mapping"></a>새 속성 매핑을 정의하려면

- `Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     `AddClipMapping` 메서드는 <xref:System.Windows.UIElement.Clip%2A> 속성에 대 한 새 매핑을 추가 합니다.

     `OnClipChange` 메서드는 <xref:System.Windows.UIElement.Clip%2A> 속성을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> 속성으로 변환 합니다.

     `Window1_SizeChanged` 메서드는 창의 <xref:System.Windows.FrameworkElement.SizeChanged> 이벤트를 처리 하 고 클리핑 영역의 크기를 응용 프로그램 창에 맞게 조정 합니다.

## <a name="removing-a-default-property-mapping"></a>기본 속성 매핑 제거

<xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 메서드를 호출 하 여 기본 속성 매핑을 제거 합니다.

### <a name="to-remove-a-default-property-mapping"></a>기본 속성 매핑을 제거하려면

- `Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     `RemoveCursorMapping` 메서드는 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성의 기본 매핑을 삭제 합니다.

## <a name="replacing-a-default-property-mapping"></a>기본 속성 매핑 바꾸기

기본 매핑을 제거 하 고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>에서 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 메서드를 호출 하 여 기본 속성 매핑을 바꿉니다.

### <a name="to-replace-a-default-property-mapping"></a>기본 속성 매핑을 바꾸려면

- `Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     `ReplaceFlowDirectionMapping` 메서드는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성의 기본 매핑을 바꿉니다.

     `OnFlowDirectionChange` 메서드는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> 속성으로 변환 합니다.

     `cb_CheckedChanged` 메서드는 <xref:System.Windows.Forms.CheckBox> 컨트롤의 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트를 처리 합니다. <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성의 값을 기반으로 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 할당 합니다.

## <a name="extending-a-default-property-mapping"></a>기본 속성 매핑 확장

기본 속성 매핑을 사용하고 고유 매핑으로 확장할 수도 있습니다.

### <a name="to-extend-a-default-property-mapping"></a>기본 속성 매핑을 확장하려면

- `Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     `ExtendBackgroundMapping` 메서드는 기존 <xref:System.Windows.Controls.Control.Background%2A> 속성 매핑에 사용자 지정 속성 번역기를 추가 합니다.

     `OnBackgroundChange` 메서드는 호스트 된 컨트롤의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성에 특정 이미지를 할당 합니다. `OnBackgroundChange` 메서드는 기본 속성 매핑이 적용 된 후에 호출 됩니다.

## <a name="initializing-your-property-mappings"></a>속성 매핑 초기화

<xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기에서 앞에서 설명한 메서드를 호출 하 여 속성 매핑을 설정 합니다.

### <a name="to-initialize-your-property-mappings"></a>속성 매핑을 초기화하려면

1. `Window1` 클래스에 대 한 정의에 다음 코드를 복사 합니다.

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     `WindowLoaded` 메서드는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리 하 고 다음 초기화를 수행 합니다.

    - [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> 컨트롤을 만듭니다.

    - 연습에서 이전에 정의한 메서드를 호출하여 속성 매핑을 설정합니다.

    - 매핑된 속성에 초기 값을 할당합니다.

2. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다. <xref:System.Windows.FrameworkElement.FlowDirection%2A> 매핑의 효과를 확인 하려면이 확인란을 클릭 합니다. 확인란을 클릭하면 레이아웃이 왼쪽에서 오른쪽으로의 방향을 반대로 바꿉니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
