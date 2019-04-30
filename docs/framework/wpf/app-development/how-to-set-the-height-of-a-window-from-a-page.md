---
title: '방법: 페이지에서 창 높이 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007328"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>방법: 페이지에서 창 높이 설정
이 예제에서 창의 높이 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Page>합니다.  
  
## <a name="example"></a>예제  
 A <xref:System.Windows.Controls.Page> 설정 하 여 해당 호스트 창의 높이 설정할 수 있습니다 <xref:System.Windows.Controls.Page.WindowHeight%2A>합니다. 이 속성을 사용 하면를 <xref:System.Windows.Controls.Page> 를 호스팅하는 창의 유형에 대 한 명시적 정보가 없습니다.  
  
> [!NOTE]
>  사용 하 여 창 높이 설정 하려면 <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> 창의 자식 이어야 합니다.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
