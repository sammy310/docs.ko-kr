---
title: '방법: 3D 객체에 방사재 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112156"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a>방법: 3D 객체에 방사재 적용
다음 예제에서는 기존 <xref:System.Windows.Media.Media3D.EmissiveMaterial> 재질에 색상을 Emissive Material 의 브러시의 색상과 동일한 색상을 추가하는 데 사용하는 방법을 보여 주며 있습니다. 아래 코드는 <xref:System.Windows.Media.Media3D.DiffuseMaterial> <xref:System.Windows.Media.Media3D.EmissiveMaterial> DiffuseMaterial의 모양에 파란색을 추가하기 위해 조합하여 표시하고 적용합니다.  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 절차 코드에서:  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a>예제  
 다음 코드는 XAML의 전체 샘플을 보여 주며,  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a>예제  
 다음은 절차 코드의 전체 샘플입니다.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [3D 장면 만들기](how-to-create-a-3-d-scene.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
- [3D 장면에서 재질 특성 에 애니메이션](how-to-animate-material-properties-in-a-3-d-scene.md)
- [3D 객체의 전면 및 뒷면에 재질 적용](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
