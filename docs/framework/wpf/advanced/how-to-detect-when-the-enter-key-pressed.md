---
title: '방법: 탐지를 누른 키를 입력 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051418"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="0fab9-102">방법: 탐지를 누른 키를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fab9-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="0fab9-103">시기를 감지 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Input.Key.Enter> 키보드의 키가 눌러져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fab9-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="0fab9-104">이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab9-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fab9-105">예제</span><span class="sxs-lookup"><span data-stu-id="0fab9-105">Example</span></span>  
 <span data-ttu-id="0fab9-106">누를 때 합니다 <xref:System.Windows.Input.Key.Enter> 키를 <xref:System.Windows.Controls.TextBox>, 텍스트 상자에 입력의 다른 영역에 표시는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="0fab9-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="0fab9-107">다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 구성 된 사용자 인터페이스를 만들고는 <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>, 및 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="0fab9-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="0fab9-108">다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.KeyDown> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab9-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="0fab9-109">키를 누를 경우는 <xref:System.Windows.Input.Key.Enter> 키를 메시지에 표시 됩니다는 <xref:System.Windows.Controls.TextBlock>합니다.</span><span class="sxs-lookup"><span data-stu-id="0fab9-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="0fab9-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="0fab9-110">See also</span></span>

- [<span data-ttu-id="0fab9-111">입력 개요</span><span class="sxs-lookup"><span data-stu-id="0fab9-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="0fab9-112">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="0fab9-112">Routed Events Overview</span></span>](routed-events-overview.md)
