---
title: 사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: d1047b8be35545e83eaa8788b53751b6b0056984
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338047"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="a4759-102">사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터</span><span class="sxs-lookup"><span data-stu-id="a4759-102">Custom Composite Designers - Workflow Item Presenter</span></span>

<span data-ttu-id="a4759-103"><xref:System.Activities.Presentation.WorkflowItemPresenter>는 임의의 작업을 배치할 수 있는 "끌어 놓기 영역"을 만들 수 있도록 하는 WF 디자이너 프로그래밍 모델의 키 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="a4759-104">이 샘플에서는 "끌어 놓기 영역"을 표시 하는 활동 디자이너를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

<span data-ttu-id="a4759-105">이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-105">This sample demonstrates:</span></span>

- <span data-ttu-id="a4759-106"><xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="a4759-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

- <span data-ttu-id="a4759-107">메타데이터 저장소를 사용하여 사용자 지정 디자이너 등록</span><span class="sxs-lookup"><span data-stu-id="a4759-107">Registering the custom designer using the metadata store.</span></span>

- <span data-ttu-id="a4759-108">다시 호스트된 도구 상자를 선언적으로 또는 명령적으로 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a4759-108">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="a4759-109">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="a4759-109">Sample Details</span></span>

<span data-ttu-id="a4759-110">이 샘플의 코드는 다음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-110">The code for this sample shows:</span></span>

- <span data-ttu-id="a4759-111">`SimpleNativeActivity` 클래스에 대해 사용자 지정 활동 디자이너가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-111">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

- <span data-ttu-id="a4759-112"><xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="a4759-112">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

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

 <span data-ttu-id="a4759-113">WPF 데이터 바인딩을 사용하여 `ModelItem.Body`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-113">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="a4759-114">`ModelItem`는 디자이너가 사용 되는 원본 개체 (이 경우 **SimpleNativeActivity**)를 참조 하는 <xref:System.Activities.Presentation.ActivityDesigner>의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-114">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="a4759-115">샘플 설정, 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="a4759-115">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="a4759-116">Visual Studio에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-116">Open the solution in Visual Studio.</span></span>

2. <span data-ttu-id="a4759-117">**F5** 키를 눌러 응용 프로그램을 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-117">Press **F5** to compile and run the application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4759-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4759-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a4759-119">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a4759-120">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4759-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4759-121">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`

## <a name="see-also"></a><span data-ttu-id="a4759-122">참조</span><span class="sxs-lookup"><span data-stu-id="a4759-122">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="a4759-123">워크플로 디자이너로 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="a4759-123">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
