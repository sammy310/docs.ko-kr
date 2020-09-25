---
title: '방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: cf2a47c5d29c0af680ee4ccae503e92d3a9124d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194715"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩

<xref:System.Windows.Forms.DataGridView> 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다. <xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원하므로 <xref:System.Data.DataView> 및 다양한 데이터 소스에 바인딩합니다. 그러나 대부분의 경우 데이터 소스와의 상호 작용에 대한 세부 사항을 관리하는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩합니다.  
  
 컨트롤에 대 한 자세한 내용은 <xref:System.Windows.Forms.DataGridView> [DataGridView 컨트롤 개요](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms)를 참조 하세요.  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>DataGridView 컨트롤을 DataView에 연결하려면  
  
1. 데이터베이스에서 데이터를 검색하는 세부 과정을 처리하는 메서드를 구현합니다. 다음 코드 예제에서는 `GetData` 구성 요소를 초기화한 다음 이 구성 요소를 사용하여 <xref:System.Data.SqlClient.SqlDataAdapter>을 채우는 <xref:System.Data.DataSet> 메서드를 구현합니다. `connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다. AdventureWorks SQL Server 샘플 데이터베이스가 설치된 서버에 액세스해야 합니다.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩한 다음 `GetData` 메서드를 호출하여 데이터베이스에서 데이터를 검색합니다. 는 <xref:System.Data.DataView> 연락처에 대 한 LINQ to DataSet 쿼리에서 생성 된 <xref:System.Data.DataTable> 다음 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩됩니다.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>참고 항목

- [데이터 바인딩 및 LINQ to DataSet](data-binding-and-linq-to-dataset.md)
