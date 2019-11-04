---
title: '방법: 3차원 모델에 그리기 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459375"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>방법: 3차원 모델에 그리기 적용

이 예에서는 <xref:System.Windows.Media.DrawingBrush>을 3 차원 모델에 적용 된 <xref:System.Windows.Media.Media3D.Material> 사용 하는 방법을 보여 줍니다.

다음 코드는 <xref:System.Windows.Media.DrawingGroup>를 <xref:System.Windows.Media.DrawingBrush>의 콘텐츠로 정의 합니다.  <xref:System.Windows.Media.DrawingBrush>은 3 차원 평면에 적용 되는 <xref:System.Windows.Media.Media3D.DiffuseMaterial>의 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> 속성으로 설정 됩니다.

> [!NOTE]
> 코드를 다시 사용 하 고 단순화할 수 있는 리소스로 아래 드로잉과 같이 복잡 한 개체 및 값을 정의 하는 것이 좋습니다. 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md) 를 참조 하세요.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>예제

다음 코드에서는 전체 샘플을 보여 줍니다.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>참조

- [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [3차원 장면 만들기](how-to-create-a-3-d-scene.md)
- [Drawing 개체 개요](drawing-objects-overview.md)
- [3차원 그래픽 개요](3-d-graphics-overview.md)
