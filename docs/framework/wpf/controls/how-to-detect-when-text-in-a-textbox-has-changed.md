---
title: '방법: TextBox에서 텍스트가 변경되는 시점 감지'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1adadb0f071815930d34f40ddf244ffc8c19131b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000976"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="785b0-102">방법: TextBox에서 텍스트가 변경되는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="785b0-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="785b0-103">이 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 메서드를 실행 하는 이벤트 때마다의 텍스트를 <xref:System.Windows.Controls.TextBox> 컨트롤이 변경 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="785b0-104">코드 숨김 클래스에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 포함 하는 합니다 <xref:System.Windows.Controls.TextBox> 변경에 대 한 모니터링 하려는 컨트롤 삽입 될 때마다 호출할 메서드를를 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="785b0-105">이 메서드는에서 예상한 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="785b0-106">이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 사용자 또는 프로그래밍 방식으로 제어 됩니다 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="785b0-107">**참고:** 이 이벤트를 발생 하는 경우는 <xref:System.Windows.Controls.TextBox> 제어를 만들고 텍스트를 사용 하 여 처음에 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="785b0-108">예제</span><span class="sxs-lookup"><span data-stu-id="785b0-108">Example</span></span>  
 <span data-ttu-id="785b0-109">에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 프로그램 <xref:System.Windows.Controls.TextBox> 컨트롤을 지정를 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 처리기 메서드 이름이 일치 하는 값을 사용 하 여 특성.</span><span class="sxs-lookup"><span data-stu-id="785b0-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="785b0-110">예제</span><span class="sxs-lookup"><span data-stu-id="785b0-110">Example</span></span>  
 <span data-ttu-id="785b0-111">코드 숨김 클래스에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 포함 하는 합니다 <xref:System.Windows.Controls.TextBox> 변경에 대 한 모니터링 하려는 컨트롤 삽입 될 때마다 호출할 메서드를를 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="785b0-112">이 메서드는에서 예상한 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="785b0-113">이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 사용자 또는 프로그래밍 방식으로 제어 됩니다 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="785b0-114">**참고:** 이 이벤트를 발생 하는 경우는 <xref:System.Windows.Controls.TextBox> 제어를 만들고 텍스트를 사용 하 여 처음에 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="785b0-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="785b0-115">설명</span><span class="sxs-lookup"><span data-stu-id="785b0-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785b0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="785b0-116">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="785b0-117">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="785b0-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="785b0-118">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="785b0-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
