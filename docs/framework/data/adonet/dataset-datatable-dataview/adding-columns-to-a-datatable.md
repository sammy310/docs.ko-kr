---
title: DataTable에 열 추가
description: DataTable에는 테이블의 Columns 속성에서 참조 하는 DataColumn 개체가 포함 되어 있습니다. ADO.NET의 테이블에 열을 추가 하려면 다음 예제 코드를 사용 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 9d6d21696acd7a6b63cfd6d2ea7e906ec2acd7c9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286949"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="ec332-104">DataTable에 열 추가</span><span class="sxs-lookup"><span data-stu-id="ec332-104">Adding Columns to a DataTable</span></span>
<span data-ttu-id="ec332-105">에는 <xref:System.Data.DataTable> <xref:System.Data.DataColumn> 테이블의 **Columns** 속성에서 참조 하는 개체의 컬렉션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-105">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="ec332-106">이 열 컬렉션과 모든 제약 조건을 함께 사용하여 테이블의 스키마나 구조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-106">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="ec332-107">**Datacolumn** 생성자를 사용 하거나 테이블의 **Columns** 속성 ()의 **Add** 메서드를 호출 하 여 테이블 내에서 **datacolumn** 개체를 만들 수 있습니다 <xref:System.Data.DataColumnCollection> .</span><span class="sxs-lookup"><span data-stu-id="ec332-107">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="ec332-108">**Add** 메서드는 선택적 **ColumnName**, **DataType**및 **Expression** 인수를 받아들이고 컬렉션의 멤버로 새 **DataColumn** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-108">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="ec332-109">또한 기존 **datacolumn** 개체를 수락 하 여 컬렉션에 추가 하 고 요청 시 추가 된 **datacolumn** 에 대 한 참조를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-109">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="ec332-110">**DataTable** 개체는 데이터 원본에 한정 되지 않으므로 **DataColumn**의 데이터 형식을 지정할 때 .NET Framework 형식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-110">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="ec332-111">다음 예에서는 **DataTable**에 4 개의 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-111">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="ec332-112">이 예에서는 **CustID** 열에 대 한 속성이 **DBNull** 값을 허용 하지 않도록 설정 되 고 값을 고유 하 게 제한 하는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-112">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="ec332-113">그러나 **CustID** 열을 테이블의 기본 키 열로 정의 하면 **allowdbnull** 속성은 자동으로 **False** 로 설정 되 고 **Unique** 속성은 자동으로 **true**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-113">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="ec332-114">자세한 내용은 [기본 키 정의](defining-primary-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-114">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ec332-115">열에 대해 열 이름을 지정 하지 않으면 열에 "Column1"으로 시작 하는 열*N* 의 증분 기본 이름이 지정 됩니다 .이 이름은 **DataColumnCollection**에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-115">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="ec332-116">열 이름을 제공 하는 경우 "열*N*"의 명명 규칙을 사용 하지 않는 것이 좋습니다 .이 경우 사용자가 제공 하는 이름이 **DataColumnCollection**의 기존 기본 열 이름과 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-116">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="ec332-117">이미 있는 이름을 입력하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-117">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="ec332-118"><xref:System.Xml.Linq.XElement>를 <xref:System.Data.DataColumn.DataType%2A>에서 <xref:System.Data.DataColumn>의 <xref:System.Data.DataTable>로 사용하는 경우 데이터를 읽을 때 XML serialization이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-118">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="ec332-119">예를 들어 <xref:System.Xml.XmlDocument> 메서드를 사용하여 `DataTable.WriteXml`를 작성하는 경우 XML에 대한 serialization 수행 시 <xref:System.Xml.Linq.XElement>에 추가 부모 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-119">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ec332-120">이 문제를 해결하려면 <xref:System.Data.SqlTypes.SqlXml> 대신 <xref:System.Xml.Linq.XElement> 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-120">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ec332-121">`ReadXml` 및 `WriteXml`이 <xref:System.Data.SqlTypes.SqlXml>와 올바르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ec332-121">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec332-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec332-122">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="ec332-123">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="ec332-123">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="ec332-124">DataTables</span><span class="sxs-lookup"><span data-stu-id="ec332-124">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="ec332-125">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="ec332-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
