---
title: '방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화'
description: Windows Presentation Foundation (WPF)에서 그룹화, 정렬 및 필터링을 위해 데이터 컬렉션의 뷰를 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: a4f8e2de9345dba8e4ea0d3a16a32d57a9adb55c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621680"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화
이 예에서는에서 데이터 컬렉션의 뷰를 만드는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . 뷰를 사용 하면 그룹화, 정렬, 필터링 및 현재 항목의 개념에 대 한 기능을 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정적 리소스 명명 된 *위치* *개체의 컬렉션* 으로 정의 됩니다. 여기서 각 *위치* 개체는 도시 이름과 상태로 구성 됩니다. 접두사 *src* 는 데이터 원본 *위치가* 정의 된 네임 스페이스에 매핑됩니다. *Scm* 은에 매핑되고 `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` *dat* 는로 매핑됩니다 `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` .  
  
 다음 예에서는 도시 이름을 기준으로 정렬 되 고 상태별로 그룹화 된 데이터 컬렉션 뷰를 만듭니다.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 그러면 다음 예제와 같이 뷰가 바인딩 원본이 될 수 있습니다.  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 리소스에 정의 된 XML 데이터에 대 한 바인딩의 경우 <xref:System.Windows.Data.XmlDataProvider> xml 이름 앞에 @ 기호를 사용 합니다.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Data.CollectionViewSource>
- [데이터 컬렉션의 기본 뷰 가져오기](how-to-get-the-default-view-of-a-data-collection.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 도움말 항목](data-binding-how-to-topics.md)
