---
title: '방법: UI를 반환하는 추가 기능 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: f8323fe35555a56d39c1efed649c2aa3fcf17e43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174591"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>방법: UI를 반환하는 추가 기능 만들기
이 예제에서는 WPF(Windows 프레젠테이션 파운데이션)를 호스트 WPF 독립 실행형 응용 프로그램에 반환하는 추가 기능을 만드는 방법을 보여 주습니다.  
  
 추가 기능을 사용하면 WPF 사용자 컨트롤인 UI가 반환됩니다. 이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다. WPF 독립 실행형 응용 프로그램은 추가 기능을 호스트하고 사용자 컨트롤(추가 기능에서 반환됨)을 기본 응용 프로그램 창의 콘텐츠로 표시합니다.  
  
 **필수 조건**  
  
 이 예제에서는 이 시나리오를 사용하도록 설정하는 .NET Framework 추가 기능 모델에 대한 WPF 확장을 중시하고 다음을 가정합니다.  
  
- 파이프라인, 추가 기능 및 호스트 개발을 비롯한 .NET Framework 추가 기능 모델에 대한 지식입니다. 이러한 개념에 익숙하지 않은 경우 [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))을 참조하십시오. 파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 보여 주는 자습서의 경우 [연습: 확장 가능한 응용 프로그램 만들기를](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))참조하십시오.  
  
- 여기에서 찾을 수 있는 .NET 프레임워크 추가 기능 모델에 대한 WPF 확장에 대한 지식: [WPF 추가 기능 개요](wpf-add-ins-overview.md).  
  
## <a name="example"></a>예제  
 WPF UI를 반환 하는 추가 기능을 만들려면 각 파이프라인 세그먼트, 추가 기능 및 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>계약 파이프라인 세그먼트 구현  
 메서드는 UI반환 계약에 의해 정의되어야 하며 반환 값은 형식이어야 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 이는 다음 코드에서 `GetAddInUI` `IWPFAddInContract` 계약의 메서드에 의해 입증됩니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>추가 기능 뷰 파이프라인 세그먼트 구현  
 추가 기능이 하위 클래스로 <xref:System.Windows.FrameworkElement>제공하는 UI를 구현하기 때문에 추가 기능 뷰에서 메서드는 `IWPFAddInView.GetAddInUI` 형식 <xref:System.Windows.FrameworkElement>값을 반환해야 합니다. 다음 코드에서는 인터페이스로 구현된 계약의 추가 기능 뷰를 보여 줍니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>추가 기능 쪽 어댑터 파이프라인 세그먼트 구현  
 계약 메서드는 <xref:System.AddIn.Contract.INativeHandleContract>을 반환하지만 추가 기능 <xref:System.Windows.FrameworkElement> (추가 기능 뷰에서 지정 한 대로)을 반환합니다. 따라서 격리 <xref:System.Windows.FrameworkElement> 경계를 <xref:System.AddIn.Contract.INativeHandleContract> 교차하기 전에 변환해야 합니다. 이 작업은 다음 코드와 같이 호출하여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>추가 인 사이드 어댑터에 의해 수행됩니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>호스트 뷰 파이프라인 세그먼트 구현  
 호스트 응용 프로그램에는 <xref:System.Windows.FrameworkElement>와 상관 관계가 있는 메서드가 호스트 `IWPFAddInHostView.GetAddInUI` <xref:System.Windows.FrameworkElement>뷰에 대해 형식 값을 반환해야 합니다. 다음 코드에서는 인터페이스로 구현된 계약의 호스트 뷰를 보여 줍니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>호스트 측 어댑터 파이프라인 세그먼트 구현  
 계약 메서드는 <xref:System.AddIn.Contract.INativeHandleContract>을 반환하지만 호스트 응용 <xref:System.Windows.FrameworkElement> 프로그램은 (호스트 뷰에서 지정한 대로) 기대합니다. 따라서 격리 <xref:System.AddIn.Contract.INativeHandleContract> 경계를 교차한 후 <xref:System.Windows.FrameworkElement> a로 변환해야 합니다. 이 작업은 다음 코드와 같이 호출하여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>호스트 측 어댑터에 의해 수행됩니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>추가 기능 구현  
 추가 기능 어댑터 및 추가 기능 뷰가 생성되면 추가`WPFAddIn1.AddIn`기능()은 `IWPFAddInView.GetAddInUI` <xref:System.Windows.FrameworkElement> 개체를 반환하는 <xref:System.Windows.Controls.UserControl> 메서드를 구현해야 합니다(이 예제에서는). 의 <xref:System.Windows.Controls.UserControl> `AddInUI`구현은 다음 코드로 표시됩니다.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 `IWPFAddInView.GetAddInUI` 추가 기능의 구현은 다음 코드에서 볼 수 `AddInUI`있는 대로 의 새 인스턴스를 반환하기만 하면 됩니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a>호스트 애플리케이션 구현  
 호스트 측 어댑터 및 호스트 뷰를 만든 호스트 응용 프로그램은 .NET Framework 추가 기능 모델을 사용하여 파이프라인을 열고 추가 `IWPFAddInHostView.GetAddInUI` 기능의 호스트 뷰를 획득하고 메서드를 호출할 수 있습니다. 이러한 단계는 다음 코드에 나와 있습니다.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>참고 항목

- [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [WPF 추가 기능 개요](wpf-add-ins-overview.md)
