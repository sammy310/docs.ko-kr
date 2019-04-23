---
title: '방법: 메시지 상자 열기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: cf7534cdee5e17d53e95294573023d660135e395
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101109"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="0235b-102">방법: 메시지 상자 열기</span><span class="sxs-lookup"><span data-stu-id="0235b-102">How to: Open a Message Box</span></span>
<span data-ttu-id="0235b-103">이 예제에서는 메시지 상자를 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0235b-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0235b-104">예제</span><span class="sxs-lookup"><span data-stu-id="0235b-104">Example</span></span>  
 <span data-ttu-id="0235b-105">메시지 상자는 사용자에 게 정보를 표시 하기 위한 미리 만들어진된 모달 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="0235b-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="0235b-106">정적 호출 하 여 메시지 상자가 열려 <xref:System.Windows.MessageBox.Show%2A> 메서드는 <xref:System.Windows.MessageBox> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0235b-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="0235b-107">때 <xref:System.Windows.MessageBox.Show%2A> 는 호출 메시지 문자열 매개 변수를 사용 하 여 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0235b-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="0235b-108">여러 오버 로드가 <xref:System.Windows.MessageBox.Show%2A> 메시지 상자는 표시 되는 방식을 구성할 수 있습니다 (참조 <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="0235b-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="0235b-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="0235b-109">See also</span></span>

- [<span data-ttu-id="0235b-110">MessageBox 샘플</span><span class="sxs-lookup"><span data-stu-id="0235b-110">MessageBox Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160023)
