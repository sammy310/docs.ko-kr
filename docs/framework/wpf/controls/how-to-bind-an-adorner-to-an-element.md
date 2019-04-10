---
title: '방법: 요소에 표시기(Adorner) 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 54c9e6dfff2bbf7bfabde523b5d6ae5a623fe733
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194723"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="83e28-102">방법: 요소에 표시기(Adorner) 바인딩</span><span class="sxs-lookup"><span data-stu-id="83e28-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="83e28-103">지정 된 표시기를 프로그래밍 방식으로 바인딩하는 방법을 보여 주는이 예제 <xref:System.Windows.UIElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="83e28-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83e28-104">예제</span><span class="sxs-lookup"><span data-stu-id="83e28-104">Example</span></span>  
 <span data-ttu-id="83e28-105">특정에 표시기를 바인딩할 <xref:System.Windows.UIElement>, 다음이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e28-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="83e28-106">호출을 `static` 메서드 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 가져오려고는 <xref:System.Windows.Documents.AdornerLayer> 개체에 대 한는 <xref:System.Windows.UIElement> 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e28-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> <span data-ttu-id="83e28-107">지정 된 시작 하 여 시각적 트리를 차례로 **UIElement**를 찾으면 첫 번째 표시기 계층을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83e28-107">walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="83e28-108">(표시기 계층이 없으면 메서드가 null을 반환합니다.)</span><span class="sxs-lookup"><span data-stu-id="83e28-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="83e28-109">호출 된 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 대상에 표시기를 바인딩할 메서드 **UIElement**합니다.</span><span class="sxs-lookup"><span data-stu-id="83e28-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="83e28-110">다음 예제에서는 바인딩합니다 (위)에 <xref:System.Windows.Controls.TextBox> 라는 *myTextBox*합니다.</span><span class="sxs-lookup"><span data-stu-id="83e28-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="83e28-111">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용하여 표시기를 다른 요소에 바인딩하는 것은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83e28-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e28-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="83e28-112">See also</span></span>

- [<span data-ttu-id="83e28-113">표시기 개요</span><span class="sxs-lookup"><span data-stu-id="83e28-113">Adorners Overview</span></span>](adorners-overview.md)
