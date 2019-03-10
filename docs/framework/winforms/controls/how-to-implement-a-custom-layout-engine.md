---
title: '방법: 사용자 지정 레이아웃 엔진 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: 2b5bdab243039014b42d2f57f4037833f2137d67
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702635"
---
# <a name="how-to-implement-a-custom-layout-engine"></a><span data-ttu-id="95f42-102">방법: 사용자 지정 레이아웃 엔진 구현</span><span class="sxs-lookup"><span data-stu-id="95f42-102">How to: Implement a Custom Layout Engine</span></span>
<span data-ttu-id="95f42-103">다음 코드 예제에서는 간단한 선형 레이아웃을 수행 하는 사용자 지정 레이아웃 엔진을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95f42-103">The following code example demonstrates how to create a custom layout engine that performs a simple flow layout.</span></span> <span data-ttu-id="95f42-104">라는 패널 컨트롤을 구현 `DemoFlowPanel`를 재정의 하는 <xref:System.Windows.Forms.Control.LayoutEngine%2A> 의 인스턴스를 제공 하는 속성은 `DemoFlowLayout` 클래스.</span><span class="sxs-lookup"><span data-stu-id="95f42-104">It implements a panel control named `DemoFlowPanel`, which overrides the <xref:System.Windows.Forms.Control.LayoutEngine%2A> property to provide an instance of the `DemoFlowLayout` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95f42-105">예제</span><span class="sxs-lookup"><span data-stu-id="95f42-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="95f42-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="95f42-106">See also</span></span>
- <xref:System.Windows.Forms.Layout.LayoutEngine>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
