---
title: '방법: 대화 상자 결과 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968239"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="b569d-102">방법: 대화 상자 결과 반환</span><span class="sxs-lookup"><span data-stu-id="b569d-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="b569d-103">이 예제에서는를 호출 <xref:System.Windows.Window.ShowDialog%2A>하 여 연 창에 대 한 대화 상자 결과를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b569d-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b569d-104">예제</span><span class="sxs-lookup"><span data-stu-id="b569d-104">Example</span></span>  
 <span data-ttu-id="b569d-105">대화 상자를 닫기 전에 해당 <xref:System.Windows.Window.DialogResult%2A> 속성은 사용자가 대화 상자를 닫은 방법을 나타내는 <xref:System.Nullable%601> <xref:System.Boolean> 로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b569d-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="b569d-106">이 값은 클라이언트 코드 <xref:System.Windows.Window.ShowDialog%2A> 에서 대화 상자를 닫은 방법과 결과를 처리 하는 방법을 결정할 수 있도록에 의해 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b569d-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b569d-107"><xref:System.Windows.Window.DialogResult%2A>창이를 호출 <xref:System.Windows.Window.ShowDialog%2A>하 여 열린 경우에만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b569d-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="b569d-108">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="b569d-108">.NET Framework Security</span></span>  
 <span data-ttu-id="b569d-109">를 <xref:System.Windows.Window.ShowDialog%2A> 호출 하려면 제한 없이 모든 창과 사용자 입력 이벤트를 사용할 수 있는 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b569d-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
