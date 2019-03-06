---
title: '방법: 단순 바인딩 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 157060e784e4169ac8e31c6028ed65f0a9568e0f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373584"
---
# <a name="how-to-create-a-simple-binding"></a>방법: 단순 바인딩 만들기
이 예제에서는 간단한을 만드는 방법을 보여 줍니다. <xref:System.Windows.Data.Binding>합니다.  
  
## <a name="example"></a>예제  
 이 예제는 `Person` 이라는 문자열 속성을 사용 하 여 개체 `PersonName`합니다. 합니다 `Person` 개체가 이라는 네임 스페이스에 정의 된 `SDKSample`합니다.  
  
 포함 하는 강조 표시 된 줄을 `<src>` 다음 예제에서 요소를 인스턴스화하는 `Person` 개체를 `PersonName` 속성 값 `Joe`합니다. 이렇게 합니다 `Resources` 섹션 및 할당을 `x:Key`합니다.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 포함 하는 강조 표시 된 줄을 `<TextBlock>` 바인딩합니다 요소를 <xref:System.Windows.Controls.TextBlock> 컨트롤을 `PersonName` 속성. 결과적으로 <xref:System.Windows.Controls.TextBlock> "Joe" 값으로 나타납니다.  
  
## <a name="see-also"></a>참고자료
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
