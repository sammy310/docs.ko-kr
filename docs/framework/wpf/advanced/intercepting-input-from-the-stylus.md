---
title: 스타일러스에서 입력 가로채기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 76976f1599ecbbaf7405d7941f66aa2c5f955565
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598948"
---
# <a name="intercepting-input-from-the-stylus"></a>스타일러스에서 입력 가로채기
합니다 <xref:System.Windows.Input.StylusPlugIns> 아키텍처를 통해 하위 수준 제어를 구현 하기 위한 메커니즘을 제공 <xref:System.Windows.Input.Stylus> 입력과 디지털 잉크 생성 <xref:System.Windows.Ink.Stroke> 개체입니다. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스는 사용자 지정 동작을 구현 하 고 최적의 성능을 위해 스타일러스 장치에서 가져온 데이터의 스트림으로 적용 메커니즘을 제공 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- [아키텍처](#Architecture)  
  
- [스타일러스 플러그 인을 구현합니다.](#ImplementingStylusPlugins)  
  
- [InkCanvas에 플러그 인 추가](#AddingYourPluginToAnInkCanvas)  
  
- [결론](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>아키텍처  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 의 발전은 합니다 [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) 에 설명 된 Api [액세스 및 조작 펜 입력](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)의 [Microsoft Windows XP Tablet PC Edition 소프트웨어 개발 키트 1.7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)합니다.  
  
 각 <xref:System.Windows.UIElement> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. 추가할 수 있습니다는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 요소를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성을 조작 <xref:System.Windows.Input.StylusPoint> 데이터 생성 됩니다. <xref:System.Windows.Input.StylusPoint> 데이터가 포함 하 여 시스템 디지타이저에서 지 원하는 모든 속성으로 구성 합니다 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 포인트 데이터 뿐만 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 데이터.  
  
 프로그램 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체에서 가져온 데이터의 스트림으로 직접 삽입 됩니다는 <xref:System.Windows.Input.Stylus> 추가할 때 장치를 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성. 플러그 인에 추가 되는 순서를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에는 수신 하는 순서가 결정 <xref:System.Windows.Input.StylusPoint> 데이터입니다. 예를 들어, 특정 지역에 대 한 입력을 제한 하는 필터 플러그 인을 추가 하 고 기록 될 때 해당 제스처를 인식 하는 플러그 인을 추가 하는 경우 제스처를 인식 하는 플러그 인 받을 필터링 <xref:System.Windows.Input.StylusPoint> 데이터입니다.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>스타일러스 플러그 인을 구현합니다.  
 플러그 인을 구현 하려면 파생 클래스에서 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>합니다. 이 클래스는 스트림에 적용된 데이터에서 입력 되는 <xref:System.Windows.Input.Stylus>합니다. 이 클래스의 값을 수정할 수는 <xref:System.Windows.Input.StylusPoint> 데이터입니다.  
  
> [!CAUTION]
>  경우는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throw 하거나 응용 프로그램이 종료 되므로 예외가 발생 합니다. 사용 하는 컨트롤을 철저히 테스트 해야 하는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 확실 한 경우에 컨트롤을 사용 하 고는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 예외를 throw 하지 것입니다.  
  
 다음 예제에서는 수정 하 여 스타일러스 입력을 제한 하는 플러그 인을 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 값을 <xref:System.Windows.Input.StylusPoint> 에서 나오는 데이터를는 <xref:System.Windows.Input.Stylus> 장치.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>InkCanvas에 플러그 인 추가  
 사용자 지정 플러그 인을 사용 하는 가장 쉬운 방법은 InkCanvas에서 파생 된 클래스를 구현 하 고 추가 하는 것은 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성입니다.  
  
 다음 예제에서는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 잉크를 필터링 하는 합니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 추가 하는 경우는 `FilterInkCanvas` 응용 프로그램을 실행, 알 수 있습니다 잉크 되지까지 지역으로 제한 된 사용자가 스트로크를 완료 합니다. 때문에 이것이 <xref:System.Windows.Controls.InkCanvas> 에 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성을 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 멤버인 이미를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션. 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 추가한 합니다 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션 수신 합니다 <xref:System.Windows.Input.StylusPoint> 후 데이터 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 데이터를 수신 합니다. 결과적으로 <xref:System.Windows.Input.StylusPoint> 데이터 후 사용자가 스트로크를 종료 하려면 펜을 뗄 때까지 필터링 되지 것입니다. 사용자가 그리는으로 잉크를 필터링 하려면 삽입 해야 합니다 `FilterPlugin` 하기 전에 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 다음 C# 코드에서는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 필터링 하는 잉크를 그릴 때.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>결론  
 직접 파생 시켜 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스에 삽입 하 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 컬렉션 디지털 잉크의 동작을 크게 향상 시킬 수 있습니다. 에 액세스할 수는 <xref:System.Windows.Input.StylusPoint> 데이터를 사용자 지정할 수 있으므로 생성 되는 <xref:System.Windows.Input.Stylus> 입력 합니다. 이러한 하위 수준 액세스를 갖고 있으므로 <xref:System.Windows.Input.StylusPoint> 데이터 잉크 모음 및 렌더링 최적의 성능으로 응용 프로그램을 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [고급 잉크 처리](advanced-ink-handling.md)
- [액세스 및 조작을 펜 입력](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
