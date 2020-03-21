---
title: '방법: 3D 객체의 전면 및 뒷면에 재질을 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112143"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a>방법: 3D 객체의 전면 및 뒷면에 재질을 적용
다음 예제에서는 3D <xref:System.Windows.Media.Media3D.Material> 개체의 앞면과 뒷면에 a를 적용하고 오브젝트에 애니메이션을 적용하여 오브젝트의 양쪽을 표시하는 방법을 보여 주습니다. a의 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D> <xref:System.Windows.Media.Brush> 속성은 객체의 전면에 빨간색을 적용하는 데 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 사용되며, <xref:System.Windows.Media.Media3D.GeometryModel3D> 의 속성은 <xref:System.Windows.Media.Brush> 객체의 뒷면에 파란색을 적용하는 데 사용됩니다. 아래 코드는 개체에 재질을 적용한 것을 보여 주며,  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>예제  
 다음 코드에는 전체 샘플을 보여 줍니다.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [3D 장면 만들기](how-to-create-a-3-d-scene.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
- [3D 장면에서 재질 특성 에 애니메이션](how-to-animate-material-properties-in-a-3-d-scene.md)
- [3D 객체에 방사재 적용](how-to-apply-emissive-material-to-a-3-d-object.md)
