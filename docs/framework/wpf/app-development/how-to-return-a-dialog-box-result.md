---
title: '방법: 대화 상자 결과 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: b574a5bbc08d947371837116915c2fc8c13ec81d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006716"
---
# <a name="how-to-return-a-dialog-box-result"></a>방법: 대화 상자 결과 반환
이 예제에서는 호출 하 여 열려 있는 창에 대 한 대화 상자 결과 검색 하는 방법을 보여 줍니다 <xref:System.Windows.Window.ShowDialog%2A>합니다.  
  
## <a name="example"></a>예제  
 대화 상자를 닫기 전에 해당 <xref:System.Windows.Window.DialogResult%2A> 속성을 사용 하 여 설정할 수는 <xref:System.Nullable%601> <xref:System.Boolean> 사용자 대화 상자를 닫은 방법을 나타내는입니다. 이 값을 반환할 <xref:System.Windows.Window.ShowDialog%2A> 클라이언트 코드는 대화 상자를 닫은 방법 및이 따른 결과 처리 하는 방법을 결정할 수 있도록 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A> 호출 하 여 창을 열린 경우에 설정할 수 있습니다 <xref:System.Windows.Window.ShowDialog%2A>합니다.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 호출 <xref:System.Windows.Window.ShowDialog%2A> 모든 창과 사용자 입력된 이벤트를 제한 없이 사용할 수 있는 권한이 필요 합니다.
