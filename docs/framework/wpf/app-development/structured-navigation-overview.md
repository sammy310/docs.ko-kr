---
title: 구조적 탐색 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: 0cf2a37eaa812d27dc3d111b1459c9daae72dc5a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320073"
---
# <a name="structured-navigation-overview"></a>구조적 탐색 개요
호스팅될 수 있는 콘텐츠를 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame>, 또는 <xref:System.Windows.Navigation.NavigationWindow> 팩에서 식별할 수 있는 페이지로 구성 됩니다 [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] 하이퍼링크 탐색 하 고 있습니다. 하이퍼링크를 통해 정의되는 페이지 및 페이지 탐색 방법의 구조를 탐색 토폴로지라고 합니다. 이 토폴로지는 다양한 애플리케이션 형식, 특히 문서를 탐색하는 애플리케이션에 적합합니다. 해당 애플리케이션의 경우 한쪽 페이지가 다른 페이지에 대해 아무것도 알 필요 없이 사용자가 페이지 사이에서 이동할 수 있습니다.  
  
 하지만 다른 유형의 애플리케이션 형식에는 페이지를 탐색할 때 알아야 하는 페이지가 있습니다. 예를 들어 조직의 모든 직원을 나열하는 하나의 "직원 목록" 페이지가 있는 인사 관리 애플리케이션을 살펴보겠습니다. 이 페이지에서 사용자는 하이퍼링크를 클릭하여 새 직원을 추가할 수 있습니다. 클릭되면 페이지가 "직원 추가" 페이지로 이동하여 새 직원의 세부 정보를 수집하고 이를 "직원 목록" 페이지로 반환하여 새 직원을 만들고 목록을 업데이트합니다. 이 탐색 스타일은 처리를 수행하고 값을 반환하는 구조적 프로그래밍이라고 알려진 메서드 호출과 비슷합니다. 마찬가지로 이 탐색 스타일을 *구조적 탐색*이라고 합니다.  
  
 <xref:System.Windows.Controls.Page> 클래스에는 구조적된 탐색에 대 한 지원을 구현 하지 않습니다. 대신 합니다 <xref:System.Windows.Navigation.PageFunction%601> 클래스에서 파생 되며 <xref:System.Windows.Controls.Page> 구조적된 탐색에 필요한 기본 생성자를 사용 하 여 확장 하 고 있습니다. 이 항목에서는 구조적된 탐색에 사용 하 여 설정 하는 방법을 보여 줍니다. <xref:System.Windows.Navigation.PageFunction%601>합니다.  

<a name="Structured_Navigation"></a>   
## <a name="structured-navigation"></a>구조적 탐색  
 구조적 탐색에서 한 페이지가 다른 페이지를 호출하면 다음 동작의 일부 또는 전체가 필요합니다.  
  
-   호출 페이지는 호출된 페이지로 이동하고 필요한 경우 호출된 페이지에 필요한 매개 변수를 전달합니다.  
  
-   사용자가 호출 페이지 사용을 마치면 호출된 페이지는 필요한 경우 특별히 호출 페이지로 돌아갑니다.  
  
    -   호출 페이지가 완료된 방식을 설명하는 상태 정보 반환(예: 사용자가 [확인] 단추나 [취소] 단추를 눌렀는지 여부).  
  
    -   사용자로부터 수집된 데이터 반환(예: 새 직원 세부 정보).  
  
-   호출 페이지가 호출된 페이지로 돌아가면 호출된 페이지 인스턴스를 다른 인스턴스와 격리하기 위해 호출된 페이지가 탐색 기록에서 제거됩니다.  
  
 다음 그림에서는 이러한 동작을 설명 합니다.  
  
 ![스크린 샷 호출 페이지와 호출된 된 페이지 사이의 흐름을 보여 줍니다.](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)  
  
 사용 하 여 이러한 동작을 구현할 수는 <xref:System.Windows.Navigation.PageFunction%601> 호출된 페이지와 합니다.  
  
<a name="Structured_Navigation_with_PageFunction"></a>   
## <a name="structured-navigation-with-pagefunction"></a>PageFunction을 사용한 구조적 탐색  
 이 항목에서는 단일 구조적된 탐색의 기본 메커니즘을 구현 하는 방법을 보여 줍니다. <xref:System.Windows.Navigation.PageFunction%601>합니다. 이 샘플에서는 <xref:System.Windows.Controls.Page> 호출을 <xref:System.Windows.Navigation.PageFunction%601> 가져오려는 <xref:System.String> 사용자 로부터 값을 반환 합니다.  
  
### <a name="creating-a-calling-page"></a>호출 페이지 만들기  
 호출 하는 페이지는 <xref:System.Windows.Navigation.PageFunction%601> 일 수를 <xref:System.Windows.Controls.Page> 또는 <xref:System.Windows.Navigation.PageFunction%601>합니다. 이 예제는 <xref:System.Windows.Controls.Page>다음 코드에 표시 된 것 처럼 합니다.  
  
 [!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]  
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]  
  
 [!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
 [!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]  
  
### <a name="creating-a-page-function-to-call"></a>호출할 페이지 함수 만들기  
 호출 페이지는 호출된 페이지를 사용 하 여 수집 하 고 사용자 로부터 데이터를 반환할 수 있으므로 <xref:System.Windows.Navigation.PageFunction%601> 형식 인수로 호출된 페이지로 반환 하는 값의 형식을 지정 하는 제네릭 클래스로 구현 됩니다. 다음 코드는 호출의 초기 구현을 보여 줍니다. 페이지를 사용 하는 <xref:System.Windows.Navigation.PageFunction%601>를 반환 하는 <xref:System.String>합니다.  
  
 [!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]  
  
 [!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
 [!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]  
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]  
  
 선언의 <xref:System.Windows.Navigation.PageFunction%601> 선언과 비슷합니다는 <xref:System.Windows.Controls.Page> 형식 인수를 추가 합니다. 코드 예제에서 확인할 수 있는 것처럼 형식 인수는 `x:TypeArguments` 특성을 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에서 지정되고 표준 제네릭 형식 인수 구문을 사용하여 코드 숨김에서 지정됩니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 클래스만 형식 인수로 사용할 필요는 없습니다. <xref:System.Windows.Navigation.PageFunction%601> 사용자 지정 형식으로 추상화 되는 도메인 별로 데이터를 수집 하도록 호출할 수 있습니다. 다음 코드에 사용자 지정 형식에 대 한 형식 인수로 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Navigation.PageFunction%601>합니다.  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]  
  
 [!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]  
[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind2)]  
  
 형식 인수는 <xref:System.Windows.Navigation.PageFunction%601> 다음 섹션에서 설명 하는 호출 페이지와 호출된 된 페이지 간 통신에 대 한 기초를 제공 합니다.  
  
 알 수 있듯이, 선언을 통해 식별 되는 형식을 <xref:System.Windows.Navigation.PageFunction%601> 에서 데이터를 반환할 때의 중요 한 역할을 <xref:System.Windows.Navigation.PageFunction%601> 호출 페이지로 합니다.  
  
### <a name="calling-a-pagefunction-and-passing-parameters"></a>PageFunction 호출 및 매개 변수 전달  
 페이지를 호출 하려면 호출 페이지 호출된 된 페이지를 인스턴스화하고 하며 사용 하 여 이동 된 <xref:System.Windows.Navigation.NavigationService.Navigate%2A> 메서드. 이렇게 하면 호출 페이지가 호출된 페이지에서 수집되는 데이터의 기본값과 같은 초기 데이터를 호출된 페이지에 전달할 수 있습니다.  
  
 다음 코드에서는 기본값이 아닌 생성자를 사용하여 호출 페이지에서 매개 변수를 허용하는 호출된 페이지를 보여 줍니다.  
  
 [!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
 [!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]  
  
 다음 코드는 호출 페이지 처리를 보여 줍니다.는 <xref:System.Windows.Documents.Hyperlink.Click> 의 이벤트를 <xref:System.Windows.Documents.Hyperlink> 호출된 된 페이지를 인스턴스화하고 초기 문자열 값을 전달 합니다.  
  
 [!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]  
  
 매개 변수를 호출된 페이지로 전달할 필요는 없습니다. 대신에 다음을 수행할 수 있습니다.  
  
-   호출 페이지에서:  
  
    1.  호출 된 인스턴스화할 <xref:System.Windows.Navigation.PageFunction%601> 기본 생성자를 사용 하 여 합니다.  
  
    2.  매개 변수를 저장할 <xref:System.Windows.Application.Properties%2A>합니다.  
  
    3.  호출 된 이동할 <xref:System.Windows.Navigation.PageFunction%601>합니다.  
  
-   호출 된 <xref:System.Windows.Navigation.PageFunction%601>:  
  
    -   에 저장 된 매개 변수를 사용 하 여 검색 <xref:System.Windows.Application.Properties%2A>합니다.  
  
 그러나 간단히 살펴보겠지만 호출된 페이지에서 반환된 데이터를 수집하려고 호출된 페이지를 인스턴스화하고 여기로 이동하는 데는 코드를 사용해야 합니다. 이러한 이유로 <xref:System.Windows.Navigation.PageFunction%601> 이동할이 고 그렇지 않으면 활성 상태로 유지 해야, 다음에 <xref:System.Windows.Navigation.PageFunction%601>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 인스턴스화하는 <xref:System.Windows.Navigation.PageFunction%601> 기본 생성자를 사용 하 여.  
  
 하지만 호출된 페이지는 호출 페이지에서 검색될 수 있는 데이터를 반환해야 합니다.  
  
### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>작업에서 호출 페이지로 작업 결과 및 작업 데이터 반환  
 사용자가 [확인] 또는 [취소] 단추를 눌러 이 예제에서 보여 준 호출된 페이지 사용을 마치면 호출된 페이지가 반환해야 합니다. 호출 페이지는 호출된 페이지를 사용하여 사용자로부터 데이터를 수집했으므로 호출 페이지에는 두 가지 정보가 필요합니다.  
  
1. 사용자가 호출된 페이지를 취소했는지 여부(이 예제에서 [확인] 또는 [취소] 단추를 눌러). 이 경우 호출 페이지는 호출 페이지가 사용자로부터 수집한 데이터를 처리할지 결정할 수 있습니다.  
  
2. 사용자가 제공한 데이터.  
  
 정보를 반환할 <xref:System.Windows.Navigation.PageFunction%601> 구현 된 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 메서드. 다음 코드에서는 메서드를 호출하는 방법을 보여 줍니다.  
  
 [!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
 [!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]  
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]  
  
 이 예제에서 사용자가 [취소] 단추를 누르면 `null` 값이 호출 페이지로 반환됩니다. [확인] 단추를 누르면 사용자가 제공한 문자열 값이 반환됩니다. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 가 `protected virtual` 호출 페이지로 데이터를 반환 하기 위해 호출 하는 메서드입니다. 데이터를 제네릭 인스턴스의 패키지 해야 <xref:System.Windows.Navigation.ReturnEventArgs%601> 형식, 해당 형식 인수 유형을 지정 하는 값 <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> 반환 합니다. 이러한 방식으로 선언 하는 경우는 <xref:System.Windows.Navigation.PageFunction%601> 특정 형식 인수를 사용 하는 나타낼 수 있습니다는 <xref:System.Windows.Navigation.PageFunction%601> 형식 인수에 의해 지정 된 형식의 인스턴스를 반환 합니다. 이 예제에서 형식 인수 및 반환 값은 결과적으로 형식의 <xref:System.String>합니다.  
  
 때 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 가 호출의 반환 값을 받을 방법이 호출 페이지 요구는 <xref:System.Windows.Navigation.PageFunction%601>합니다. 이러한 이유로 <xref:System.Windows.Navigation.PageFunction%601> 구현를 <xref:System.Windows.Navigation.PageFunction%601.Return> 이벤트를 처리 하는 페이지를 호출 합니다. 때 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 가 호출 <xref:System.Windows.Navigation.PageFunction%601.Return> 이 발생 하면 호출 페이지를 등록할 수 있도록 <xref:System.Windows.Navigation.PageFunction%601.Return> 알림을 받아야 하 합니다.  
  
 [!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
 [!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]  
  
### <a name="removing-task-pages-when-a-task-completes"></a>작업이 완료될 때 작업 페이지 제거  
 호출된 페이지가 반환하고 사용자가 호출된 페이지를 취소하면 호출 페이지는 사용자가 제공한 데이터와 호출된 페이지에서 반환된 데이터를 처리합니다. 이 방법으로 데이터를 취득하는 것은 격리된 활동입니다. 호출된 페이지가 반환할 경우 호출 페이지는 추가 데이터를 캡처하기 위해 새 호출 페이지를 만들고 여기로 이동해야 합니다.  
  
 하지만 호출된 페이지가 업무 일지에서 제거되지 않는 한 사용자는 호출 페이지의 이전 인스턴스로 돌아갈 수 있습니다. 여부를 <xref:System.Windows.Navigation.PageFunction%601> 에 보존 되는 저널에 의해 결정 됩니다는 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 속성입니다. 기본적으로 페이지 함수는 자동으로 제거 될 때 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 되므로 이라고 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 로 설정 된 `true`합니다. 페이지 함수 후 탐색 기록에 유지할 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 가 호출 설정 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 를 `false`합니다.  
  
<a name="Other_Types_of_Structured_Navigation"></a>   
## <a name="other-types-of-structured-navigation"></a>기타 구조적 탐색 유형  
 이 항목에서는 가장 기본적인 사용을 <xref:System.Windows.Navigation.PageFunction%601> 구조적 탐색 호출/반환을 지원 하도록 합니다. 이 기본 사항은 더 복잡한 구조적 탐색을 만들 수 있는 기능을 제공합니다.  
  
 예를 들어 사용자로부터 충분한 데이터를 수집하거나 작업을 수행하기 위해 호출 페이지에 여러 페이지가 필요한 경우가 있습니다. 여러 페이지를 사용하는 것을 "마법사"라고 합니다.  
  
 다른 경우에는 구조적 탐색을 기반으로 효과적으로 작동하는 복잡한 탐색 토폴로지가 애플리케이션에 포함될 수 있습니다. 자세한 내용은 [탐색 토폴로지 개요](navigation-topologies-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [탐색 토폴로지 개요](navigation-topologies-overview.md)
