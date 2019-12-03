---
title: Programming Model Item Tree
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: efda69ac568b0ad9c5fdcf4d42722c5b7dadd3f3
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715673"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="c6238-102">Programming Model Item Tree</span><span class="sxs-lookup"><span data-stu-id="c6238-102">Programming Model Item Tree</span></span>
<span data-ttu-id="c6238-103">이 샘플에서는 Windows Presentation Foundation (WPF) 트리 뷰에서 선언적 데이터 바인딩을 사용 하 여 <xref:System.Activities.Presentation.Model.ModelItem> 트리를 탐색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="c6238-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="c6238-104">Sample Details</span></span>
 <span data-ttu-id="c6238-105"><xref:System.Activities.Presentation.Model.ModelItem> 트리는 Windows 워크플로 디자이너 인프라에서 편집 중인 기본 인스턴스에 대 한 데이터를 노출 하는 데 사용 되는 추상화입니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the Windows Workflow Designer infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="c6238-106">다음 그림은 워크플로 디자이너 내에서 인프라의 다양 한 계층을 묘사 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-106">The following illustration is a depiction of the various layers of infrastructure within the Workflow Designer.</span></span>

 ![워크플로 디자이너 아키텍처를 보여 주는 다이어그램입니다.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="c6238-108"><xref:System.Activities.Presentation.Model.ModelItem>은 내부 값에 대한 포인터와 <xref:System.Activities.Presentation.Model.ModelProperty> 개체의 컬렉션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="c6238-109"><xref:System.Activities.Presentation.Model.ModelProperty> 개체는 속성의 이름 및 형식 같은 데이터와 값에 대한 포인터로 구성되며 이 값은 또 다른 <xref:System.Activities.Presentation.Model.ModelItem>입니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="c6238-110">값 변환기는 <xref:System.Activities.Presentation.Model.ModelItem>에서 반환된 <xref:System.Activities.Presentation.Model.ModelProperty>의 일부를 조작하여 트리 뷰에 올바르게 나타나도록 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="c6238-111">그런 다음 샘플에서는 다음 예제에 표시된 것과 같은 명령적 구문을 사용하여 <xref:System.Activities.Presentation.Model.ModelItem> 트리에 대해 명령적으로 프로그래밍하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="c6238-112">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="c6238-112">To use this sample</span></span>

1. <span data-ttu-id="c6238-113">Visual Studio 2010에서 ProgrammingModelItemTree 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="c6238-114">**빌드** 메뉴에서 **솔루션 빌드** 를 선택 하 여 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="c6238-115">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-115">Press F5 to run the application.</span></span> <span data-ttu-id="c6238-116">WPF 양식이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="c6238-117">**WF 로드** 단추를 클릭 하 여 <xref:System.Activities.Presentation.Model.ModelItem>를 로드 하 고 트리 뷰에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="c6238-118">**모델 항목 트리 변경** 단추를 클릭 하면 이전 코드를 실행 하 여 트리에 항목을 추가 하 고 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6238-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c6238-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c6238-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="c6238-121">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c6238-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6238-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="c6238-123">참조</span><span class="sxs-lookup"><span data-stu-id="c6238-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>
