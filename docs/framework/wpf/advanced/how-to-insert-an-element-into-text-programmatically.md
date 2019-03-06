---
title: '방법: 프로그래밍 방식으로 요소를 텍스트에 삽입'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: c93a1c7542a4ddb33b3880de423c256adcc3f1c3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378563"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a>방법: 프로그래밍 방식으로 요소를 텍스트에 삽입
다음 예제에는 두 개 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Documents.TextPointer> 적용할 텍스트 내의 범위를 지정 하는 개체는 <xref:System.Windows.Documents.Span> 요소입니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 아래 그림은 이 예제가 어떻게 보이는지 보여 줍니다.  
  
 ![텍스트 범위에 적용된 Span 요소](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")  
  
## <a name="see-also"></a>참고자료
- [유동 문서 개요](flow-document-overview.md)
