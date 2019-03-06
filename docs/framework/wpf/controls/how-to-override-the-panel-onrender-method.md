---
title: '방법: Panel의 OnRender 메서드 재정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: cefeee320e10a9e9de0d38894d4d865ca2e639ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368956"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="8840f-102">방법: Panel의 OnRender 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="8840f-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="8840f-103">재정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Panel.OnRender%2A> 메서드의 <xref:System.Windows.Controls.Panel> 레이아웃 요소를 사용자 지정 그래픽 효과 추가 하려면.</span><span class="sxs-lookup"><span data-stu-id="8840f-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8840f-104">예제</span><span class="sxs-lookup"><span data-stu-id="8840f-104">Example</span></span>  
 <span data-ttu-id="8840f-105">사용 된 <xref:System.Windows.Controls.Panel.OnRender%2A> 그래픽 효과 렌더링된 panel 요소를 추가 하기 위해 메서드.</span><span class="sxs-lookup"><span data-stu-id="8840f-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="8840f-106">예를 들어, 사용자 지정 테두리 또는 배경 효과 추가 하려면이 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8840f-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="8840f-107"><xref:System.Windows.Media.DrawingContext> 개체는 도형, 텍스트, 이미지 또는 비디오를 그리기 위한 메서드를 제공 하는 인수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8840f-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="8840f-108">결과적으로,이 메서드는 패널 개체의 사용자 지정에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8840f-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8840f-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="8840f-109">See also</span></span>
- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="8840f-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="8840f-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="8840f-111">사용자 지정 방사형 패널 샘플</span><span class="sxs-lookup"><span data-stu-id="8840f-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)
- [<span data-ttu-id="8840f-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="8840f-112">How-to Topics</span></span>](panel-how-to-topics.md)
