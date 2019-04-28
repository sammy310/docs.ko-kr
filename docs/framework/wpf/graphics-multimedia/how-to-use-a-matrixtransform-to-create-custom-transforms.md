---
title: '방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769267"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="02dcb-102">방법: MatrixTransform을 사용하여 사용자 지정 변환 만들기</span><span class="sxs-lookup"><span data-stu-id="02dcb-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="02dcb-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MatrixTransform> 변환 (이동) 하는 위치 늘이기, 및의 기울이기는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02dcb-104">사용 합니다 <xref:System.Windows.Media.MatrixTransform> 클래스에서 제공 하지 않는 사용자 지정 변환을 만들 수는 <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, 또는 <xref:System.Windows.Media.TranslateTransform> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02dcb-105">예제</span><span class="sxs-lookup"><span data-stu-id="02dcb-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="02dcb-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="02dcb-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="02dcb-107">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="02dcb-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="02dcb-108">방법 항목</span><span class="sxs-lookup"><span data-stu-id="02dcb-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="02dcb-109">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="02dcb-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
