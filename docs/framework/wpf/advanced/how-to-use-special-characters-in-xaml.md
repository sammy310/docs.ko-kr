---
title: '방법: XAML에서 특수 문자 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 18934e06f45ca4b88f48bce8a310a07b460a5f53
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377965"
---
# <a name="how-to-use-special-characters-in-xaml"></a>방법: XAML에서 특수 문자 사용
마크업 파일에서 만든 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 에 자동으로 저장 됩니다는 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] utf-8 파일 형식 이므로 악센트 부호와 같은 대부분의 특수 문자가 올바르게 인코딩됩니다. 그러나 다르게 처리되는 일반적으로 사용되는 특수 문자 집합이 있습니다. 이러한 특수 문자에 따라 합니다 [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 인코딩 표준입니다.  
  
 다음 표는 이 특수 문자 집합을 인코딩하는 구문을 보여 줍니다.  
  
|문자|구문|설명|  
|---------------|------------|-----------------|  
|<|`&lt;`|보다 작음 기호|  
|>|`&gt;`|보다 큼 기호|  
|&|`&amp;`|앰퍼샌드 기호|  
|"|`&quot;`|큰따옴표 기호|  
  
> [!NOTE]
>  파일을 만드는 경우는 태그 텍스트를 사용 하 여 편집기와 같은 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 메모장에서 파일을 저장 해야 합니다 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] 인코딩된 특수 문자를 보존 하려면 utf-8 파일 형식입니다.  
  
 다음 예제에서는 태그를 만들 때 텍스트에 특수 문자를 사용하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
