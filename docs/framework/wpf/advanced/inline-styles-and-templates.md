---
title: 인라인 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460012"
---
# <a name="inline-styles-and-templates"></a>인라인 스타일 및 템플릿
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 여러 번 사용할 수 있도록 리소스에서 요소의 시각적 모양을 정의 하는 방법으로 <xref:System.Windows.Style> 개체 및 템플릿 개체 (<xref:System.Windows.FrameworkTemplate> 서브 클래스)를 제공 합니다. 이러한 이유로 <xref:System.Windows.Style> 및 <xref:System.Windows.FrameworkTemplate> 형식을 사용 하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성은 거의 항상 새 항목을 인라인으로 정의 하지 않고 기존 스타일 및 템플릿에 대 한 리소스 참조를 만듭니다.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>인라인 스타일 및 템플릿의 제한 사항  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 스타일 및 템플릿 속성은 기술적으로 두 가지 방법 중 하나로 설정할 수 있습니다. 특성 구문을 사용 하 여 리소스 내에 정의 된 스타일을 참조할 수 있습니다. 예를 들어 `<`*개체*`Style="{StaticResource`*myResourceKey*`}" .../>`합니다. 또는 속성 요소 구문을 사용 하 여 인라인 스타일을 정의할 수 있습니다. 예를 들면 다음과 같습니다.  
  
 `<` *개체* `>`  
  
 `<` *개체* `.Style>`  
  
 `<` `Style``.../>`  
  
 `</` *개체* `.Style>`  
  
 `</` *개체* `>`  
  
 특성 사용은 훨씬 더 일반적입니다. 인라인으로 정의 되 고 리소스에 정의 되지 않은 스타일은 반드시 포함 하는 요소로만 범위가 지정 되며 리소스 키가 없기 때문에 쉽게 다시 사용할 수 없습니다. 일반적으로 리소스 정의 스타일은 더 다양 하 고 유용 하며, 코드에서 프로그램 논리를 태그 디자인 으로부터 분리 하는 일반적인 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 프로그래밍 모델 원칙을 유지 하는 것이 더 좋습니다.  
  
 일반적으로 스타일 또는 템플릿 인라인을 설정 하는 이유는 해당 위치에서 해당 스타일이 나 템플릿만 사용 하려는 경우에도 마찬가지입니다. 스타일이 나 템플릿을 사용할 수 있는 대부분의 요소는 콘텐츠 속성과 콘텐츠 모델도 지원 합니다. 스타일 지정 또는 템플릿을 한 번만 사용 하 여 만든 논리 트리를 사용 하는 경우에는 직접 태그에서 해당 하는 자식 요소를 사용 하 여 해당 콘텐츠 속성을 간단 하 게 채울 수 있습니다. 이는 스타일 및 템플릿 메커니즘을 모두 무시 합니다.  
  
 개체를 반환 하는 태그 확장에서 사용 하도록 설정 된 다른 구문은 스타일 및 템플릿에도 사용할 수 있습니다. 가능한 시나리오의 두 확장에는 [TemplateBinding](templatebinding-markup-extension.md) 및 <xref:System.Windows.Data.Binding>가 있습니다.  
  
## <a name="see-also"></a>참조

- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
