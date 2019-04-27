---
title: '방법: 방사형 그라데이션으로 영역 칠하기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: c3bcc11dea4b1f223f629415591ab03588881dde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921834"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>방법: 방사형 그라데이션으로 영역 칠하기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RadialGradientBrush> 방사형 그라데이션으로 영역 그리기 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.RadialGradientBrush> 노란색에서 빨간색에서 파란색 라임 녹색으로 전환 하는 방사형 그라데이션 사용 하 여 사각형을 그립니다.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 다음 그림에서는 앞의 예제에서 그라데이션을 보여 줍니다. 그라데이션 중지점의 중지를 볼 수 있습니다.  
  
 ![방사형 그라데이션의 그라데이션 중지점](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops")  
  
> [!NOTE]
>  제어점을 설정 하기 위한 기본 좌표계를 사용 하는이 항목의 예제입니다. 기본 좌표계는 경계 상자를 기준으로 합니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다. 설정 하 여이 좌표계를 변경할 수 있습니다 합니다 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성 값을 <xref:System.Windows.Media.BrushMappingMode.Absolute>입니다. 절대 좌표계는 경계 상자를 기준으로 하지 않습니다. 값은 로컬 공간에서 직접 해석됩니다.  
  
 에 대 한 추가 <xref:System.Windows.Media.RadialGradientBrush> 예제를 참조 합니다 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)합니다. 그라데이션 및 브러시의 다른 형식에 대 한 자세한 내용은 참조 하세요. [단색 및 그라데이션 개요 그리기](painting-with-solid-colors-and-gradients-overview.md)합니다.
