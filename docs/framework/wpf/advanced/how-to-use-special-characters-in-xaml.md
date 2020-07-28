---
title: '방법: XAML에서 특수 문자 사용'
description: Windows Presentation Foundation의 XAML 파일에서 사용 하기 위해 Visual Studio에서 유니코드 UTF-8 파일 형식의 특수 문자를 인코딩하는 구문에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: ac2388fd96aa26ddd99408ac9f847ce517958568
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168355"
---
# <a name="how-to-use-special-characters-in-xaml"></a>방법: XAML에서 특수 문자 사용
Visual Studio에서 만든 태그 파일은 자동으로 유니코드 UTF-8 파일 형식으로 저장 됩니다. 즉, 대부분의 특수 문자 (예: 악센트 표시)가 올바르게 인코딩됩니다. 그러나 다르게 처리되는 일반적으로 사용되는 특수 문자 집합이 있습니다. 이러한 특수 문자는 인코딩에 대해 W3C (World Wide Web 컨소시엄) XML 표준을 따릅니다.  
  
 다음 표는 이 특수 문자 집합을 인코딩하는 구문을 보여 줍니다.  
  
|문자|구문|Description|  
|---------------|------------|-----------------|  
|<|`&lt;`|보다 작음 기호|  
|>|`&gt;`|보다 큼 기호|  
|&|`&amp;`|앰퍼샌드 기호|  
|"|`&quot;`|큰따옴표 기호|  
  
> [!NOTE]
> Windows 메모장과 같은 텍스트 편집기를 사용 하 여 태그 파일을 만드는 경우 인코딩된 특수 문자를 유지 하기 위해 파일을 유니코드 UTF-8 파일 형식으로 저장 해야 합니다.  
  
 다음 예제에서는 태그를 만들 때 텍스트에 특수 문자를 사용하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
