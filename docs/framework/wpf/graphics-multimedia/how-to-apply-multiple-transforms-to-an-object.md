---
title: '방법: 개체에 다중 변환 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 3ef11104b2a4fc775d29d2a388c9a70a69a3f10f
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112117"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="53831-102">방법: 개체에 다중 변환 적용</span><span class="sxs-lookup"><span data-stu-id="53831-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="53831-103">이 예제에서는 두 <xref:System.Windows.Media.TransformGroup> 개 이상의 <xref:System.Windows.Media.Transform> 개체를 단일 복합체로 <xref:System.Windows.Media.Transform>그룹화하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53831-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53831-104">예제</span><span class="sxs-lookup"><span data-stu-id="53831-104">Example</span></span>  
 <span data-ttu-id="53831-105">다음 예제에서는 <xref:System.Windows.Media.TransformGroup> <xref:System.Windows.Media.ScaleTransform> a와 a를 <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Controls.Button>에 적용하기 위해 을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="53831-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="53831-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53831-106">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [<span data-ttu-id="53831-107">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="53831-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="53831-108">2D 변환 샘플</span><span class="sxs-lookup"><span data-stu-id="53831-108">2D Transforms Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
