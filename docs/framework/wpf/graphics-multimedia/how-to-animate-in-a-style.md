---
title: 스타일에서 애니메이션 효과를 주는 방법
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 0b29648bf15f0046adcdee610f9565f7deb24972
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744884"
---
# <a name="how-to-animate-in-a-style"></a>스타일에서 애니메이션 효과를 주는 방법

이 예제에서는 스타일의 속성에 애니메이션 효과를 주는 방법을 보여 줍니다. 스타일 내에서 애니메이션 효과를 적용 하는 경우 스타일이 정의 된 프레임 워크 요소만 직접 대상으로 지정할 수 있습니다. Freezable 개체를 대상으로 지정 하려면 스타일이 지정 된 요소의 속성에서 "dot" 여야 합니다.

다음 예제에서는 여러 애니메이션이 스타일 내에서 정의 되 고 <xref:System.Windows.Controls.Button>에 적용 됩니다. 사용자가 단추 위로 마우스를 이동 하면 불투명에서 부분적으로 투명 하 게 그리고 다시 반복 해 서 다시 돌아옵니다. 사용자가 마우스를 단추 밖으로 움직이면 완전히 불투명 하 게 됩니다. 단추를 클릭 하면 배경색이 주황색에서 흰색으로 바뀌고 다시 돌아옵니다. 단추를 그리는 데 사용 되는 <xref:System.Windows.Media.SolidColorBrush>를 직접 대상으로 지정할 수 없으므로 단추의 <xref:System.Windows.Controls.Control.Background%2A> 속성에서 dotting down을 사용 하 여 액세스 합니다.

## <a name="example"></a>예

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

스타일 내에서 애니메이션 효과를 적용 하는 경우 존재 하지 않는 개체를 대상으로 지정할 수 있습니다. 예를 들어 스타일에서 <xref:System.Windows.Media.SolidColorBrush>를 사용 하 여 단추의 배경 속성을 설정 한다고 가정 하지만, 특정 시점에는 스타일이 재정의 되 고 단추의 배경이 <xref:System.Windows.Media.LinearGradientBrush>로 설정 됩니다.  <xref:System.Windows.Media.SolidColorBrush>에 애니메이션을 적용 하려고 하면 예외가 throw 되지 않습니다. 애니메이션은 간단 하 게 자동으로 실패 합니다.

Storyboard 대상 지정 구문에 대 한 자세한 내용은 [Storyboard 개요](storyboards-overview.md)를 참조 하세요. 애니메이션에 대 한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조 하세요. 스타일에 대 한 자세한 내용은 스타일 지정 [및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조 하세요.
