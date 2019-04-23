---
title: '방법: 종속성 속성 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: e2f18cb3941be2ebf4315a844c05b91ff49c6aa2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223803"
---
# <a name="how-to-implement-a-dependency-property"></a>방법: 종속성 속성 구현
백업 하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성을 <xref:System.Windows.DependencyProperty> 필드, 따라서 종속성 속성을 정의 합니다. 고유 속성을 정의하고 스타일, 데이터 바인딩, 상속, 애니메이션 및 기본값을 포함한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능의 여러 측면을 지원하려면 해당 속성을 종속성 속성으로 구현해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 호출 하 여 종속성 속성을 먼저 등록을 <xref:System.Windows.DependencyProperty.Register%2A> 메서드. 사용 하 여 이름을 저장 하 고 종속성 속성의 특성 이어야 합니다 하는 식별자 필드의 이름을 합니다 <xref:System.Windows.DependencyProperty.Name%2A> 의 일부로 종속성 속성에 대해 선택한는 <xref:System.Windows.DependencyProperty.Register%2A> 호출, 리터럴 문자열에 의해 추가 된 `Property`합니다. 예를 들어 사용 하 여 종속성 속성을 등록 하는 경우는 <xref:System.Windows.DependencyProperty.Name%2A> 의 `Location`, 종속성 속성에 대해 정의한 식별자 필드의 이름은 다음 `LocationProperty`합니다.  
  
 이 예제에서는 종속성 속성의 이름 및 해당 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 접근자가 `State`; 식별자 필드는 `StateProperty`; 속성의 형식은 <xref:System.Boolean>; 종속성 속성을 등록 하는 형식은 이며 `MyStateControl`합니다.  
  
 이 명명 패턴을 따르지 못한 경우 디자이너가 속성을 제대로 보고하지 않을 수 있으며 속성 시스템 스타일 애플리케이션의 특정 측면이 예상대로 작동하지 않을 수 있습니다.  
  
 종속성 속성에 대한 기본 메타데이터를 지정할 수도 있습니다. 이 예제에서는 `State` 종속성 속성의 기본값이 `false`로 등록됩니다.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 개인 필드가 있는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성을 단지 백업하는 것과는 반대로 종속성 속성을 구현하는 방법과 이유에 대한 자세한 내용은 [종속성 속성 개요](dependency-properties-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [종속성 속성 개요](dependency-properties-overview.md)
- [방법 항목](properties-how-to-topics.md)
