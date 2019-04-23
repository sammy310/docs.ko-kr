---
title: '방법: RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209426"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a>방법: RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정
에 대 한 사용자 지정 상황에 맞는 메뉴를 배치 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 **RichTextBox**에 대한 사용자 지정 상황에 맞는 메뉴를 구현하는 경우 상황에 맞는 메뉴의 배치를 처리해야 합니다.  기본적으로 **RichTextBox**의 가운데에 사용자 지정 상황에 맞는 메뉴가 열립니다.  
  
## <a name="example"></a>예제  
 기본 배치 동작을 재정의 하려면에 대 한 수신기를 추가 합니다 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 이벤트입니다.  다음 예제에서는 이를 프로그래밍 방식으로 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 해당 구현을 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 이벤트 수신기입니다.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>참고자료

- [RichTextBox 개요](richtextbox-overview.md)
- [TextBox 개요](textbox-overview.md)
