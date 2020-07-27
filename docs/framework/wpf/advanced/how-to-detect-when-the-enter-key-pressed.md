---
title: '방법: Enter 키를 누르는 시점 감지'
description: Windows Presentation Foundation 키보드에서 Enter 키가 선택 된 경우를 검색 합니다. 이 예제는 XAML 및 코드 숨김으로 구성 되어 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163187"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="6d4c0-104">방법: Enter 키를 누르는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="6d4c0-104">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="6d4c0-105">이 예제에서는 키보드에서 키를 누르는 시기를 검색 하는 방법을 보여 줍니다 <xref:System.Windows.Input.Key.Enter> .</span><span class="sxs-lookup"><span data-stu-id="6d4c0-105">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="6d4c0-106">이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김으로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d4c0-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d4c0-107">예제</span><span class="sxs-lookup"><span data-stu-id="6d4c0-107">Example</span></span>  
 <span data-ttu-id="6d4c0-108">사용자가에서 키를 누르면 <xref:System.Windows.Input.Key.Enter> <xref:System.Windows.Controls.TextBox> 텍스트 상자의 입력이의 다른 영역에 나타납니다 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d4c0-108">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="6d4c0-109">다음 XAML은, 및로 구성 된 사용자 인터페이스를 만듭니다 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="6d4c0-109">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="6d4c0-110">다음 코드는 <xref:System.Windows.UIElement.KeyDown> 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d4c0-110">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="6d4c0-111">누른 키가 <xref:System.Windows.Input.Key.Enter> 키인 경우 메시지가에 표시 됩니다 <xref:System.Windows.Controls.TextBlock> .</span><span class="sxs-lookup"><span data-stu-id="6d4c0-111">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="6d4c0-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d4c0-112">See also</span></span>

- [<span data-ttu-id="6d4c0-113">입력 개요</span><span class="sxs-lookup"><span data-stu-id="6d4c0-113">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="6d4c0-114">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="6d4c0-114">Routed Events Overview</span></span>](routed-events-overview.md)
