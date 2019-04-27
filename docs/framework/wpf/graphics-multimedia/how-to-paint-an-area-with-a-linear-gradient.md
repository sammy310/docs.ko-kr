---
title: '방법: 선형 그라데이션으로 영역 칠하기'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921919"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>방법: 선형 그라데이션으로 영역 칠하기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.LinearGradientBrush> 선형 그라데이션으로 영역 그리기 클래스입니다. 다음 예제에서는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 노란색에서 빨간색에서 파란색 라임 녹색으로 전환 하는 대각선 선형 그라데이션을 사용 하 여 그려집니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![대각선 선형 그라데이션](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 가로 선형 그라데이션 만들기, 변경 된 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 의 <xref:System.Windows.Media.LinearGradientBrush> (0, 0.5)에 (1, 0.5) 및 합니다. 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 가로 선형 그라데이션을 사용 하 여 그려집니다.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![가로 선형 그라데이션의](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 세로 선형 그라데이션 만들기, 변경 된 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 의 <xref:System.Windows.Media.LinearGradientBrush> (0.5, 0)을 (0.5, 1) 및 합니다. 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 세로 선형 그라데이션을 사용 하 여 그려집니다.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.  
  
 ![세로 선형 그라데이션](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  이 항목의 예제는 시작점 및 끝점 설정에 대 한 기본 좌표계를 사용 합니다. 기본 좌표계는 경계 상자를 기준으로 합니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다. 설정 하 여이 좌표계를 변경할 수 있습니다 합니다 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성 값을 <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>입니다. 절대 좌표계는 경계 상자를 기준으로 하지 않습니다. 값은 로컬 공간에서 직접 해석됩니다.  
  
 추가 예제를 보려면 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)합니다. 그라데이션 및 브러시의 다른 형식에 대 한 자세한 내용은 참조 하세요. [단색 및 그라데이션 개요 그리기](painting-with-solid-colors-and-gradients-overview.md)합니다.
