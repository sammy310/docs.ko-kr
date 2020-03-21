---
title: '방법: 3D 모델의 배율 변환'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111987"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>방법: 3D 모델의 배율 변환
이 예제에서는 3D 개체의 배율을 조정하는 방법을 보여 주습니다. 3D 개체의 배율을 <xref:System.Windows.Media.Media3D.ScaleTransform3D>조정하려면 을 사용합니다. <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>및 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 속성은 지정한 요소별로 요소의 크기를 조정합니다. 예를 들어 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 값이 1.5이면 객체가 원래 너비의 150%까지 늘어날 수 있습니다. <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 값이 0.5이면 개체의 높이가 50% 줄어듭니다. 아래 코드는 <xref:System.Windows.Media.Media3D.ScaleTransform3D> <xref:System.Windows.Media.Media3D.GeometryModel3D>에 대한 변환으로 를 사용하는 것을 보여 주며.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>예제  
 다음 코드에는 전체 샘플을 보여 줍니다.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [3D 번역 애니메이션](how-to-animate-3-d-translations.md)
- [3D 장면 만들기](how-to-create-a-3-d-scene.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
