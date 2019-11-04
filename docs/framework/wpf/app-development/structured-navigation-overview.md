---
title: 구조적 탐색 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: 09c3c57f3ac1009416a5c67b37c035fe30cd5b5e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425336"
---
# <a name="structured-navigation-overview"></a>구조적 탐색 개요

XBAP (XAML 브라우저 응용 프로그램), <xref:System.Windows.Controls.Frame>또는 <xref:System.Windows.Navigation.NavigationWindow>에서 호스팅할 수 있는 콘텐츠는 pack Uri (uniform resource identifier)로 식별 되 고 하이퍼링크로 탐색할 수 있는 페이지로 구성 됩니다. 하이퍼링크를 통해 정의되는 페이지 및 페이지 탐색 방법의 구조를 탐색 토폴로지라고 합니다. 이 토폴로지는 다양한 애플리케이션 형식, 특히 문서를 탐색하는 애플리케이션에 적합합니다. 해당 애플리케이션의 경우 한쪽 페이지가 다른 페이지에 대해 아무것도 알 필요 없이 사용자가 페이지 사이에서 이동할 수 있습니다.

하지만 다른 유형의 애플리케이션 형식에는 페이지를 탐색할 때 알아야 하는 페이지가 있습니다. 예를 들어 조직의 모든 직원을 나열하는 하나의 "직원 목록" 페이지가 있는 인사 관리 애플리케이션을 살펴보겠습니다. 이 페이지에서 사용자는 하이퍼링크를 클릭하여 새 직원을 추가할 수 있습니다. 클릭되면 페이지가 "직원 추가" 페이지로 이동하여 새 직원의 세부 정보를 수집하고 이를 "직원 목록" 페이지로 반환하여 새 직원을 만들고 목록을 업데이트합니다. 이 탐색 스타일은 처리를 수행하고 값을 반환하는 구조적 프로그래밍이라고 알려진 메서드 호출과 비슷합니다. 마찬가지로 이 탐색 스타일을 *구조적 탐색*이라고 합니다.

<xref:System.Windows.Controls.Page> 클래스는 구조적 탐색에 대 한 지원을 구현 하지 않습니다. 대신 <xref:System.Windows.Navigation.PageFunction%601> 클래스가 <xref:System.Windows.Controls.Page>에서 파생 되 고 구조적 탐색에 필요한 기본 구문으로 확장 됩니다. 이 항목에서는 <xref:System.Windows.Navigation.PageFunction%601>를 사용 하 여 구조적 탐색을 설정 하는 방법을 보여 줍니다.

<a name="Structured_Navigation"></a>

## <a name="structured-navigation"></a>구조적 탐색

구조적 탐색에서 한 페이지가 다른 페이지를 호출하면 다음 동작의 일부 또는 전체가 필요합니다.

- 호출 페이지는 호출된 페이지로 이동하고 필요한 경우 호출된 페이지에 필요한 매개 변수를 전달합니다.

- 사용자가 호출 페이지 사용을 마치면 호출된 페이지는 필요한 경우 특별히 호출 페이지로 돌아갑니다.

  - 호출 페이지가 완료된 방식을 설명하는 상태 정보 반환(예: 사용자가 [확인] 단추나 [취소] 단추를 눌렀는지 여부).

  - 사용자로부터 수집된 데이터 반환(예: 새 직원 세부 정보).

- 호출 페이지가 호출된 페이지로 돌아가면 호출된 페이지 인스턴스를 다른 인스턴스와 격리하기 위해 호출된 페이지가 탐색 기록에서 제거됩니다.

이러한 동작은 다음 그림에 나와 있습니다.

![호출 페이지와 호출 된 페이지 사이의 흐름을 보여 주는 스크린샷](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)

호출 된 페이지로 <xref:System.Windows.Navigation.PageFunction%601>를 사용 하 여 이러한 동작을 구현할 수 있습니다.

<a name="Structured_Navigation_with_PageFunction"></a>

## <a name="structured-navigation-with-pagefunction"></a>PageFunction을 사용한 구조적 탐색

이 항목에서는 단일 <xref:System.Windows.Navigation.PageFunction%601>와 관련 된 구조적 탐색의 기본 메커니즘을 구현 하는 방법을 보여 줍니다. 이 샘플에서 <xref:System.Windows.Controls.Page>은 <xref:System.Windows.Navigation.PageFunction%601>를 호출 하 여 사용자 로부터 <xref:System.String> 값을 가져오고 반환 합니다.

### <a name="creating-a-calling-page"></a>호출 페이지 만들기

<xref:System.Windows.Navigation.PageFunction%601>를 호출 하는 페이지는 <xref:System.Windows.Controls.Page> 또는 <xref:System.Windows.Navigation.PageFunction%601>수 있습니다. 이 예제에서는 다음 코드와 같이 <xref:System.Windows.Controls.Page>입니다.

[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]

[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]

### <a name="creating-a-page-function-to-call"></a>호출할 페이지 함수 만들기

호출 페이지는 호출 된 페이지를 사용 하 여 사용자 로부터 데이터를 수집 하 고 반환할 수 있으므로 <xref:System.Windows.Navigation.PageFunction%601>는 호출 된 페이지에서 반환할 값의 형식을 지정 하는 제네릭 클래스로 구현 됩니다. 다음 코드에서는 <xref:System.String>을 반환 하는 <xref:System.Windows.Navigation.PageFunction%601>을 사용 하 여 호출 된 페이지의 초기 구현을 보여 줍니다.

[!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]

[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]

<xref:System.Windows.Navigation.PageFunction%601> 선언은 형식 인수를 추가 하 여 <xref:System.Windows.Controls.Page> 선언과 비슷합니다. 코드 예제에서 확인할 수 있는 것처럼 형식 인수는 `x:TypeArguments` 특성을 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에서 지정되고 표준 제네릭 형식 인수 구문을 사용하여 코드 숨김에서 지정됩니다.

.NET Framework 클래스만 형식 인수로 사용할 필요는 없습니다. <xref:System.Windows.Navigation.PageFunction%601>를 호출 하 여 사용자 지정 형식으로 추상화 된 도메인 관련 데이터를 수집할 수 있습니다. 다음 코드에서는 사용자 지정 형식을 <xref:System.Windows.Navigation.PageFunction%601>의 형식 인수로 사용 하는 방법을 보여 줍니다.

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

<xref:System.Windows.Navigation.PageFunction%601>에 대 한 형식 인수는 호출 페이지와 호출 된 페이지 간의 통신에 대 한 기초를 제공 합니다 .이에 대해서는 다음 섹션에서 설명 합니다.

여기에서 볼 수 있듯이 <xref:System.Windows.Navigation.PageFunction%601>의 선언으로 식별 되는 형식은 <xref:System.Windows.Navigation.PageFunction%601>에서 호출 페이지로 데이터를 반환 하는 데 중요 한 역할을 합니다.

### <a name="calling-a-pagefunction-and-passing-parameters"></a>PageFunction 호출 및 매개 변수 전달

페이지를 호출 하려면 호출 하는 페이지가 호출 된 페이지를 인스턴스화하고 <xref:System.Windows.Navigation.NavigationService.Navigate%2A> 메서드를 사용 하 여 이동 해야 합니다. 이렇게 하면 호출 페이지가 호출된 페이지에서 수집되는 데이터의 기본값과 같은 초기 데이터를 호출된 페이지에 전달할 수 있습니다.

다음 코드에서는 호출 하는 페이지에서 매개 변수를 허용 하는 매개 변수가 없는 생성자가 포함 된 호출 된 페이지를 보여 줍니다.

[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]

다음 코드에서는 호출 된 페이지를 인스턴스화하고 초기 문자열 값을 전달 하는 <xref:System.Windows.Documents.Hyperlink>의 <xref:System.Windows.Documents.Hyperlink.Click> 이벤트를 처리 하는 호출 페이지를 보여 줍니다.

[!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]

매개 변수를 호출된 페이지로 전달할 필요는 없습니다. 대신에 다음을 수행할 수 있습니다.

- 호출 페이지에서:

  1. 매개 변수가 없는 생성자를 사용 하 여 호출 된 <xref:System.Windows.Navigation.PageFunction%601>를 인스턴스화합니다.

  2. <xref:System.Windows.Application.Properties%2A>에 매개 변수를 저장 합니다.

  3. 호출 된 <xref:System.Windows.Navigation.PageFunction%601>로 이동 합니다.

- 호출 된 <xref:System.Windows.Navigation.PageFunction%601>에서:

  - <xref:System.Windows.Application.Properties%2A>에 저장 된 매개 변수를 검색 하 고 사용 합니다.

그러나 간단히 살펴보겠지만 호출된 페이지에서 반환된 데이터를 수집하려고 호출된 페이지를 인스턴스화하고 여기로 이동하는 데는 코드를 사용해야 합니다. 이러한 이유로 <xref:System.Windows.Navigation.PageFunction%601>을 활성 상태로 유지 해야 합니다. 그렇지 않으면 다음에 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Navigation.PageFunction%601>으로 이동할 때 매개 변수가 없는 생성자를 사용 하 여 <xref:System.Windows.Navigation.PageFunction%601>를 인스턴스화합니다.

하지만 호출된 페이지는 호출 페이지에서 검색될 수 있는 데이터를 반환해야 합니다.

### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>작업에서 호출 페이지로 작업 결과 및 작업 데이터 반환

사용자가 [확인] 또는 [취소] 단추를 눌러 이 예제에서 보여 준 호출된 페이지 사용을 마치면 호출된 페이지가 반환해야 합니다. 호출 페이지는 호출된 페이지를 사용하여 사용자로부터 데이터를 수집했으므로 호출 페이지에는 두 가지 정보가 필요합니다.

1. 사용자가 호출된 페이지를 취소했는지 여부(이 예제에서 [확인] 또는 [취소] 단추를 눌러). 이 경우 호출 페이지는 호출 페이지가 사용자로부터 수집한 데이터를 처리할지 결정할 수 있습니다.

2. 사용자가 제공한 데이터.

정보를 반환 하기 위해 <xref:System.Windows.Navigation.PageFunction%601>는 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 메서드를 구현 합니다. 다음 코드에서는 메서드를 호출하는 방법을 보여 줍니다.

[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]

이 예제에서 사용자가 [취소] 단추를 누르면 `null` 값이 호출 페이지로 반환됩니다. [확인] 단추를 누르면 사용자가 제공한 문자열 값이 반환됩니다. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>은 호출 페이지로 데이터를 반환 하기 위해 호출 하는 `protected virtual` 메서드입니다. 데이터는 제네릭 <xref:System.Windows.Navigation.ReturnEventArgs%601> 형식의 인스턴스에 패키지 되어야 합니다. 형식 인수는 <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> 반환 하는 값의 형식을 지정 합니다. 이러한 방식으로 특정 형식 인수를 사용 하 여 <xref:System.Windows.Navigation.PageFunction%601>을 선언 하면 <xref:System.Windows.Navigation.PageFunction%601>는 형식 인수에 지정 된 형식의 인스턴스를 반환 합니다. 이 예제에서 형식 인수 및 따라서 반환 값은 <xref:System.String> 형식입니다.

<xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>를 호출 하면 호출 페이지에서 <xref:System.Windows.Navigation.PageFunction%601>의 반환 값을 받는 방법이 필요 합니다. 따라서 <xref:System.Windows.Navigation.PageFunction%601>에서 처리할 페이지를 호출 하는 <xref:System.Windows.Navigation.PageFunction%601.Return> 이벤트를 구현 합니다. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>를 호출 하면 <xref:System.Windows.Navigation.PageFunction%601.Return> 발생 하므로 호출 하는 페이지가 <xref:System.Windows.Navigation.PageFunction%601.Return>에 등록 하 여 알림을 받을 수 있습니다.

[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]

### <a name="removing-task-pages-when-a-task-completes"></a>작업이 완료될 때 작업 페이지 제거

호출된 페이지가 반환하고 사용자가 호출된 페이지를 취소하면 호출 페이지는 사용자가 제공한 데이터와 호출된 페이지에서 반환된 데이터를 처리합니다. 이 방법으로 데이터를 취득하는 것은 격리된 활동입니다. 호출된 페이지가 반환할 경우 호출 페이지는 추가 데이터를 캡처하기 위해 새 호출 페이지를 만들고 여기로 이동해야 합니다.

하지만 호출된 페이지가 업무 일지에서 제거되지 않는 한 사용자는 호출 페이지의 이전 인스턴스로 돌아갈 수 있습니다. 저널에 <xref:System.Windows.Navigation.PageFunction%601> 유지 되는지 여부는 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 속성에 따라 결정 됩니다. 기본적으로 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A>를 `true`로 설정 했기 때문에 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>가 호출 되 면 페이지 함수가 자동으로 제거 됩니다. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>를 호출한 후에 탐색 기록에 페이지 함수를 유지 하려면 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A>를 `false`로 설정 합니다.

<a name="Other_Types_of_Structured_Navigation"></a>

## <a name="other-types-of-structured-navigation"></a>기타 구조적 탐색 유형

이 항목에서는 호출/반환 구조적 탐색을 지 원하는 <xref:System.Windows.Navigation.PageFunction%601>의 가장 기본적인 사용 방법을 보여 줍니다. 이 기본 사항은 더 복잡한 구조적 탐색을 만들 수 있는 기능을 제공합니다.

예를 들어 사용자로부터 충분한 데이터를 수집하거나 작업을 수행하기 위해 호출 페이지에 여러 페이지가 필요한 경우가 있습니다. 여러 페이지를 사용하는 것을 "마법사"라고 합니다.

다른 경우에는 구조적 탐색을 기반으로 효과적으로 작동하는 복잡한 탐색 토폴로지가 애플리케이션에 포함될 수 있습니다. 자세한 내용은 [탐색 토폴로지 개요](navigation-topologies-overview.md)를 참조하세요.

## <a name="see-also"></a>참조

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [탐색 토폴로지 개요](navigation-topologies-overview.md)
