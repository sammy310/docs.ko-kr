---
title: '방법: 그라데이션에 시스템 색 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 55c99640907a0c372f8c7bbc50b9b45c9f15ef3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769241"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="013e2-102">방법: 그라데이션에 시스템 색 사용</span><span class="sxs-lookup"><span data-stu-id="013e2-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="013e2-103">그라데이션에 시스템 색을 사용 하려면 사용 합니다  *\<SystemColor >* 색 및  *\<SystemColor >* ColorKey 정적 속성의를 <xref:System.Windows.SystemColors> 가져오려고 클래스를 색에 대 한 참조 위치  *\<SystemColor >* 원하는 시스템 색의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="013e2-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="013e2-104">사용 된  *\<SystemColor >* ColorKey 속성 시스템 테마가 변경 될 때 자동으로 업데이트 되는 동적 참조를 만들려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="013e2-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="013e2-105">그렇지 않은 경우 사용 합니다  *\<SystemColor >* Color 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="013e2-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="013e2-106">예제</span><span class="sxs-lookup"><span data-stu-id="013e2-106">Example</span></span>  
 <span data-ttu-id="013e2-107">다음 예제에서는 동적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="013e2-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="013e2-108">그 다음 예제에서는 정적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="013e2-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="013e2-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="013e2-109">See also</span></span>

- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="013e2-110">시스템 브러시로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="013e2-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="013e2-111">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="013e2-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
