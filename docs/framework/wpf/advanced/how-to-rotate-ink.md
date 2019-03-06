---
title: '방법: 잉크 회전'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], rotating
- rotating ink [WPF]
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
ms.openlocfilehash: 31f5d0ffb6f0fdcdaef13bc44653f8c7938ac7f3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378799"
---
# <a name="how-to-rotate-ink"></a><span data-ttu-id="1ef7a-102">방법: 잉크 회전</span><span class="sxs-lookup"><span data-stu-id="1ef7a-102">How to: Rotate Ink</span></span>
## <a name="example"></a><span data-ttu-id="1ef7a-103">예제</span><span class="sxs-lookup"><span data-stu-id="1ef7a-103">Example</span></span>  
 <span data-ttu-id="1ef7a-104">잉크를 복사 하는 다음 예제는 <xref:System.Windows.Controls.InkCanvas> 에 <xref:System.Windows.Controls.Canvas> 를 포함 하는 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef7a-104">The following example copies the ink from an <xref:System.Windows.Controls.InkCanvas> to a <xref:System.Windows.Controls.Canvas> that contains an <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="1ef7a-105">응용 프로그램은 잉크를 복사할 때이 잉크를 회전 90도 시계 방향으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef7a-105">When the application copies the ink, it also rotates the ink 90 degrees clockwise.</span></span>  
  
 [!code-xaml[HowToRotateInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="1ef7a-106">예제</span><span class="sxs-lookup"><span data-stu-id="1ef7a-106">Example</span></span>  
 <span data-ttu-id="1ef7a-107">다음 예제는 사용자 지정 <xref:System.Windows.Documents.Adorner> 에 스트로크를 회전 하는 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef7a-107">The following example is a custom <xref:System.Windows.Documents.Adorner> that rotates the strokes on an <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[AdornerForStrokes#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 <span data-ttu-id="1ef7a-108">다음 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 파일을 <xref:System.Windows.Controls.InkPresenter> 잉크도 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="1ef7a-108">The following example is a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that defines an <xref:System.Windows.Controls.InkPresenter> and populates it with ink.</span></span> <span data-ttu-id="1ef7a-109">합니다 `Window_Loaded` 사용자 지정 표시기를 추가 하는 이벤트 처리기는 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef7a-109">The `Window_Loaded` event handler adds the custom adorner to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-xaml[AdornerForStrokes#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
