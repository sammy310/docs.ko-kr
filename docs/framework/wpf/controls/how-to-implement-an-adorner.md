---
title: '방법: 표시기(Adorner) 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120811"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="fb033-102">방법: 표시기(Adorner) 구현</span><span class="sxs-lookup"><span data-stu-id="fb033-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="fb033-103">이 예제에서는 최소 표시기 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb033-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="fb033-104">구현자 참고 사항</span><span class="sxs-lookup"><span data-stu-id="fb033-104">Notes for Implementers</span></span>  
 <span data-ttu-id="fb033-105">표시기에는 고유 렌더링 동작이 포함되어 있지 않음에 유의해야 합니다. 표시기를 렌더링하는 것은 표시기 구현자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="fb033-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="fb033-106">렌더링 동작을 구현 하는 일반적인 방법은 재정의 하는 것을 <xref:System.Windows.UIElement.OnRender%2A> 메서드 및 사용법 하나 이상의 <xref:System.Windows.Media.DrawingContext> (이 예제 에서처럼) 필요에 따라 표시기의 시각적 개체를 렌더링 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fb033-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb033-107">예제</span><span class="sxs-lookup"><span data-stu-id="fb033-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fb033-108">설명</span><span class="sxs-lookup"><span data-stu-id="fb033-108">Description</span></span>  
 <span data-ttu-id="fb033-109">추상에서 상속 되는 클래스를 구현 하 여 사용자 지정 표시기 만들어집니다 <xref:System.Windows.Documents.Adorner> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fb033-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="fb033-110">표시기 예제에서는의 모서리를 원으로 간단히 표시를 <xref:System.Windows.UIElement> 재정의 하 여 원으로 <xref:System.Windows.UIElement.OnRender%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fb033-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fb033-111">코드</span><span class="sxs-lookup"><span data-stu-id="fb033-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="fb033-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb033-112">See also</span></span>

- [<span data-ttu-id="fb033-113">표시기 개요</span><span class="sxs-lookup"><span data-stu-id="fb033-113">Adorners Overview</span></span>](adorners-overview.md)
