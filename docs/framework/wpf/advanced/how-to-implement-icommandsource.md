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
# <a name="how-to-implement-icommandsource"></a>방법: ICommandSource 구현

이 예제에서는 을 구현하여 <xref:System.Windows.Input.ICommandSource>명령 소스를 만드는 방법을 보여 주십습니다. 명령 소스는 명령을 호출하는 방법을 알고 있는 개체입니다. 인터페이스는 <xref:System.Windows.Input.ICommandSource> 세 멤버를 노출합니다.

- <xref:System.Windows.Input.ICommandSource.Command%2A>: 호출될 명령입니다.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: 명령 소스에서 명령을 처리하는 메서드로 전달되는 사용자 정의 데이터 형식입니다.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: 명령이 실행중인 개체입니다.

이 예제에서는 <xref:System.Windows.Controls.Slider> 컨트롤에서 상속 하 고 인터페이스를 구현 <xref:System.Windows.Input.ICommandSource> 하는 클래스가 만들어집니다.
  
## <a name="example"></a>예제

<xref:System.Windows.Input.ICommandSource>WPF는 <xref:System.Windows.Controls.Button>을 구현 하는 클래스의 <xref:System.Windows.Controls.MenuItem>수를 <xref:System.Windows.Documents.Hyperlink>제공 합니다. 명령 소스는 명령을 호출하는 방법을 정의합니다. 이러한 클래스는 클릭할 때 명령을 호출하고 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성이 설정될 때만 명령 소스가 됩니다.

이 예제에서는 슬라이더를 이동할 때 또는 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성이 변경될 때 더 정확하게 명령을 호출합니다.

클래스 정의는 다음과 입니다.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

다음 단계는 멤버를 <xref:System.Windows.Input.ICommandSource> 구현하는 것입니다. 이 예제에서는 속성이 개체로 <xref:System.Windows.DependencyProperty> 구현됩니다. 이렇게 하면 속성에서 데이터 바인딩을 사용할 수 있습니다. 클래스에 <xref:System.Windows.DependencyProperty> 대한 자세한 내용은 [종속성 속성 개요를](dependency-properties-overview.md)참조하십시오. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오.

<xref:System.Windows.Input.ICommandSource.Command%2A> 숙소만 여기에 표시됩니다.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
변경 콜백은 <xref:System.Windows.DependencyProperty> 다음과 입니다.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

다음 단계는 명령 소스와 연결된 명령을 추가하고 제거하는 것입니다. 이전 <xref:System.Windows.Input.ICommandSource.Command%2A> 명령과 연결된 이벤트 처리기를 먼저 제거해야 하므로 새 명령을 추가할 때 속성을 덮어쓸 수 없습니다.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

다음 단계는 처리기에 대한 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 논리를 만드는 것입니다.

이 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트는 명령 소스에 현재 명령 대상에서 실행하는 명령의 기능이 변경되었을 수 있음을 지정합니다. 명령 원본이 이 이벤트를 수신하면 <xref:System.Windows.Input.ICommand.CanExecute%2A> 일반적으로 명령에서 메서드를 호출합니다. 명령이 현재 명령 대상에서 실행할 수 없는 경우 명령 소스는 일반적으로 자체적으로 비활성화됩니다. 명령이 현재 명령 대상에서 실행할 수 있는 경우 명령 소스는 일반적으로 자체적으로 사용하도록 설정합니다.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

마지막 단계는 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드입니다. 명령이 a인 <xref:System.Windows.Input.RoutedCommand>경우 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드가 호출됩니다. 그렇지 않으면 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 메서드가 호출됩니다.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [명령 개요](commanding-overview.md)
