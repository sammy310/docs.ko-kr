---
title: DataReader 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 3af6ae3a8f4ecc3ec34c186ce55c1c77c27514a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202333"
---
# <a name="creating-a-datareader"></a>DataReader 만들기

<xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스에는 <xref:System.Data.DataTable.CreateDataReader%2A>의 내용이나 <xref:System.Data.DataTable> 개체의 <xref:System.Data.DataSet> 컬렉션 내용을 하나 이상의 정방향 읽기 전용 커서로 반환하는 <xref:System.Data.DataSet.Tables%2A> 메서드가 있습니다.  
  
## <a name="example"></a>예제  

 다음 콘솔 애플리케이션에서는 <xref:System.Data.DataTable> 인스턴스를 만듭니다. 그런 다음이 예제에서는 메서드를 호출 하는 프로시저에 채워진를 전달 합니다 <xref:System.Data.DataTable> .이 프로시저는 내에 포함 된 <xref:System.Data.DataTable.CreateDataReader%2A> 결과를 반복 합니다 <xref:System.Data.DataTableReader> .  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 이 예제에서는 콘솔 창에 다음 출력을 표시합니다.  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [DataTableReader](datatablereaders.md)
- [ADO.NET 개요](../ado-net-overview.md)
