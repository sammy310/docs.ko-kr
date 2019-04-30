---
title: '방법: 대화 상자 열기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947708"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="6670d-102">방법: 대화 상자 열기</span><span class="sxs-lookup"><span data-stu-id="6670d-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="6670d-103">이 예제에서는 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6670d-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6670d-104">예제</span><span class="sxs-lookup"><span data-stu-id="6670d-104">Example</span></span>  
 <span data-ttu-id="6670d-105">대화 상자는 인스턴스화하여 열려 있는 창을 <xref:System.Windows.Window> 호출을 <xref:System.Windows.Window.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6670d-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="6670d-106"><xref:System.Windows.Window.ShowDialog%2A> 창이 열리고 새 대화 상자가 닫힐 때까지 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6670d-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="6670d-107">이 창 유형에 라고도 *모달* 창 하며 사용자 입력을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6670d-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="6670d-108">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="6670d-108">.NET Framework Security</span></span>  
 <span data-ttu-id="6670d-109">호출 <xref:System.Windows.Window.ShowDialog%2A> 모든 창과 사용자 입력된 이벤트를 제한 없이 사용할 수 있는 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6670d-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6670d-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="6670d-110">See also</span></span>

- [<span data-ttu-id="6670d-111">대화 상자 결과 반환</span><span class="sxs-lookup"><span data-stu-id="6670d-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
