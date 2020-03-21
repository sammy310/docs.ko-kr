---
title: '방법: ICommandSource 구현'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174695"
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="2f8e9-102">방법: ICommandSource 구현</span><span class="sxs-lookup"><span data-stu-id="2f8e9-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="2f8e9-103">이 예제에서는 을 구현하여 <xref:System.Windows.Input.ICommandSource>명령 소스를 만드는 방법을 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="2f8e9-104">명령 소스는 명령을 호출하는 방법을 알고 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="2f8e9-105">인터페이스는 <xref:System.Windows.Input.ICommandSource> 세 멤버를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="2f8e9-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: 호출될 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="2f8e9-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: 명령 소스에서 명령을 처리하는 메서드로 전달되는 사용자 정의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="2f8e9-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: 명령이 실행중인 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="2f8e9-109">이 예제에서는 <xref:System.Windows.Controls.Slider> 컨트롤에서 상속 하 고 인터페이스를 구현 <xref:System.Windows.Input.ICommandSource> 하는 클래스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="2f8e9-110">예제</span><span class="sxs-lookup"><span data-stu-id="2f8e9-110">Example</span></span>

<span data-ttu-id="2f8e9-111"><xref:System.Windows.Input.ICommandSource>WPF는 <xref:System.Windows.Controls.Button>을 구현 하는 클래스의 <xref:System.Windows.Controls.MenuItem>수를 <xref:System.Windows.Documents.Hyperlink>제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="2f8e9-112">명령 소스는 명령을 호출하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="2f8e9-113">이러한 클래스는 클릭할 때 명령을 호출하고 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성이 설정될 때만 명령 소스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="2f8e9-114">이 예제에서는 슬라이더를 이동할 때 또는 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성이 변경될 때 더 정확하게 명령을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="2f8e9-115">클래스 정의는 다음과 입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="2f8e9-116">다음 단계는 멤버를 <xref:System.Windows.Input.ICommandSource> 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="2f8e9-117">이 예제에서는 속성이 개체로 <xref:System.Windows.DependencyProperty> 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="2f8e9-118">이렇게 하면 속성에서 데이터 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="2f8e9-119">클래스에 <xref:System.Windows.DependencyProperty> 대한 자세한 내용은 [종속성 속성 개요를](dependency-properties-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="2f8e9-120">데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="2f8e9-121"><xref:System.Windows.Input.ICommandSource.Command%2A> 숙소만 여기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="2f8e9-122">변경 콜백은 <xref:System.Windows.DependencyProperty> 다음과 입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="2f8e9-123">다음 단계는 명령 소스와 연결된 명령을 추가하고 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="2f8e9-124">이전 <xref:System.Windows.Input.ICommandSource.Command%2A> 명령과 연결된 이벤트 처리기를 먼저 제거해야 하므로 새 명령을 추가할 때 속성을 덮어쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="2f8e9-125">다음 단계는 처리기에 대한 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 논리를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="2f8e9-126">이 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트는 명령 소스에 현재 명령 대상에서 실행하는 명령의 기능이 변경되었을 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="2f8e9-127">명령 원본이 이 이벤트를 수신하면 <xref:System.Windows.Input.ICommand.CanExecute%2A> 일반적으로 명령에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="2f8e9-128">명령이 현재 명령 대상에서 실행할 수 없는 경우 명령 소스는 일반적으로 자체적으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="2f8e9-129">명령이 현재 명령 대상에서 실행할 수 있는 경우 명령 소스는 일반적으로 자체적으로 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="2f8e9-130">마지막 단계는 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="2f8e9-131">명령이 a인 <xref:System.Windows.Input.RoutedCommand>경우 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드가 호출됩니다. 그렇지 않으면 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8e9-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="2f8e9-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f8e9-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="2f8e9-133">명령 개요</span><span class="sxs-lookup"><span data-stu-id="2f8e9-133">Commanding Overview</span></span>](commanding-overview.md)
