---
title: '방법: UI인 추가 기능 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 339231031b9e57b9f00a2aeb6fbbde8ad66c1ad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141031"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>방법: UI인 추가 기능 만들기
이 예제에서는 WPF 독립 실행형 응용 프로그램에서 호스트하는 WPF(Windows 프레젠테이션 파운데이션)인 추가 기능을 만드는 방법을 보여 주며 있습니다.  
  
 추가 인은 WPF 사용자 컨트롤인 UI입니다. 이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다. WPF 독립 실행형 응용 프로그램은 추가 기능 UI를 기본 응용 프로그램 창의 콘텐츠로 호스팅합니다.  
  
 **필수 조건**  
  
 이 예제에서는 이 시나리오를 사용하도록 설정하는 .NET Framework 추가 기능 모델에 대한 WPF 확장을 중시하고 다음을 가정합니다.  
  
- 파이프라인, 추가 기능 및 호스트 개발을 비롯한 .NET Framework 추가 기능 모델에 대한 지식입니다. 이러한 개념에 익숙하지 않은 경우 [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))을 참조하십시오. 파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 보여 주는 자습서의 경우 [연습: 확장 가능한 응용 프로그램 만들기를](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))참조하십시오.  
  
- .NET 프레임워크 추가 기능 모델에 대한 WPF 확장에 대한 지식입니다. [WPF 추가 기능 개요를](wpf-add-ins-overview.md)참조하십시오.  
  
## <a name="example"></a>예제  
 WPF UI인 추가 기능을 만들려면 각 파이프라인 세그먼트, 추가 기능 및 호스트 응용 프로그램에 대한 특정 코드가 필요합니다.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>계약 파이프라인 세그먼트 구현

추가 기능이 UI인 경우 추가 기능의 계약은 구현되어야 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 이 예제에서는 `IWPFAddInContract` 다음 <xref:System.AddIn.Contract.INativeHandleContract>코드에 표시된 대로 을 구현합니다.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>추가 기능 뷰 파이프라인 세그먼트 구현

추가 기능이 <xref:System.Windows.FrameworkElement> 형식의 하위 클래스로 구현되므로 추가 기능 보기도 하위 <xref:System.Windows.FrameworkElement>클래스여야 합니다. 다음 코드는 클래스로 구현된 계약의 추가 기능 `WPFAddInView` 보기를 보여 주며, 이 코드는 클래스로 구현됩니다.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
여기서 추가 기능 보기는 에서 <xref:System.Windows.Controls.UserControl>파생됩니다. 따라서 추가 기능 UI는 <xref:System.Windows.Controls.UserControl>에서 파생되어야 합니다.  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>추가 기능 쪽 어댑터 파이프라인 세그먼트 구현

계약은 <xref:System.AddIn.Contract.INativeHandleContract>에서 추가 <xref:System.Windows.FrameworkElement> 기능(추가 기능 보기 파이프라인 세그먼트에 의해 지정된 대로)입니다. 따라서 격리 <xref:System.Windows.FrameworkElement> 경계를 <xref:System.AddIn.Contract.INativeHandleContract> 교차하기 전에 변환해야 합니다. 이 작업은 다음 코드와 같이 호출하여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>추가 인 사이드 어댑터에 의해 수행됩니다.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

추가 기능이 UI를 반환하는 추가 기능 모델(UI를 [반환하는 추가 기능 만들기](how-to-create-an-add-in-that-returns-a-ui.md)참조)에서 추가 기능 <xref:System.Windows.FrameworkElement> 어댑터는 을 호출하여 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>을 로 변환했습니다. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>호출할 코드를 작성하는 메서드를 구현해야 하지만 이 모델에서도 호출해야 합니다. 호출하는 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 코드가 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> <xref:System.AddIn.Contract.INativeHandleContract>를 예상하는 경우 호출하는 코드를 재정의하고 구현하여 이 작업을 수행합니다. 이 경우 호출자가 호스트 쪽 어댑터가 됩니다. 이에 대해서는 이후의 하위 단원에서 설명합니다.  
  
> [!NOTE]
> 또한 호스트 응용 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 프로그램 UI와 추가 기능 UI 간에 탭을 활성화하려면 이 모델에서 재정의해야 합니다. 자세한 내용은 WPF 추가 기능 [개요에서 "WPF](wpf-add-ins-overview.md)추가 기능 제한"을 참조하십시오.  
  
추가 인 사이드 어댑터는 <xref:System.AddIn.Contract.INativeHandleContract>에서 파생되는 인터페이스를 구현하기 때문에 <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>재정의 할 때 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 무시되지만 구현해야합니다.  
  
<a name="HostViewPipeline"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>호스트 뷰 파이프라인 세그먼트 구현

이 모델에서 호스트 응용 프로그램은 일반적으로 호스트 뷰가 하위 클래스가 <xref:System.Windows.FrameworkElement> 될 것으로 예상합니다. 호스트 측 어댑터는 격리 <xref:System.AddIn.Contract.INativeHandleContract> 경계를 <xref:System.Windows.FrameworkElement> 교차한 <xref:System.AddIn.Contract.INativeHandleContract> 후 를 a로 변환해야 합니다. 메서드를 호스트 응용 프로그램에서 호출하지 않으므로 호스트 <xref:System.Windows.FrameworkElement>뷰를 "반환"해야 <xref:System.Windows.FrameworkElement> 합니다. 따라서 호스트 뷰는 <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.UserControl>와 같은 다른 UI를 포함할 수 있는 하위 클래스에서 파생되어야 합니다. 다음 코드는 클래스로 구현된 계약의 호스트 `WPFAddInHostView` 보기를 보여 주며, 이 코드는 클래스로 구현됩니다.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>호스트 측 어댑터 파이프라인 세그먼트 구현

계약은 에서이지만 <xref:System.AddIn.Contract.INativeHandleContract>호스트 응용 프로그램은 <xref:System.Windows.Controls.UserControl> (호스트 뷰에서 지정한 대로) 예상합니다. 따라서 호스트 <xref:System.AddIn.Contract.INativeHandleContract> 뷰의 콘텐츠로 <xref:System.Windows.FrameworkElement> 설정하기 전에 격리 경계를 교차한 후 a로 변환해야 <xref:System.Windows.Controls.UserControl>합니다(파생됨).  
  
다음 코드와 같이 이 작업은 호스트 쪽 어댑터로 수행됩니다.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

보시다시피 호스트 측 어댑터는 추가 <xref:System.AddIn.Contract.INativeHandleContract> 측 어댑터의 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 메서드를 호출하여 획득합니다(격리 경계를 <xref:System.AddIn.Contract.INativeHandleContract> 교차하는 지점입니다).  
  
그런 다음 호스트 측 어댑터가 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> 을 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>호출하여 로 변환합니다. 마지막으로, <xref:System.Windows.FrameworkElement> 는 호스트 뷰의 콘텐츠로 설정됩니다.  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>추가 기능 구현

추가 기능 쪽 어댑터와 추가 기능 뷰를 배치했으면 다음 코드와 같이 추가 기능 뷰에서 파생시켜 추가 기능을 구현할 수 있습니다.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

이 예제에서는 추가 기능 개발자가 추가 기능 클래스와 추가 기능 UI가 아닌 추가 기능 개발자가 UI이기 때문에 추가 기능을 구현하기만 하면 됩니다.  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>호스트 애플리케이션 구현

호스트 측 어댑터 및 호스트 뷰를 만든 호스트 응용 프로그램은 .NET Framework 추가 기능 모델을 사용하여 파이프라인을 열고 추가 기능의 호스트 뷰를 획득할 수 있습니다. 이러한 단계는 다음 코드에 나와 있습니다.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

호스트 응용 프로그램은 일반적인 .NET Framework 추가 기능 모델 코드를 사용하여 추가 기능을 활성화하며, 이 코드는 호스트 뷰를 호스트 응용 프로그램에 암시적으로 반환합니다. 호스트 응용 프로그램은 이후에 <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Grid>에서 호스트 뷰(a)를 표시합니다.  
  
 추가 기능 UI와의 상호 작용을 처리하기 위한 코드는 추가 기능의 응용 프로그램 도메인에서 실행됩니다. 이러한 상호 작용에는 다음이 포함됩니다.  
  
- <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 처리.  
  
- 을 <xref:System.Windows.MessageBox>보여 주시면 됩니다.  
  
 이 작업은 호스트 애플리케이션에서 완전히 격리됩니다.  
  
## <a name="see-also"></a>참고 항목

- [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [WPF 추가 기능 개요](wpf-add-ins-overview.md)
