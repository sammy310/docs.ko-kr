---
title: '방법: Viewport3D의 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 54d3ee859a50ed348308b083c48f2dd73d312bbe
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106935"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="1aa7c-102">방법: Viewport3D의 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="1aa7c-102">How to: Hit Test in a Viewport3D</span></span>
<span data-ttu-id="1aa7c-103">이 예제에서는에서 3D 시각적 개체에 대 한 적중 테스트 <xref:System.Windows.Controls.Viewport3D>를 진행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1aa7c-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>  
  
 <span data-ttu-id="1aa7c-104">는 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2d 및 3d 정보를 반환 하기 때문에 테스트 결과를 반복 하 여 3d 결과만 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa7c-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <span data-ttu-id="1aa7c-105">다음 <xref:System.Windows.Media.HitTestResultBehavior> 코드의는 적중 테스트 결과를 처리 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa7c-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span>  <span data-ttu-id="1aa7c-106">`UpdateResultInfo`및 `UpdateMaterial` 은 로컬로 정의 된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa7c-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
 
