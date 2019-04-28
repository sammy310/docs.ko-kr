---
title: '방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: 8ffa4c9919788060dc4524e127c181ee8282e6f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768604"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, 및 <xref:System.Windows.Documents.FlowDocument> 컨트롤은 모두 기본 제공 끌어서 놓기 기능을 포함 합니다. 기본 제공 기능 및 컨트롤 내에서 텍스트 끌어서 놓기 수 있습니다. 그러나 사용 되지 않습니다 컨트롤에 있는 파일을 삭제 하 여 파일을 열면 됩니다. 이러한 컨트롤은 또한 처리 된 것으로 끌어서 놓기 이벤트를 표시 합니다. 결과적으로, 기본적으로 끌어 놓은 파일을 여는 기능을 제공 하는 고유한 이벤트 처리기를 추가할 수 없습니다.  
  
 이러한 컨트롤에서 끌어서 놓기 이벤트에 대 한 추가 처리를 추가 하려면 사용 된 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 끌어서 놓기 이벤트에 대 한 이벤트 처리기를 추가 하는 방법입니다. 설정 된 `handledEventsToo` 매개 변수를 `true` 된 지정 된 처리기를 이벤트 경로 따라 다른 요소에 의해 처리 된 것으로 이미 표시 된 라우트된 이벤트에 대 한 호출 수에 합니다.  
  
> [!TIP]
>  기본 제공 끌어서 놓기 기능을 바꿀 수 있습니다 <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, 및 <xref:System.Windows.Documents.FlowDocument> 미리 보기 버전의 끌어서 놓기 이벤트를 처리 하 여 미리 보기 이벤트를 처리 됨으로 표시 합니다. 그러나이 기본 제공 끌어서 놓기 기능을 사용 하지 않도록 설정 됩니다 및 권장 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 처리기를 추가 하는 방법에 설명 합니다 <xref:System.Windows.DragDrop.DragOver> 및 <xref:System.Windows.DragDrop.Drop> 이벤트는 <xref:System.Windows.Controls.RichTextBox>합니다. 이 예제에서는 합니다 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 메서드 집합과 `handledEventsToo` 매개 변수를 `true` 이벤트 처리기도 호출 될 수 있도록는 <xref:System.Windows.Controls.RichTextBox> 이러한 이벤트를 처리 됨으로 표시 합니다. 삭제 된 텍스트 파일을 여는 기능을 추가 하는 이벤트 처리기의 코드는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 이 예제를 테스트 하려면 끌어 텍스트 파일 또는 서식 있는 텍스트 RTF (서식) 파일에 Windows 탐색기에서는 <xref:System.Windows.Controls.RichTextBox>합니다. 파일을 열 수는 <xref:System.Windows.Controls.RichTextBox>합니다. 삭제 하기 전에 SHIFT 키를 누르면 파일에 일반 텍스트로 파일을 열 수는 있습니다.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
