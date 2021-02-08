---
description: XAML에서 WPF 및 Windows Workflow Foundation 통합에 대해 자세히 알아보세요.
title: XAML의 WPF 및 WF 통합
ms.date: 03/30/2017
ms.assetid: a4f53b48-fc90-4315-bca0-ba009562f488
ms.openlocfilehash: 3cc2d0336a2507dcf36fea3f3d240b95d22193e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798110"
---
# <a name="wpf-and-windows-workflow-foundation-integration-in-xaml"></a>WPF 및 XAML의 Windows Workflow Foundation 통합

이 샘플에서는 단일 XAML 문서에서 Windows Presentation Foundation (WPF) 및 Windows Workflow Foundation (WF) 기능을 사용 하는 응용 프로그램을 만드는 방법을 보여 줍니다. 이를 위해이 샘플에서는 Windows Workflow Foundation 및 XAML 확장성을 사용 합니다.

## <a name="sample-details"></a>샘플 세부 정보

 <xref:System.Activities.Statements.Sequence> 및 `ShowWindow`이라는 활동 시퀀스를 통해 조작되는 문자열 변수 두 개를 사용하여 ShowWindow.xaml 파일을 `WriteLine` 활동으로 역직렬화합니다. <xref:System.Activities.Statements.WriteLine> 활동은 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성에 할당되는 식을 콘솔 창에 출력합니다. `ShowWindow`활동은 WPF 창을 실행 논리의 일부로 표시 합니다. 이 창의 <xref:System.Activities.ActivityContext.DataContext%2A>에는 시퀀스에서 선언한 변수가 포함됩니다. `ShowWindow` 활동에 선언된 창의 컨트롤에서 데이터 바인딩을 사용하여 해당 변수를 조작합니다. 마지막으로, 창에 단추 컨트롤이 포함됩니다. 단추에 대한 `Click` 이벤트는 이름이 <xref:System.Activities.ActivityDelegate>인 `MarkupExtension` 활동이 포함된 `CloseWindow`에서 처리됩니다. `MarkUpExtension`은 포함된 활동을 호출하고, 이 활동은 컨텍스트에 따라 `x:Name`으로 식별되는 개체 및 해당 활동을 포함하는 창의 <xref:System.Activities.ActivityContext.DataContext%2A>를 제공합니다. 따라서 창의 이름을 참조하는 식을 사용하여 `CloseWindow.InArgument<Window>`를 바인딩할 수 있습니다.

 `ShowWindow`활동은 클래스에서 파생 <xref:System.Activities.AsyncCodeActivity%601> 되어 WPF 창을 표시 하 고 창이 닫힐 때 완료 됩니다. `Window` 속성은 활동을 실행할 때마다 요청 시 창을 만들도록 허용하는 `Func<Window>` 형식입니다. 이와 같은 지연된 계산 모델을 위해 `Window`가 <xref:System.Xaml.XamlDeferringLoader> 속성에 사용됩니다. `FuncFactoryDeferringLoader`는 serialization 과정에서 `XamlReader`를 캡처한 다음 활동을 실행하는 동안 이를 읽을 수 있도록 합니다.

 활동을 제대로 작성하면 스케줄러 스레드가 차단되지 않습니다. 그러나 표시되어 있는 창을 닫지 않으면 `ShowWindow` 활동이 완료되지 않습니다. `ShowWindow` 활동에서는 이와 같은 동작을 달성하기 위해 <xref:System.Activities.AsyncCodeActivity>로부터 파생하고 <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A> 메서드에 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> 메서드를 호출하고, 창을 모달로 표시합니다. 대리자는 WPF <xref:System.ServiceModel.InstanceContext.SynchronizationContext%2A>를 통해 호출됩니다. `ShowWindow` 활동에서는 범위 내의 변수에 대한 데이터 바인딩된 컨트롤 액세스를 제공하기 위해 <xref:System.Activities.ActivityContext.DataContext%2A> 속성을 `Window.DataContext` 속성에 할당합니다.

 이 샘플에서 마지막으로 주목해야 할 부분은 <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>이라는 `DelegateActivityExtension`입니다. 이 태그 확장의 `ProvideValue` 메서드는 포함된 활동을 호출하는 대리자를 반환합니다. 이 활동은 WPF 데이터 컨텍스트 및 범위 내 값을 포함 하는 환경에서 실행 됩니다 `x:Name` . `GenericInvoke` 메서드에서 이 환경은 <xref:System.Activities.Hosting.SymbolResolver> 확장을 통해 환경에 제공됩니다. 이 확장은 <xref:System.Activities.WorkflowInvoker>에 추가되고, 이 호출자는 태그 확장의 대리자를 호출할 때마다 포함된 활동을 호출하는 데 사용됩니다.

> [!NOTE]
> 기본 디자이너에서는 ShowWindow 활동을 지원하지 않으므로 ShowWindow.Xaml 파일이 디자이너에 올바르게 표시되지 않습니다.

## <a name="run-the-sample"></a>샘플 실행

1. Visual Studio를 사용 하 여 WPFWFIntegration 솔루션 파일을 엽니다.

2. 솔루션을 빌드하려면 **ctrl** + **Shift** + **B** 를 누릅니다.

3. 솔루션을 실행 하려면 **f5** 키를 누릅니다.

4. 대화 상자에 이름과 성을 입력합니다.

5. 대화 상자를 닫으면 콘솔에 사용자의 이름이 표시됩니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\WPFWFIntegration`
