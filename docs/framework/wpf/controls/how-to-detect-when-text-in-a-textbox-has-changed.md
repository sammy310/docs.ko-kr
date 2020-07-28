---
title: '방법: TextBox에서 텍스트가 변경되는 시점 감지'
description: TextChanged 이벤트를 사용 하 여 Windows Presentation Foundation 응용 프로그램에서 TextBox 컨트롤의 텍스트가 변경 될 때마다 메서드를 실행 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166228"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="14d76-103">방법: TextBox에서 텍스트가 변경되는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="14d76-103">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="14d76-104">이 예제에서는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 컨트롤의 텍스트가 변경 될 때마다 이벤트를 사용 하 여 메서드를 실행 하는 한 가지 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="14d76-104">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="14d76-105">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]변경 내용을 모니터링 하려는 컨트롤이 포함 된의 코드 숨김이 클래스에서 <xref:System.Windows.Controls.TextBox> 이벤트가 발생할 때마다 호출할 메서드를 삽입 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d76-105">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="14d76-106">이 메서드에는 대리자가 예상 하는 시그니처와 일치 하는 시그니처가 있어야 합니다 <xref:System.Windows.Controls.TextChangedEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="14d76-106">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="14d76-107">사용자 또는 프로그래밍 방식으로 컨트롤의 내용이 변경 될 때마다 이벤트 처리기가 호출 됩니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="14d76-107">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="14d76-108">이 이벤트는 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어지고 처음에 텍스트로 채워질 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d76-108">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="14d76-109">예제</span><span class="sxs-lookup"><span data-stu-id="14d76-109">Example</span></span>

<span data-ttu-id="14d76-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]컨트롤을 정의 하는에서 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 처리기 메서드 이름과 일치 하는 값을 사용 하 여 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d76-110">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="14d76-111">예제</span><span class="sxs-lookup"><span data-stu-id="14d76-111">Example</span></span>

<span data-ttu-id="14d76-112">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]변경 내용을 모니터링 하려는 컨트롤이 포함 된의 코드 숨김이 클래스에서 <xref:System.Windows.Controls.TextBox> 이벤트가 발생할 때마다 호출할 메서드를 삽입 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d76-112">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="14d76-113">이 메서드에는 대리자가 예상 하는 시그니처와 일치 하는 시그니처가 있어야 합니다 <xref:System.Windows.Controls.TextChangedEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="14d76-113">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="14d76-114">사용자 또는 프로그래밍 방식으로 컨트롤의 내용이 변경 될 때마다 이벤트 처리기가 호출 됩니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="14d76-114">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="14d76-115">이 이벤트는 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어지고 처음에 텍스트로 채워질 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="14d76-115">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="14d76-116">주석</span><span class="sxs-lookup"><span data-stu-id="14d76-116">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="14d76-117">참조</span><span class="sxs-lookup"><span data-stu-id="14d76-117">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="14d76-118">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="14d76-118">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="14d76-119">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="14d76-119">RichTextBox Overview</span></span>](richtextbox-overview.md)
