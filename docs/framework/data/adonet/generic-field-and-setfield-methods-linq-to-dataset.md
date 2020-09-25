---
title: 제네릭 Field 및 SetField 메서드(LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 9deda11592389dd799477bdc027d59a0be0036da
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200656"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>제네릭 Field 및 SetField 메서드(LINQ to DataSet)

LINQ to DataSet는 열 값에 액세스 하는 클래스에 대 한 확장 메서드를 제공 합니다 <xref:System.Data.DataRow> . <xref:System.Data.DataRowExtensions.Field%2A> 메서드 및 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드. 개발자는 이러한 메서드를 사용하여 열 값에 쉽게 액세스할 수 있으며, 특히 null 값과 관련된 작업을 쉽게 수행할 수 있습니다. 는 <xref:System.Data.DataSet> 를 사용 하 여 <xref:System.DBNull.Value?displayProperty=nameWithType> null 값을 표시 하는 반면 LINQ는 <xref:System.Nullable> 및 형식을 사용 합니다 <xref:System.Nullable%601> . <xref:System.Data.DataRow>의 기존 열 접근자를 사용하려면 반환 개체를 적절한 형식으로 캐스팅해야 합니다. 반환된 <xref:System.Data.DataRow>가 암시적으로 다른 형식으로 캐스팅되면 <xref:System.DBNull.Value?displayProperty=nameWithType>이 throw되므로 <xref:System.InvalidCastException>의 특정 필드가 null일 가능성이 있는 경우 명시적으로 null 값을 확인해야 합니다. 다음 예제에서 <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> 메서드를 사용하여 null 값을 확인하지 않으면 인덱서에서 <xref:System.DBNull.Value?displayProperty=nameWithType>를 반환하면서 <xref:System.String>으로 캐스팅할 때 예외가 throw됩니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 <xref:System.Data.DataRowExtensions.Field%2A> 메서드는 <xref:System.Data.DataRow>의 열 값에 대한 액세스를 제공하고 <xref:System.Data.DataRowExtensions.SetField%2A>는 <xref:System.Data.DataRow>의 열 값을 설정합니다. <xref:System.Data.DataRowExtensions.Field%2A>메서드와 메서드는 모두 <xref:System.Data.DataRowExtensions.SetField%2A> null을 허용 하는 값 형식을 처리 하므로 이전 예제와 같이 명시적으로 null 값을 확인 하지 않아도 됩니다. 또한 두 메서드 모두 제네릭 메서드이므로 반환 형식을 캐스팅하지 않아도 됩니다.  
  
 다음 예제에서는 <xref:System.Data.DataRowExtensions.Field%2A> 메서드를 사용합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 `T` 메서드 및 <xref:System.Data.DataRowExtensions.Field%2A> 메서드의 제네릭 매개 변수 <xref:System.Data.DataRowExtensions.SetField%2A>에 지정된 데이터 형식은 내부 값의 형식과 일치해야 합니다. 그렇지 않으면 <xref:System.InvalidCastException> 예외가 throw됩니다. 지정된 열 이름도 <xref:System.Data.DataSet>의 열 이름과 일치해야 하며, 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다. 두 경우 모두 쿼리가 실행되는 런타임에 데이터 열거형에서 예외가 throw됩니다.  
  
 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드 자체에서는 형식 변환이 수행되지 않습니다. 그렇다고 해서 형식 변환이 발생하지 않는다는 것은 아닙니다. <xref:System.Data.DataRowExtensions.SetField%2A>메서드는 클래스의 ADO.NET 동작을 노출 합니다 <xref:System.Data.DataRow> . <xref:System.Data.DataRow> 개체에서 형식 변환을 수행하면 변환된 값은 <xref:System.Data.DataRow> 개체에 저장됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataRowExtensions>
