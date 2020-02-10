---
title: WindowsFormsHost 요소에 대한 레이아웃 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
ms.openlocfilehash: 89ed57a787b93a1326b4accd3bb1bc5ff9a825fd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095153"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>WindowsFormsHost 요소에 대한 레이아웃 고려 사항
이 항목에서는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템과 상호 작용 하는 방법에 대해 설명 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 Windows Forms는 폼 또는 페이지의 크기를 조정 하 고 위치를 지정 하는 것과 유사한 논리를 지원 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 Windows Forms 컨트롤을 호스트 하는 하이브리드 UI (사용자 인터페이스)를 만들 때 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 두 가지 레이아웃 체계를 통합 합니다.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>WPF와 Windows Forms 간의 레이아웃 차이  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 해상도 독립적 레이아웃을 사용 합니다. 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 차원은 *장치 독립적 픽셀*을 사용 하 여 지정 됩니다. 장치 독립적 픽셀은 크기 및 해상도에 구애 받지 않는 1 인치의 90-6입니다. 따라서 72 dpi 모니터 또는 19200 dpi 프린터로 렌더링 하는지 여부에 관계 없이 비슷한 결과를 얻을 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 *동적 레이아웃*을 기반으로 합니다. 즉, UI 요소는 콘텐츠, 부모 레이아웃 컨테이너 및 사용 가능한 화면 크기에 따라 폼 이나 페이지에 정렬 됩니다. 동적 레이아웃은 문자열이 변경 길이를 포함 하는 경우 UI 요소의 크기와 위치를 자동으로 조정 하 여 지역화를 용이 하 게 합니다.  
  
 Windows Forms 레이아웃은 장치에 따라 다르며 정적일 가능성이 높습니다. 일반적으로 Windows Forms 컨트롤은 하드웨어 픽셀에 지정 된 차원을 사용 하 여 폼에 배치 됩니다. 그러나 Windows Forms는 다음 표에 요약 된 것 처럼 몇 가지 동적 레이아웃 기능을 지원 합니다.  
  
|레이아웃 기능|설명|  
|--------------------|-----------------|  
|자동 크기 조정|일부 Windows Forms 컨트롤의 크기를 조정 하면 해당 내용이 제대로 표시 됩니다. 자세한 내용은 [AutoSize 속성 개요](../../winforms/controls/autosize-property-overview.md)를 참조 하세요.|  
|고정 및 도킹|Windows Forms 컨트롤은 부모 컨테이너를 기반으로 위치 지정 및 크기 조정을 지원 합니다. 자세한 내용은 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>를 참조하세요.|  
|자동 확장|컨테이너 컨트롤은 출력 장치의 해상도 또는 기본 컨테이너 글꼴의 크기 (픽셀 단위)에 따라 자신과 자식 항목의 크기를 조정 합니다. 자세한 내용은 [Windows Forms 자동 크기 조정](../../winforms/automatic-scaling-in-windows-forms.md)을 참조 하세요.|  
|레이아웃 컨테이너|<xref:System.Windows.Forms.FlowLayoutPanel> 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 자식 컨트롤을 정렬 하 고 내용에 따라 크기를 조정 합니다.|  
  
## <a name="layout-limitations"></a>레이아웃 제한  
 일반적으로 Windows Forms 컨트롤의 크기를 조정 하 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가능한 범위로 변환할 수 없습니다. 다음 목록에서는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 호스팅된 Windows Forms 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템에 통합 하려고 할 때 알려진 제한 사항을 설명 합니다.  
  
- 경우에 따라 Windows Forms 컨트롤의 크기를 조정할 수 없거나 특정 차원 으로만 크기를 조정할 수 있습니다. 예를 들어 Windows Forms <xref:System.Windows.Forms.ComboBox> 컨트롤은 컨트롤의 글꼴 크기에 따라 정의 되는 단일 높이도 지원 합니다. 요소가 세로로 확장 될 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 동적 레이아웃에서 호스팅된 <xref:System.Windows.Forms.ComboBox> 컨트롤은 예상 대로 확장 되지 않습니다.  
  
- Windows Forms 컨트롤은 회전 하거나 기울일 수 없습니다. 기울이기 또는 회전 변환을 적용 하면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트를 발생 시킵니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트를 처리 하지 않으면 <xref:System.InvalidOperationException> 발생 합니다.  
  
- 대부분의 경우 Windows Forms 컨트롤은 비례 크기 조정을 지원 하지 않습니다. 컨트롤의 전체 크기는 조정할 수 있지만, 컨트롤의 구성 요소와 자식 컨트롤의 크기가 예상대로 조정되지 않을 수 있습니다. 이러한 제한 사항은 각 Windows Forms 컨트롤이 크기 조정을 얼마나 잘 지원 하는지에 따라 달라 집니다. 또한 Windows Forms 컨트롤을 0 픽셀 크기로 축소할 수 없습니다.  
  
- Windows Forms 컨트롤은 자동 크기 조정을 지원 합니다 .이를 통해 폼은 글꼴 크기에 따라 자동으로 크기를 조정 하 고 컨트롤의 크기를 조정 합니다. 개별 요소의 크기는 동적으로 조정할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 글꼴 크기를 변경해도 전체 레이아웃의 크기는 조정되지 않습니다.  
  
### <a name="z-order"></a>Z 순서  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 겹치는 동작을 제어하기 위해 요소의 z 순서를 변경할 수 있습니다. 호스팅된 Windows Forms 컨트롤은 별도의 HWND로 그려지며 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 위에 그려집니다.  
  
 호스팅된 Windows Forms 컨트롤은 <xref:System.Windows.Documents.Adorner> 요소 위에도 그려집니다.  
  
## <a name="layout-behavior"></a>레이아웃 동작  
 다음 섹션에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 Windows Forms 컨트롤을 호스팅할 때 레이아웃 동작의 특정 측면에 대해 설명 합니다.  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>크기 조정, 단위 변환 및 장치 독립성  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 Windows Forms 차원과 관련 된 작업을 수행할 때마다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 하드웨어 픽셀에 대 한 장치 독립적 픽셀을 Windows Forms에 포함 하는 두 가지 좌표계를 사용할 수 있습니다. 따라서 일관 된 레이아웃을 얻기 위해서는 적절 한 단위 및 크기 조정 변환을 적용 해야 합니다.  
  
 좌표계 간의 변환은 현재 장치 해상도와 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소나 해당 상위 항목에 적용 된 레이아웃 또는 렌더링 변환에 따라 달라 집니다.  
  
 출력 장치가 96 dpi이 고 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 배율이 적용 되지 않은 경우 하나의 장치 독립적 픽셀은 하나의 하드웨어 픽셀과 같습니다.  
  
 다른 모든 경우에는 좌표계 크기 조정이 필요 합니다. 호스팅된 컨트롤의 크기가 조정 되지 않습니다. 대신, <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스트 된 컨트롤과 모든 자식 컨트롤의 크기를 조정 하려고 합니다. Windows Forms는 크기 조정을 완전히 지원 하지 않으므로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 특정 컨트롤에서 지 원하는 수준으로 확장 됩니다.  
  
 재정의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> 호스팅된 Windows Forms 컨트롤에 대 한 사용자 지정 크기 조정 동작을 제공 하는 방법입니다.  
  
 크기 조정 외에도 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 표에 설명 된 대로 반올림 및 오버플로 사례를 처리 합니다.  
  
|변환 문제|설명|  
|----------------------|-----------------|  
|반올림|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 장치 독립적 픽셀 차원은 `double`으로 지정 되 고 Windows Forms 하드웨어 픽셀 차원은 `int`로 지정 됩니다. `double`기반 차원이 `int`기반 차원으로 변환 되는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 표준 반올림을 사용 하므로 0.5 미만의 소수 자릿수 값이 0으로 반올림 됩니다.|  
|오버플로|<xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 `double` 값에서 `int` 값으로 변환 되 면 오버플로가 발생할 수 있습니다. <xref:System.Int32.MaxValue> 보다 큰 값은 <xref:System.Int32.MaxValue>로 설정 됩니다.|  
  
### <a name="layout-related-properties"></a>레이아웃 관련 속성  
 Windows Forms 컨트롤과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소의 레이아웃 동작을 제어 하는 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 의해 적절 하 게 매핑됩니다. 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)을 참조하세요.  
  
### <a name="layout-changes-in-the-hosted-control"></a>호스팅된 컨트롤의 레이아웃 변경 내용  
 호스팅된 Windows Forms 컨트롤의 레이아웃 변경 내용은 레이아웃 업데이트를 트리거하기 위해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 전파 됩니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost>에 대 한 <xref:System.Windows.UIElement.InvalidateMeasure%2A> 메서드는 호스트 된 컨트롤의 레이아웃 변경으로 인해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 엔진이 실행 되도록 합니다.  
  
### <a name="continuously-sized-windows-forms-controls"></a>지속적으로 크기가 조정 되는 Windows Forms 컨트롤  
 연속 크기 조정을 지 원하는 Windows Forms 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템과 완벽 하 게 상호 작용 합니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 일반적인 방법으로 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 사용 하 여 호스팅된 Windows Forms 컨트롤의 크기를 조정 하 고 정렬 합니다.  
  
### <a name="sizing-algorithm"></a>크기 조정 알고리즘  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음 절차를 사용 하 여 호스트 된 컨트롤의 크기를 조정 합니다.  
  
1. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 재정의 합니다.  
  
2. 호스팅된 컨트롤의 크기를 확인 하기 위해 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드에 전달 된 제약 조건에서 변환 된 제약 조건을 사용 하 여 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드를 호출 합니다.  
  
3. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드는 호스팅된 컨트롤을 지정 된 크기 제약 조건으로 설정 하려고 시도 합니다.  
  
4. 호스팅된 컨트롤의 <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정 된 제약 조건과 일치 하면 호스팅된 컨트롤의 크기가 제약 조건에 맞게 조정 됩니다.  
  
 <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정 된 제약 조건과 일치 하지 않으면 호스팅된 컨트롤이 연속 크기 조정을 지원 하지 않습니다. 예를 들어 <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 불연속 크기만 허용 합니다. 이 컨트롤에 허용 되는 크기는 높이와 너비의 정수 (월 수를 나타냄)로 구성 됩니다. 이와 같은 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 다음과 같이 동작 합니다.  
  
- <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정 된 제약 조건 보다 큰 크기를 반환 하는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스트 된 컨트롤을 자릅니다. Height 및 width는 개별적으로 처리 되므로 호스트 된 컨트롤이 어느 방향에서 나 잘릴 수 있습니다.  
  
- <xref:System.Windows.Forms.Control.Size%2A> 속성이 지정 된 제약 조건 보다 작은 크기를 반환 하는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost>이 크기 값을 허용 하 고 값을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템으로 반환 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [연습: WPF에서 Windows Forms 컨트롤 정렬](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [WPF 샘플에서 Windows Forms 컨트롤 정렬](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)
- [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)
- [마이그레이션 및 상호 운용성](migration-and-interoperability.md)
