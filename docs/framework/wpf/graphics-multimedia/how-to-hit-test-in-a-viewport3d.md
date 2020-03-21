---
title: '방법: Viewport3D의 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D visuals [WPF], hit-testing for
- hit tests [WPF], for 3D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 34bc86349332293e40aca5743cbabb2a48634da6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112091"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="1338d-102">방법: Viewport3D의 적중 테스트</span><span class="sxs-lookup"><span data-stu-id="1338d-102">How to: Hit Test in a Viewport3D</span></span>

<span data-ttu-id="1338d-103">이 예제에서는 <xref:System.Windows.Controls.Viewport3D>에서 3D 시각적 개체에 대한 테스트를 누르는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1338d-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>

<span data-ttu-id="1338d-104">2D 및 3D 정보를 반환하기 때문에 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 테스트 결과를 반복하여 3D 결과만 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1338d-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

<span data-ttu-id="1338d-105">다음 <xref:System.Windows.Media.HitTestResultBehavior> 코드에서는 적중 테스트 결과가 처리되는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1338d-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span> <span data-ttu-id="1338d-106">`UpdateResultInfo``UpdateMaterial` 로컬로 정의된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1338d-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
