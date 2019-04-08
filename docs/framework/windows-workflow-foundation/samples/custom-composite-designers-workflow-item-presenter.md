---
title: 사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: 4c1258a49ac3ef2227d520fe11f341819f8663a0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089200"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터
<xref:System.Activities.Presentation.WorkflowItemPresenter> 임의의 활동을 배치할 수 있는 "끌어 놓기 영역"을 만들 수 있도록 하는 WF 디자이너 프로그래밍 모델의 키 형식입니다. 이 샘플에서는 표시 이러한 "드롭 영역". "를 사용 하는 활동 디자이너를 빌드하는 방법을 보여 줍니다.

 이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.

## <a name="demonstrates"></a>세부 항목

-   <xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너 만들기

-   메타데이터 저장소를 사용하여 사용자 지정 디자이너 등록

-   다시 호스트된 도구 상자를 선언적으로 또는 명령적으로 프로그래밍

## <a name="sample-details"></a>샘플 세부 정보
 이 샘플의 코드는 다음을 보여 줍니다.

-   `SimpleNativeActivity` 클래스에 대해 사용자 지정 활동 디자이너가 빌드됩니다.

-   <xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너를 만드는 방법

```xaml
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
    xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
    <sap:ActivityDesigner.Resources>
        <DataTemplate x:Key="Collapsed">
            <StackPanel>
                <TextBlock>This is the collapsed view</TextBlock>
            </StackPanel>
        </DataTemplate>
        <DataTemplate x:Key="Expanded">
            <StackPanel>
                <TextBlock>Custom Text</TextBlock>
                <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                        HintText="Please drop an activity here" />
            </StackPanel>
        </DataTemplate>
        <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
            <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
            <Style.Triggers>
                <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                    <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                </DataTrigger>
            </Style.Triggers>
        </Style>
    </sap:ActivityDesigner.Resources>
    <Grid>
        <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
    </Grid>
</sap:ActivityDesigner>
```

 WPF 데이터 바인딩을 사용하여 `ModelItem.Body`에 바인딩합니다. `ModelItem` 속성 켜져 <xref:System.Activities.Presentation.ActivityDesigner> 은 디자이너가 사용 될,이 경우 기본 개체를 나타내는 **SimpleNativeActivity**합니다.

#### <a name="to-setup-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면

1.  Visual Studio 2010에서 솔루션을 엽니다.

2.  F5 키를 눌러 애플리케이션을 컴파일하고 실행합니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a>참고자료

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [Workflow Designer로 응용 프로그램 개발](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
