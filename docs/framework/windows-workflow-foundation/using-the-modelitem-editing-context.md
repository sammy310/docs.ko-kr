---
title: ModelItem 편집 컨텍스트 사용
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: 8b2f2b8d4c528de14ea8b37e4eda8190f1757c22
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664701"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="be59f-102">ModelItem 편집 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="be59f-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="be59f-103"><xref:System.Activities.Presentation.Model.ModelItem> 편집 컨텍스트는 호스트 응용 프로그램이 디자이너와 통신할 때 사용하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <span data-ttu-id="be59f-104"><xref:System.Activities.Presentation.EditingContext>는 사용할 수 있는 메서드 두 개(<xref:System.Activities.Presentation.EditingContext.Items%2A> 및 <xref:System.Activities.Presentation.EditingContext.Services%2A>)를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-104"><xref:System.Activities.Presentation.EditingContext> exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="be59f-105">Items 컬렉션</span><span class="sxs-lookup"><span data-stu-id="be59f-105">The Items collection</span></span>  
 <span data-ttu-id="be59f-106"><xref:System.Activities.Presentation.EditingContext.Items%2A> 컬렉션은 호스트와 디자이너 간에 공유되는 데이터나 모든 디자이너에서 사용할 수 있는 데이터에 액세스할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="be59f-107">이 컬렉션에는 <xref:System.Activities.Presentation.ContextItemManager> 클래스를 통해 액세스되는 다음 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="be59f-108">Services 컬렉션</span><span class="sxs-lookup"><span data-stu-id="be59f-108">The Services collection</span></span>  
 <span data-ttu-id="be59f-109"><xref:System.Activities.Presentation.EditingContext.Services%2A> 컬렉션은 디자이너가 호스트와 상호 작용하는 데 사용하는 서비스나 모든 디자이너에서 사용하는 서비스에 액세스할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="be59f-110">이 컬렉션에는 다음과 같은 중요한 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="be59f-111">작업에 디자이너 할당</span><span class="sxs-lookup"><span data-stu-id="be59f-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="be59f-112">작업에 사용되는 디자이너를 지정하려면 Designer 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="be59f-113">서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="be59f-113">Creating a service</span></span>  
 <span data-ttu-id="be59f-114">디자이너와 호스트 간에 정보 전달자 역할을 하는 서비스를 만들려면 인터페이스와 구현을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="be59f-115">인터페이스는 <xref:System.Activities.Presentation.ServiceManager.Publish%2A> 메서드에서 서비스의 멤버를 정의하는 데 사용되고 구현에는 서비스에 대한 논리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="be59f-116">다음 코드 예제에서는 서비스 인터페이스와 구현이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
```  
  
## <a name="publishing-a-service"></a><span data-ttu-id="be59f-117">서비스 게시</span><span class="sxs-lookup"><span data-stu-id="be59f-117">Publishing a service</span></span>  
 <span data-ttu-id="be59f-118">디자이너에서 서비스를 사용하려면 먼저 <xref:System.Activities.Presentation.ServiceManager.Publish%2A> 메서드를 사용하여 호스트가 서비스를 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="be59f-119">서비스 구독</span><span class="sxs-lookup"><span data-stu-id="be59f-119">Subscribing to a service</span></span>  
 <span data-ttu-id="be59f-120">디자이너는 <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> 메서드에서 <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> 메서드를 사용하여 서비스에 대한 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="be59f-121">다음 코드 조각에서는 서비스를 구독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
```  
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="be59f-122">Items 컬렉션을 사용하여 데이터 공유</span><span class="sxs-lookup"><span data-stu-id="be59f-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="be59f-123">Items 컬렉션 사용은 Publish 대신 <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>가 사용된다는 점을 제외하고 Services 컬렉션 사용과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="be59f-124">이 컬렉션은 복잡한 기능보다 디자이너와 호스트 간에 간단한 데이터를 공유하는 데 보다 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="be59f-125">EditingContext 호스트 항목 및 서비스</span><span class="sxs-lookup"><span data-stu-id="be59f-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="be59f-126">.NET Framework는 다양 한 기본 제공 항목 및 편집 컨텍스트를 통해 액세스 하는 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="be59f-127">항목:</span><span class="sxs-lookup"><span data-stu-id="be59f-127">Items:</span></span>  
  
- <span data-ttu-id="be59f-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: 컨트롤 (예: 식 편집기)에 대 한 워크플로 내부에서 사용 될 참조 된 로컬 어셈블리 목록을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
- <span data-ttu-id="be59f-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: 디자이너는 읽기 전용 상태 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indicates whether the designer is in a read-only state.</span></span>  
  
- <span data-ttu-id="be59f-130"><xref:System.Activities.Presentation.View.Selection>: 현재 선택 된 개체의 컬렉션을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-130"><xref:System.Activities.Presentation.View.Selection>: Defines the collection of objects that are currently selected.</span></span>  
  
- <span data-ttu-id="be59f-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span><span class="sxs-lookup"><span data-stu-id="be59f-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span></span>  
  
- <span data-ttu-id="be59f-132"><xref:System.Activities.Presentation.WorkflowFileItem>: 현재 편집 세션의 기반이 되는 파일에 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="be59f-133">서비스:</span><span class="sxs-lookup"><span data-stu-id="be59f-133">Services:</span></span>  
  
- <span data-ttu-id="be59f-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: 현재 인스턴스를 추가할 수 있습니다 사용 하 여 <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
- <span data-ttu-id="be59f-135"><xref:System.Activities.Presentation.View.DesignerView>: 디자이너 캔버스의 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-135"><xref:System.Activities.Presentation.View.DesignerView>: Allows access to the properties of the designer canvas.</span></span>  
  
- <span data-ttu-id="be59f-136"><xref:System.Activities.Presentation.IActivityToolboxService>: 업데이트할 도구 상자의 콘텐츠를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Allows the contents of the toolbox to be updated.</span></span>  
  
- <span data-ttu-id="be59f-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: 사용자 지정 제공 서비스 구현과 디자이너 명령 (예: 상황에 맞는 메뉴)를 통합 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
- <span data-ttu-id="be59f-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: 디자이너 디버거에 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Provides functionality for the designer debugger.</span></span>  
  
- <span data-ttu-id="be59f-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: 식 편집기 대화 상자에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Provides access to the Expression Editor dialog.</span></span>  
  
- <span data-ttu-id="be59f-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: 통합된 도움말 기능을 사용 하 여 디자이너를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Provides the designer with integrated help functionality.</span></span>  
  
- <span data-ttu-id="be59f-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: 사용 하 여 유효성 검사 오류에 대 한 액세스를 제공 <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
- <span data-ttu-id="be59f-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: 내부 데이터 저장 및 검색 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="be59f-143">이 서비스는.NET Framework에서 내부적으로 사용 됩니다 하 고 외부 사용에 대 한이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
- <span data-ttu-id="be59f-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: XAML 로드 오류 컬렉션을 사용에 대 한 액세스를 제공 <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
- <span data-ttu-id="be59f-145"><xref:System.Activities.Presentation.Services.ModelService>: 디자이너에서 편집 중인 워크플로 모델과 상호 작용할 수 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-145"><xref:System.Activities.Presentation.Services.ModelService>: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
- <span data-ttu-id="be59f-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: 사용 하 여 모델 항목 트리 루트에 대 한 액세스를 제공 <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
- <span data-ttu-id="be59f-147"><xref:System.Activities.Presentation.UndoEngine>: 실행 취소를 제공 하 고 기능을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-147"><xref:System.Activities.Presentation.UndoEngine>: Provides undo and redo functionality.</span></span>  
  
- <span data-ttu-id="be59f-148"><xref:System.Activities.Presentation.Services.ViewService>: 기본 모델 항목에 시각적 요소를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-148"><xref:System.Activities.Presentation.Services.ViewService>: Maps visual elements to underlying model items.</span></span>  
  
- <span data-ttu-id="be59f-149"><xref:System.Activities.Presentation.View.ViewStateService>: 뷰 모델 항목에 대 한 상태를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-149"><xref:System.Activities.Presentation.View.ViewStateService>: Stores view states for model items.</span></span>  
  
- <span data-ttu-id="be59f-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: 가상 컨테이너 UI 동작을 사용자 지정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Used to customize the virtual container UI behavior.</span></span>  
  
- <span data-ttu-id="be59f-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: 등록 및 이벤트 알림에 대 한 대리자를 등록 취소 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="be59f-152">창 소유자를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be59f-152">Also allows a window owner to be set.</span></span>
