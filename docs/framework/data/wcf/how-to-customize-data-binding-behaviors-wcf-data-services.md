---
title: '방법: 데이터 바인딩 동작 사용자 지정 (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: 453562dd1b86756bf9fc1684dc649dba1c24c578
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569170"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>방법: 데이터 바인딩 동작 사용자 지정 (WCF Data Services)
WCF Data Services를 사용 하면 바인딩 컬렉션에서 개체가 추가 또는 제거 되거나 속성 변경이 검색 될 때 <xref:System.Data.Services.Client.DataServiceCollection%601>에서 호출 하는 사용자 지정 논리를 제공할 수 있습니다. 이 사용자 지정 논리는 사용자 지정 메서드가 완료 될 때 기본 동작을 수행 해야 하는 경우 `false`의 값을 반환 하 `true` 고 후속 이벤트 처리를 중지 해야 하는 경우에 <xref:System.Func%602> 대리자로 참조 되는 메서드로 제공 됩니다.  
  
 이 항목의 예제에서는 `entityChanged`의 `entityCollectionChanged` 및 <xref:System.Data.Services.Client.DataServiceCollection%601> 매개 변수에 대해 모두 사용자 지정 메서드를 제공합니다. 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 이 서비스 및 클라이언트 데이터 클래스는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 완료 하면 생성 됩니다.  
  
## <a name="example"></a>예제  
 XAML 파일에 대 한 다음 코드를 사용 하는 페이지에서는 바인딩 컬렉션에 바인딩된 데이터가 변경 될 때 호출 되는 사용자 지정 메서드를 사용 하 여 <xref:System.Data.Services.Client.DataServiceCollection%601>를 만듭니다. <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> 이벤트가 발생할 때 제공 된 메서드는 바인딩 컬렉션에서 제거 된 항목이 데이터 서비스에서 삭제 되지 않도록 방지 합니다. <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> 이벤트가 발생 하면 `ShipDate` 값의 유효성을 검사 하 여 이미 배송 된 주문이 변경 되지 않도록 합니다.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>예제  
 다음 XAML에서는 이전 예제의 창을 정의합니다.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>참조

- [WCF Data Services 클라이언트 라이브러리](wcf-data-services-client-library.md)
