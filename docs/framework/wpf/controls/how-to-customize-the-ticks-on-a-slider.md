---
title: '방법: 슬라이더의 틱 사용자 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 438bd8aca4b44bc449415dc2b9a0ff2036d14eb5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368114"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="4b97e-102">방법: 슬라이더의 틱 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4b97e-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="4b97e-103">만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Slider> 눈금이 있는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b97e-104">예제</span><span class="sxs-lookup"><span data-stu-id="4b97e-104">Example</span></span>  
 <span data-ttu-id="4b97e-105"><xref:System.Windows.Controls.Primitives.TickBar> 설정 하는 경우 표시는 <xref:System.Windows.Controls.Slider.TickPlacement%2A> 이외의 값으로 속성을 <xref:System.Windows.Controls.Primitives.TickPlacement.None>, 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="4b97e-106">다음 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Slider> 사용 하 여는 <xref:System.Windows.Controls.Primitives.TickBar> 는 눈금을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="4b97e-107">합니다 <xref:System.Windows.Controls.Slider.TickPlacement%2A> 고 <xref:System.Windows.Controls.Slider.TickFrequency%2A> 속성 눈금 표시 및 간격의 위치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="4b97e-108">이동 하는 경우는 <xref:System.Windows.Controls.Primitives.Thumb>, 도구 설명의 값을 표시 합니다 <xref:System.Windows.Controls.Slider>합니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="4b97e-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> 속성은 도구 설명이 발생할 위치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="4b97e-110">합니다 <xref:System.Windows.Controls.Primitives.Thumb> 있기 때문에 눈금의 위치로 이동 일치 <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> 로 설정 된 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="4b97e-111">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Controls.Slider.Ticks%2A> 속성을 따라 눈금을 만드는 <xref:System.Windows.Controls.Slider> 불규칙 한 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="4b97e-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4b97e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b97e-112">See also</span></span>
- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- <span data-ttu-id="4b97e-113">[방법: 속성 값을 슬라이더 바인딩합니다](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4b97e-113">[How to: Bind a Slider to a Property Value](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span></span>
