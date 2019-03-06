---
title: '방법: 페이지에서 창 너비 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: fee6d4c9ae9dae03e81cc4be56576763cb59958b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379356"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>방법: 페이지에서 창 너비 설정
이 예제에서 창의 너비를 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Page>합니다.  
  
## <a name="example"></a>예제  
 A <xref:System.Windows.Controls.Page> 설정 하 여 해당 호스트 창의 너비를 설정할 수 있습니다 <xref:System.Windows.Controls.Page.WindowWidth%2A>합니다. 이 속성을 사용 하면를 <xref:System.Windows.Controls.Page> 를 호스팅하는 창의 유형에 대 한 명시적 정보가 없습니다.  
  
> [!NOTE]
>  사용 하 여 창 너비를 설정 하려면 <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> 창의 자식 이어야 합니다.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
