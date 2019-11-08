---
title: '방법: 계층적 XML 데이터에 마스터-세부 패턴 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733421"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>방법: 계층적 XML 데이터에 마스터-세부 패턴 사용
이 예제에서는 XML 데이터를 사용 하 여 마스터-세부 시나리오를 구현 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예는 [계층적 데이터에 마스터-세부 패턴 사용](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)에 설명 된 예제의 XML 데이터 버전입니다. 이 예제에서 데이터는 `League.xml`파일에서 가져온 것입니다. 세 번째 <xref:System.Windows.Controls.ListBox> 컨트롤이 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 속성에 바인딩하여 두 번째 <xref:System.Windows.Controls.ListBox>의 선택 변경 내용을 추적 하는 방법을 확인 합니다.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.HierarchicalDataTemplate>
- [방법 항목](data-binding-how-to-topics.md)
