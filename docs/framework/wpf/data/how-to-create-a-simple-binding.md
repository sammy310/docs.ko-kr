---
title: '방법: 단순 바인딩 만들기'
description: Windows Presentation Foundation (WPF)에서이 방법 예제를 통해 응용 프로그램에 대 한 간단한 바인딩을 만듭니다.
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618703"
---
# <a name="how-to-create-a-simple-binding"></a>방법: 단순 바인딩 만들기
이 예제에서는 간단한을 만드는 방법을 보여 줍니다 <xref:System.Windows.Data.Binding> .  
  
## <a name="example"></a>예제  
 이 예제에서는 `Person` 라는 문자열 속성이 있는 개체가 있습니다 `PersonName` . `Person`개체는 라는 네임 스페이스에 정의 됩니다 `SDKSample` .  
  
 다음 예제에서 요소를 포함 하는 강조 표시 된 줄은 `<src>` `Person` `PersonName` 의 속성 값을 사용 하 여 개체를 인스턴스화합니다 `Joe` . 이 작업은 섹션에서 수행 되 `Resources` 고가 할당 됩니다 `x:Key` .  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 요소를 포함 하는 강조 표시 된 줄은 `<TextBlock>` <xref:System.Windows.Controls.TextBlock> 컨트롤을 속성에 바인딩합니다 `PersonName` . 그 결과 <xref:System.Windows.Controls.TextBlock> "Joe" 값이 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 도움말 항목](data-binding-how-to-topics.md)
