---
title: '방법: UI인 추가 기능 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 0464d87aef3d4e88d9340af2ac1db93c13ba26e2
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592653"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>방법: UI인 추가 기능 만들기
이 예제에서는 WPF 독립 실행형 응용 프로그램에서 호스팅되는 Windows Presentation Foundation (WPF)는 추가 기능을 만드는 방법을 보여 줍니다.  
  
 추가 UI는 WPF 사용자 컨트롤입니다. 이 사용자 정의 컨트롤의 콘텐츠는 클릭했을 때 메시지 상자를 표시하는 하나의 단추입니다. WPF 독립 실행형 응용 프로그램은 주 응용 프로그램 창의 콘텐츠로 추가 UI를 호스팅합니다.  
  
 **필수 조건**  
  
 이 예제는이 시나리오를 사용 하도록 설정 하는.NET Framework 추가 기능 모델에 WPF 확장을 강조 표시 하 고 다음을 가정 합니다.  
  
- .NET Framework 추가 기능에서 모델, 파이프라인, 추가 기능 및 호스트 개발을 포함 하 여 알고 있어야 합니다. 이러한 개념을 잘 모르는 경우 [추가 기능 및 확장성](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))합니다. 파이프라인, 추가 기능 및 호스트 응용 프로그램의 구현을 설명 하는 자습서를 참조 하세요. [연습: 확장 가능한 응용 프로그램을 만드는](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))합니다.  
  
- WPF 확장명.NET Framework 추가 기능 모델을 알고 있어야 합니다. 참조 [WPF 추가 기능 개요](wpf-add-ins-overview.md)합니다.  
  
## <a name="example"></a>예제  
 WPF UI 인 추가 기능을 만드는 각 파이프라인 세그먼트에 추가 하 고 호스트 응용 프로그램에 대 한 특정 코드가 필요 합니다.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>계약 파이프라인 세그먼트 구현  
 추가 기능에 대 한 계약 구현 해야 경우의 추가 기능 UI <xref:System.AddIn.Contract.INativeHandleContract>합니다. 예에서 `IWPFAddInContract` 구현 <xref:System.AddIn.Contract.INativeHandleContract>다음 코드에 표시 된 것 처럼 합니다.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>추가 기능 뷰 파이프라인 세그먼트 구현  
 추가 기능에서 서브 클래스로 구현 되기 때문에 합니다 <xref:System.Windows.FrameworkElement> 형식에는 추가 기능 뷰 서브 클래스 해야 <xref:System.Windows.FrameworkElement>합니다. 다음 코드에서는로 구현 된 계약의 추가 기능 뷰는 `WPFAddInView` 클래스입니다.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 추가 기능 뷰에서 파생 되는 여기서 <xref:System.Windows.Controls.UserControl>합니다. 따라서 추가 UI에서 파생도 되어야 <xref:System.Windows.Controls.UserControl>합니다.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>추가 기능 쪽 어댑터 파이프라인 세그먼트 구현  
 계약은 <xref:System.AddIn.Contract.INativeHandleContract>, 추가 되는 <xref:System.Windows.FrameworkElement> (추가 기능 뷰 파이프라인 세그먼트로 지정 된 대로). 따라서 합니다 <xref:System.Windows.FrameworkElement> 으로 변환 되어야 합니다는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 하기 전에 합니다. 추가 기능 쪽 어댑터에서 호출 하 여이 작업은 수행 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>다음 코드에 표시 된 것 처럼 합니다.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 모델 추가에서의 추가 기능 UI를 반환 합니다 (참조 [UI는 추가 기능에서 반환 하는 만들기](how-to-create-an-add-in-that-returns-a-ui.md)), 추가 기능 어댑터 변환 합니다 <xref:System.Windows.FrameworkElement> 에 <xref:System.AddIn.Contract.INativeHandleContract> 호출 하 여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 도 호출 해야이 모델에서는 호출 하도록 코드를 작성 하는 메서드를 구현 해야 합니다. 재정의 하 여이 작업을 수행 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 를 호출 하는 코드를 구현 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 경우 호출 하는 코드 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 예상 하는 <xref:System.AddIn.Contract.INativeHandleContract>합니다. 이 경우 호출자가 호스트 쪽 어댑터가 됩니다. 이에 대해서는 이후의 하위 단원에서 설명합니다.  
  
> [!NOTE]
>  재정의 해야 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 호스트 응용 프로그램 UI 간 탭 이동 사용 및 UI 추가 기능에서이 모델에 있습니다. 자세한 내용은 "WPF 추가 기능에 제한 사항"를 참조 하세요 [WPF 추가 기능 개요](wpf-add-ins-overview.md)합니다.  
  
 추가 기능 쪽 어댑터에서 파생 되는 인터페이스를 구현 하므로 <xref:System.AddIn.Contract.INativeHandleContract>를 구현 해야 <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>이지만이 무시 됩니다 때 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 재정의 됩니다.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>호스트 뷰 파이프라인 세그먼트 구현  
 이 모델에서는 호스트 응용 프로그램이 일반적으로 호스트 뷰가 되도록는 <xref:System.Windows.FrameworkElement> 하위 클래스입니다. 호스트 쪽 어댑터 변환 해야 합니다는 <xref:System.AddIn.Contract.INativeHandleContract> 에 <xref:System.Windows.FrameworkElement> 후는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 통과 합니다. 호스트 응용 프로그램 가져오기 메서드를 호출 하지 때문에 합니다 <xref:System.Windows.FrameworkElement>, [호스트] 보기 해야 "return"는 <xref:System.Windows.FrameworkElement> 포함 하 여 합니다. [호스트] 보기의 서브 클래스에서 파생 되어야 합니다는 결과적으로 <xref:System.Windows.FrameworkElement> 기타를 포함할 수 있는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]와 같은 <xref:System.Windows.Controls.UserControl>합니다. 로 구현 된 계약의 호스트 뷰를 표시 하는 다음 코드는 `WPFAddInHostView` 클래스입니다.  

<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>호스트 측 어댑터 파이프라인 세그먼트 구현  
 계약은 <xref:System.AddIn.Contract.INativeHandleContract>, 호스트 응용 프로그램에서 예상을 <xref:System.Windows.Controls.UserControl> (호스트 뷰로 지정 된 대로). 결과적으로 <xref:System.AddIn.Contract.INativeHandleContract> 으로 변환 되어야 합니다는 <xref:System.Windows.FrameworkElement> 호스트 뷰의 콘텐츠로 설정 하기 전에 격리 경계를 통과 한 후 (에서 파생 되는 <xref:System.Windows.Controls.UserControl>).  
  
 다음 코드와 같이 이 작업은 호스트 쪽 어댑터로 수행됩니다.  

 알 수 있듯이 호스트 쪽 어댑터 획득를 <xref:System.AddIn.Contract.INativeHandleContract> 추가 기능 쪽 어댑터를 호출 하 여 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 메서드 (이것이 여기서는 <xref:System.AddIn.Contract.INativeHandleContract> 격리 경계를 벗어날).  
  
 호스트 쪽 어댑터가 다음 변환 합니다 <xref:System.AddIn.Contract.INativeHandleContract> 에 <xref:System.Windows.FrameworkElement> 호출 하 여 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>입니다. 마지막으로 <xref:System.Windows.FrameworkElement> 호스트 뷰의 콘텐츠로 설정 됩니다.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>추가 기능 구현  
 추가 기능 쪽 어댑터와 추가 기능 뷰를 배치했으면 다음 코드와 같이 추가 기능 뷰에서 파생시켜 추가 기능을 구현할 수 있습니다.  

 이 예제에서는이 모델의 한 가지 흥미로운 이점을 볼 수 있습니다: 추가 기능 개발자는 추가 기능 (이므로 UI) 보다는 모두 추가 기능 클래스 및 추가 UI를 구현 해야 합니다.  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>호스트 애플리케이션 구현  
 호스트 쪽 어댑터와 호스트 뷰가 만들어지면 호스트 응용 프로그램 파이프라인을 열고 추가 기능의 호스트 뷰를 가져오고.NET Framework 추가 기능 모델을 사용할 수 있습니다. 이러한 단계는 다음 코드에 나와 있습니다.  

 호스트 응용 프로그램을 활성화 하는 추가-암시적으로 호스트 응용 프로그램 호스트 뷰를 반환 하는 일반적인.NET Framework 추가 기능 모델 코드를 사용 합니다. 호스트 응용 프로그램에는 이후에 호스트 뷰가 표시 됩니다 (되는 <xref:System.Windows.Controls.UserControl>)에서 <xref:System.Windows.Controls.Grid>합니다.  
  
 추가 UI와의 상호 작용을 처리 하기 위한 코드는 추가 기능의 응용 프로그램 도메인에서 실행 됩니다. 이러한 상호 작용에는 다음이 포함됩니다.  
  
- 처리를 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
- 표시 된 <xref:System.Windows.MessageBox>합니다.  
  
 이 작업은 호스트 애플리케이션에서 완전히 격리됩니다.  
  
## <a name="see-also"></a>참고자료

- [추가 기능 및 확장성](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [WPF 추가 기능 개요](wpf-add-ins-overview.md)
