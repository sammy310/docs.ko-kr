---
title: UI 자동화를 사용하여 텍스트 찾기 및 강조
description: UI 자동화를 사용 하 여 텍스트를 찾고 강조 표시 합니다. 예제는 텍스트 컨트롤 내용 내에서 각 문자열을 검색 하 고 강조 표시 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: 7ae933bdf12c81e48371fa89ba5fc5cf5dd4731e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276466"
---
# <a name="find-and-highlight-text-using-ui-automation"></a>UI 자동화를 사용하여 텍스트 찾기 및 강조

> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
 이 항목에서는를 사용 하 여 텍스트 컨트롤의 내용 내에서 문자열의 각 항목을 순차적으로 검색 하 고 강조 표시 하는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .  
  
## <a name="example"></a>예제  

 다음 예제에서는 <xref:System.Windows.Automation.TextPattern> 텍스트 컨트롤에서 개체를 가져옵니다. <xref:System.Windows.Automation.Text.TextPatternRange>그러면이의 속성을 사용 하 여 전체 문서의 텍스트 콘텐츠를 나타내는 개체가 만들어집니다 <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> <xref:System.Windows.Automation.TextPattern> . <xref:System.Windows.Automation.Text.TextPatternRange>순차 검색 및 강조 표시 기능을 위해 두 개의 추가 개체가 생성 됩니다.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>참고 항목

- [UI 자동화를 사용하여 텍스트 찾기 및 강조](find-and-highlight-text-using-ui-automation.md)
