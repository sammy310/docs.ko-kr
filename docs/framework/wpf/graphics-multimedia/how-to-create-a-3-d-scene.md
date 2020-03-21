---
title: '방법: 3D 장면 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112104"
---
# <a name="how-to-create-a-3d-scene"></a>방법: 3D 장면 만들기
이 예제에서는 회전된 평평한 용지처럼 보이는 3D 객체를 만드는 방법을 보여 주어 있습니다. A는 <xref:System.Windows.Controls.Viewport3D> 다음 구성 요소와 함께 이 간단한 3D 장면을 만드는 데 사용됩니다.  
  
- 카메라를 사용하여 <xref:System.Windows.Media.Media3D.PerspectiveCamera>만들어집니다. 카메라는 3D 장면의 어떤 부분을 볼 수 있는지 지정합니다.  
  
- 의 속성을 사용하여 3D 객체(용지)의 모양을 지정하기 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 위해 <xref:System.Windows.Media.Media3D.GeometryModel3D>메시가 작성됩니다.  
  
- 의 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 속성을 사용하여 오브젝트 의 표면에 표시하도록 재질이 지정됩니다(이 샘플의 선형 <xref:System.Windows.Media.Media3D.GeometryModel3D>그라데이션).  
  
- 을 사용하여 <xref:System.Windows.Media.Media3D.DirectionalLight>오브젝트에 빛을 비추는 라이트가 만들어집니다.  
  
## <a name="example"></a>예제  
 아래 코드는 XAML에서 3D 장면을 만드는 방법을 보여 주며, 이 에 대한 설명입니다.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>예제  
 아래 코드는 절차 코드에서 동일한 3D 장면을 만드는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [3D 그래픽 개요](3-d-graphics-overview.md)
