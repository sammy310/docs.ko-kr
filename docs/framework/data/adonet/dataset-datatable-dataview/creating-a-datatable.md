---
title: DataTable 만들기
description: 메모리 내 관계형 데이터의 한 테이블을 나타내며 독립적으로 또는 다른 .NET Framework 개체를 사용 하 여 DataTable을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 335137eeef02e590539c6d83e46cb39901a1e03f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286923"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="d2b93-103">DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="d2b93-103">Creating a DataTable</span></span>
<span data-ttu-id="d2b93-104"><xref:System.Data.DataTable>은 메모리 내 관계형 데이터가 포함된 하나의 테이블을 나타내며, 독립적으로 만들어 사용하거나 다른 .NET Framework 개체에 의해 사용될 수도 있습니다. 이 경우에는 주로 <xref:System.Data.DataSet>의 멤버로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-104">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="d2b93-105">적절 한 **datatable** 생성자를 사용 하 여 **datatable** 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-105">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="d2b93-106">**Add** 메서드를 사용 하 여 **데이터 집합** 에 추가 하 여 **DataTable** 개체의 **Tables** 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-106">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="d2b93-107">또한 **DataAdapter** 개체의 **Fill** 또는 **FillSchema** 메서드를 사용 하거나 **데이터 집합**의 **ReadXml**, **readxmlschema**또는 **InferXmlSchema** 메서드를 사용 하 여 미리 정의 되거나 유추 된 XML 스키마에서 **데이터 집합** 내에 **DataTable** 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-107">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="d2b93-108">하나의 **데이터 집합**에 있는 **tables** 컬렉션의 멤버로 DataTable을 추가한 후에는 다른 **데이터 집합**의 테이블 컬렉션에 **DataTable** 을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-108">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="d2b93-109">**DataTable**을 처음 만들 때 스키마 (구조)가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-109">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="d2b93-110">테이블의 스키마를 정의 하려면 <xref:System.Data.DataColumn> 테이블의 **Columns** 컬렉션에 개체를 만들고 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-110">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="d2b93-111">테이블에 대 한 기본 키 열을 정의 하 고 **제약 조건** 개체를 만들어 테이블의 **제약 조건** 컬렉션에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-111">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="d2b93-112">**DataTable**의 스키마를 정의한 후에는 테이블의 **Rows** 컬렉션에 **DataRow** 개체를 추가 하 여 테이블에 데이터 행을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-112">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="d2b93-113">DataTable을 만들 때 속성에 대 한 값을 제공할 필요는 없습니다. <xref:System.Data.DataTable.TableName%2A> 속성을 다른 시간에 지정 하거나 비워 둘 수 있습니다. **DataTable**</span><span class="sxs-lookup"><span data-stu-id="d2b93-113">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="d2b93-114">그러나 **TableName** 값이 없는 테이블을 **데이터 집합**에 추가 하면 테이블에 Table0에 대 한 "table"로 시작 하는 증분 기본 이름인 table*N*이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-114">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2b93-115">사용자가 제공 하는 이름이 **데이터 집합**의 기존 기본 테이블 이름과 충돌할 수 있으므로 **TableName** 값을 제공 하는 경우 "테이블*N*" 명명 규칙을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-115">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="d2b93-116">이미 있는 이름을 입력하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-116">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="d2b93-117">다음 예에서는 **DataTable** 개체의 인스턴스를 만들고 이름을 "Customers"로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-117">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="d2b93-118">다음 예에서는 **DataSet**의 **Tables** 컬렉션에 **DataTable** 인스턴스를 추가 하 여 해당 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2b93-118">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2b93-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2b93-119">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="d2b93-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="d2b93-120">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="d2b93-121">DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="d2b93-121">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="d2b93-122">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="d2b93-122">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="d2b93-123">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="d2b93-123">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="d2b93-124">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="d2b93-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
