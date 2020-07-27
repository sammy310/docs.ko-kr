---
title: '방법: 종속성 속성 구현'
description: DependencyProperty 필드를 사용 하 여 공용 언어 런타임 속성을 백업 하 여 Windows Presentation Foundation에서 종속성 속성을 정의 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165093"
---
# <a name="how-to-implement-a-dependency-property"></a>방법: 종속성 속성 구현
이 예제에서는 필드를 사용 하 여 CLR (공용 언어 런타임) 속성을 백업 하는 방법을 보여 줍니다 <xref:System.Windows.DependencyProperty> . 따라서 종속성 속성을 정의 합니다. 고유 속성을 정의하고 스타일, 데이터 바인딩, 상속, 애니메이션 및 기본값을 포함한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능의 여러 측면을 지원하려면 해당 속성을 종속성 속성으로 구현해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 먼저 메서드를 호출 하 여 종속성 속성을 등록 합니다 <xref:System.Windows.DependencyProperty.Register%2A> . 종속성 속성의 이름과 특성을 저장 하는 데 사용 하는 식별자 필드의 이름은 <xref:System.Windows.DependencyProperty.Name%2A> 호출의 일부로 종속성 속성에 대해 선택한입니다 <xref:System.Windows.DependencyProperty.Register%2A> . 이때 리터럴 문자열을 추가 해야 합니다 `Property` . 예를 들어의를 사용 하 여 종속성 속성을 등록 하는 경우 <xref:System.Windows.DependencyProperty.Name%2A> `Location` 종속성 속성에 대해 정의 하는 식별자 필드의 이름을로 지정 해야 합니다 `LocationProperty` .  
  
 이 예제에서 종속성 속성의 이름과 CLR 접근자는입니다. 식별자 필드는이 고, `State` `StateProperty` 속성의 형식은이 고, <xref:System.Boolean> 종속성 속성을 등록 하는 형식은입니다 `MyStateControl` .  
  
 이 명명 패턴을 따르지 못한 경우 디자이너가 속성을 제대로 보고하지 않을 수 있으며 속성 시스템 스타일 애플리케이션의 특정 측면이 예상대로 작동하지 않을 수 있습니다.  
  
 종속성 속성에 대한 기본 메타데이터를 지정할 수도 있습니다. 이 예제에서는 `State` 종속성 속성의 기본값이 `false`로 등록됩니다.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 종속성 속성을 구현 하는 방법과 이유에 대 한 자세한 내용은 전용 필드를 사용 하 여 CLR 속성을 백업 하는 것과는 달리 [종속성 속성 개요](dependency-properties-overview.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [종속성 속성 개요](dependency-properties-overview.md)
- [방법 항목](properties-how-to-topics.md)
