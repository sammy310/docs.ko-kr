---
title: '방법: 제네릭 형식 T가 DataRow가 아닌 CopyToDataTable<T> 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: a1427747d03f01e52f1ee7ad1fc11d47d310edbe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590607"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a><span data-ttu-id="452d3-102">방법: 제네릭 형식 T가 DataRow가 아닌 CopyToDataTable\<T> 구현</span><span class="sxs-lookup"><span data-stu-id="452d3-102">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>
<span data-ttu-id="452d3-103">대개 <xref:System.Data.DataTable> 개체는 데이터 바인딩에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-103">The <xref:System.Data.DataTable> object is often used for data binding.</span></span> <span data-ttu-id="452d3-104"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 쿼리 결과를 받아서 나중에 데이터 바인딩에 사용할 수 있도록 데이터를 <xref:System.Data.DataTable>에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="452d3-105">하지만 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 제네릭 매개 변수 <xref:System.Collections.Generic.IEnumerable%601>가 `T` 형식인 <xref:System.Data.DataRow> 소스에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods, however, only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="452d3-106">이 제한은 유용하지만 이로 인해 일련의 스칼라 형식, 익명 형식을 프로젝션하는 쿼리 또는 테이블 조인을 수행하는 쿼리에서 테이블을 만들지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-106">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that project anonymous types, or from queries that perform table joins.</span></span>  
  
 <span data-ttu-id="452d3-107">이 항목에서는 `CopyToDataTable<T>` 형식 이외의 제네릭 매개 변수 `T` 형식을 사용할 수 있는 두 가지 사용자 지정 <xref:System.Data.DataRow> 확장을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-107">This topic describes how to implement two custom `CopyToDataTable<T>` extension methods that accept a generic parameter `T` of a type other than <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="452d3-108"><xref:System.Data.DataTable> 소스에서 <xref:System.Collections.Generic.IEnumerable%601>을 만드는 로직은 `ObjectShredder<T>` 클래스에 있으며, 이 클래스는 두 오버로드 `CopyToDataTable<T>` 확장명 메서드로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-108">The logic to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source is contained in the `ObjectShredder<T>` class, which is then wrapped in two overloaded `CopyToDataTable<T>` extension methods.</span></span> <span data-ttu-id="452d3-109">`Shred` 클래스의 `ObjectShredder<T>` 메서드는 채워진 <xref:System.Data.DataTable>을 반환하며 세 개의 입력 매개 변수로 <xref:System.Collections.Generic.IEnumerable%601> 소스, <xref:System.Data.DataTable> 및 <xref:System.Data.LoadOption> 열거형을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-109">The `Shred` method of the `ObjectShredder<T>` class returns the filled <xref:System.Data.DataTable> and accepts three input parameters: an <xref:System.Collections.Generic.IEnumerable%601> source, a <xref:System.Data.DataTable>, and a <xref:System.Data.LoadOption> enumeration.</span></span> <span data-ttu-id="452d3-110">반환된 <xref:System.Data.DataTable>의 초기 스키마는 형식 `T`의 스키마에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-110">The initial schema of the returned <xref:System.Data.DataTable> is based on the schema of the type `T`.</span></span> <span data-ttu-id="452d3-111">기존 테이블이 입력으로 제공되는 경우 해당 스키마는 형식 `T`의 스키마와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-111">If an existing table is provided as input, the schema must be consistent with the schema of the type `T`.</span></span> <span data-ttu-id="452d3-112">형식 `T`의 각 public 속성 및 필드는 반환된 테이블에서 <xref:System.Data.DataColumn>으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-112">Each public property and field of the type `T` is converted to a <xref:System.Data.DataColumn> in the returned table.</span></span> <span data-ttu-id="452d3-113">소스 시퀀스에 `T`에서 파생된 형식이 포함되는 경우 추가 public 속성 또는 필드를 사용할 수 있도록 반환된 테이블 스키마가 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-113">If the source sequence contains a type derived from `T`, the returned table schema is expanded for any additional public properties or fields.</span></span>  
  
 <span data-ttu-id="452d3-114">사용자 지정 `CopyToDataTable<T>` 메서드 사용에 대한 예제는 [쿼리에서 DataTable 만들기](creating-a-datatable-from-a-query-linq-to-dataset.md)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-114">For examples of using the custom `CopyToDataTable<T>` methods, see [Creating a DataTable From a Query](creating-a-datatable-from-a-query-linq-to-dataset.md).</span></span>  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a><span data-ttu-id="452d3-115">응용 프로그램에서 사용자 지정 CopyToDataTable 메서드를 구현 하려면 \<T></span><span class="sxs-lookup"><span data-stu-id="452d3-115">To implement the custom CopyToDataTable\<T> methods in your application</span></span>  
  
1. <span data-ttu-id="452d3-116">`ObjectShredder<T>` 소스에서 <xref:System.Data.DataTable>을 만드는 <xref:System.Collections.Generic.IEnumerable%601> 클래스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-116">Implement the `ObjectShredder<T>` class to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    <span data-ttu-id="452d3-117">앞의 예제에서는의 속성 및 필드가 `DataColumn` nullable 값 형식이 아닌 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-117">The preceding example assumes that the properties and fields of the `DataColumn` are not nullable value types.</span></span> <span data-ttu-id="452d3-118">Nullable 값 형식으로 속성 및 필드를 처리 하려면 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-118">To handle properties and fields with nullable value types, use the following code:</span></span>

    ```csharp
    // Nullable-aware code for properties.
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);

    // Nullable-aware code for fields.
    DataColumn dc = table.Columns.Contains(f.Name) ? table.Columns[f.Name] : table.Columns.Add(f.Name, Nullable.GetUnderlyingType(f.FieldType) ?? f.FieldType);
    ```

2. <span data-ttu-id="452d3-119">클래스에서 사용자 지정 `CopyToDataTable<T>` 확장명 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-119">Implement the custom `CopyToDataTable<T>` extension methods in a class:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. <span data-ttu-id="452d3-120">애플리케이션에 `ObjectShredder<T>` 클래스 및 `CopyToDataTable<T>` 확장명 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="452d3-120">Add the `ObjectShredder<T>` class and `CopyToDataTable<T>` extension methods to your application.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="452d3-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="452d3-121">See also</span></span>

- [<span data-ttu-id="452d3-122">쿼리에서 DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="452d3-122">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)
- [<span data-ttu-id="452d3-123">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="452d3-123">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)
