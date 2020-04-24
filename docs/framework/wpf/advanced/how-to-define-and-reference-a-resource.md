---
title: '방법: 리소스 정의 및 참조'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: e33c86b03d8b18113f3a15b3ab251753958ff5b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646505"
---
# <a name="how-to-define-and-reference-a-resource"></a>방법: 리소스 정의 및 참조

이 예제에서는 에서 특성을 사용하여 리소스를 정의하고 참조하는 방법을 보여 주며 있습니다. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]

## <a name="example"></a>예제

다음 예제에서는 리소스와 여러 <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Style> 리소스의 두 가지 유형의 리소스를 정의합니다. <xref:System.Windows.Media.SolidColorBrush> 리소스는 `MyBrush` 각각 형식 값을 사용하는 여러 속성의 <xref:System.Windows.Media.Brush> 값을 제공하는 데 사용됩니다. <xref:System.Windows.Style> 리소스 `PageBackground`및 `TitleText` `Label` 각 대상 특정 컨트롤 형식입니다. 스타일은 해당 스타일 리소스가 리소스 키에서 참조되고 에 정의된 여러 특정 컨트롤 요소의 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 설정하는 데 사용되는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]경우 대상 컨트롤에서 다양한 속성을 설정합니다.

`Label` 스타일 의 setter 내의 속성 중 하나는 앞에서 `MyBrush` 정의한 리소스를 참조합니다. 이는 일반적인 기술이지만 리소스가 지정된 순서대로 리소스 사전에 구문 분석되고 입력된다는 점을 기억하는 것이 중요합니다. [또한 StaticResource 마크업 확장을](staticresource-markup-extension.md) 사용하여 다른 리소스 내에서 리소스를 참조하는 경우 사전 내에 있는 순서에 의해 리소스가 요청됩니다. 참조하는 리소스가 해당 리소스가 요청된 위치보다 리소스 컬렉션 내에서 더 일찍 정의된지 확인합니다. 필요한 경우 [DynamicResource 마크업 확장을](dynamicresource-markup-extension.md) 사용하여 런타임에 리소스를 참조하여 리소스 참조의 엄격한 생성 순서를 해결할 수 있지만 이 DynamicResource 기술에는 성능 이 결과가 있다는 점에 유의해야 합니다. 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하십시오.

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>참고 항목

- [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
