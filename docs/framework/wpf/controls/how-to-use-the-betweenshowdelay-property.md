---
title: '방법: BetweenShowDelay 속성 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: b6d55c72c8264546949833fc086937a8b1fe2540
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139596"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="8b74c-102">방법: BetweenShowDelay 속성 사용</span><span class="sxs-lookup"><span data-stu-id="8b74c-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="8b74c-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 도구 설명 신속 하 게 표시 되도록 속성을 시간-지연 시간을 거의 또는 전혀-사용자 이동 하면 포인터가 하나의 도구 설명에서 간 직접.</span><span class="sxs-lookup"><span data-stu-id="8b74c-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b74c-104">예제</span><span class="sxs-lookup"><span data-stu-id="8b74c-104">Example</span></span>  
 <span data-ttu-id="8b74c-105">다음 예에서 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 속성을 1 초 (1000 밀리초)로 설정 하며 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 모두의 도구 설명에 2 초 (2000 밀리초)로 설정 되어 <xref:System.Windows.Shapes.Ellipse> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="8b74c-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="8b74c-106">타원 중 하나에 대 한 도구 설명을 표시 하 고 다음 마우스 포인터를 이동 다른 타원 일시 중지 하 고 2 초 내에 두 번째 타원의 도구 설명 바로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b74c-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="8b74c-107">다음 시나리오 중 하나에 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 적용, 1 초 표시 되기 전에 두 번째 타원에 대 한 도구 설명 하면:</span><span class="sxs-lookup"><span data-stu-id="8b74c-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="8b74c-108">두 번째 단추를 이동 하는 데 걸리는 시간 이면 2 초 이상.</span><span class="sxs-lookup"><span data-stu-id="8b74c-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="8b74c-109">도구 설명은 첫 번째 타원은 시간 간격의 시작 부분에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b74c-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="8b74c-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="8b74c-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="8b74c-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="8b74c-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="8b74c-112">도구 설명 개요</span><span class="sxs-lookup"><span data-stu-id="8b74c-112">ToolTip Overview</span></span>](tooltip-overview.md)
