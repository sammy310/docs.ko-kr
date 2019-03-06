---
title: '방법: 사용자 지정 컨트롤에서 잉크 지우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365895"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="5d25d-102">방법: 사용자 지정 컨트롤에서 잉크 지우기</span><span class="sxs-lookup"><span data-stu-id="5d25d-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="5d25d-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester> 현재 그린된 스트로크에 다른 스트로크와 교차 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d25d-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="5d25d-104">일부 스트로크를 지울 사용자 수는 컨트롤 만들기에 대 한 유용, 서 사용자 수에 <xref:System.Windows.Controls.InkCanvas> 경우는 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 로 설정 되어 <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>입니다.</span><span class="sxs-lookup"><span data-stu-id="5d25d-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d25d-105">예제</span><span class="sxs-lookup"><span data-stu-id="5d25d-105">Example</span></span>  
 <span data-ttu-id="5d25d-106">다음 예제에서는 사용자가 일부 스트로크를 지울 수 있는 사용자 지정 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d25d-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="5d25d-107">이 예제에는 초기화 될 때 잉크를 포함 하는 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d25d-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="5d25d-108">잉크를 수집 하는 컨트롤을 만들려면 [잉크 입력 컨트롤 만들기](creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="5d25d-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
