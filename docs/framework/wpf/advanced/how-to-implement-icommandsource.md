---
title: '방법: ICommandSource 구현'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 755377d25a2deb48aa9da86d4182075e30763530
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345090"
---
# <a name="how-to-implement-icommandsource"></a>방법: ICommandSource 구현

이 예제에서는 <xref:System.Windows.Input.ICommandSource>를 구현 하 여 명령 소스를 만드는 방법을 보여 줍니다. 명령 소스는 명령을 호출 하는 방법을 알고 있는 개체입니다. <xref:System.Windows.Input.ICommandSource> 인터페이스는 세 개의 멤버를 노출 합니다.

- <xref:System.Windows.Input.ICommandSource.Command%2A>: 호출 되는 명령입니다.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: 명령 소스에서 명령을 처리 하는 메서드로 전달 되는 사용자 정의 데이터 형식입니다.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: 명령이 실행 되 고 있는 개체입니다.

이 예제에서는 <xref:System.Windows.Controls.Slider> 컨트롤에서 상속 되 고 <xref:System.Windows.Input.ICommandSource> 인터페이스를 구현 하는 클래스가 생성 됩니다.
  
## <a name="example"></a>예

WPF는 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>및 <xref:System.Windows.Documents.Hyperlink>과 같은 <xref:System.Windows.Input.ICommandSource>를 구현 하는 여러 클래스를 제공 합니다. 명령 소스는 명령을 호출 하는 방법을 정의 합니다. 이러한 클래스는 클릭 하는 경우 명령을 호출 하 고 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성이 설정 된 경우에만 명령 소스가 됩니다.

이 예제에서는 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성이 변경 될 때 슬라이더가 이동 될 때 또는 더 정확 하 게 명령을 호출 합니다.

클래스 정의는 다음과 같습니다.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

다음 단계는 <xref:System.Windows.Input.ICommandSource> 멤버를 구현 하는 것입니다. 이 예제에서 속성은 <xref:System.Windows.DependencyProperty> 개체로 구현 됩니다. 이렇게 하면 속성이 데이터 바인딩을 사용할 수 있습니다. <xref:System.Windows.DependencyProperty> 클래스에 대 한 자세한 내용은 [종속성 속성 개요](dependency-properties-overview.md)를 참조 하세요. 데이터 바인딩에 대 한 자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)를 참조 하세요.

<xref:System.Windows.Input.ICommandSource.Command%2A> 속성만 여기에 표시 됩니다.
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
다음은 <xref:System.Windows.DependencyProperty> 변경 콜백입니다.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

다음 단계는 명령 원본과 연결 된 명령을 추가 하 고 제거 하는 것입니다. 이전 명령과 연결 된 이벤트 처리기가 있는 경우이를 먼저 제거 해야 하므로 새 명령이 추가 된 경우에만 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성을 덮어쓸 수 있습니다.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

다음 단계는 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 처리기에 대 한 논리를 만드는 것입니다.

<xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트는 명령 소스에 현재 명령 대상에서 실행 되는 명령의 기능이 변경 되었을 수 있음을 알립니다. 명령 소스가이 이벤트를 수신 하면 일반적으로 명령에서 <xref:System.Windows.Input.ICommand.CanExecute%2A> 메서드를 호출 합니다. 현재 명령 대상에서 명령을 실행할 수 없는 경우 명령 소스가 일반적으로 자체적으로 사용 하지 않도록 설정 됩니다. 현재 명령 대상에서 명령을 실행할 수 있는 경우 명령 소스가 일반적으로 자체적으로 사용 됩니다.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

마지막 단계는 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드입니다. 명령이 <xref:System.Windows.Input.RoutedCommand>이면 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드가 호출 됩니다. 그렇지 않으면 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 메서드가 호출 됩니다.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>참조

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [명령 개요](commanding-overview.md)
