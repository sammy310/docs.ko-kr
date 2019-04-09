---
title: DataTable 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 272976d3c581d3e8a5860ba5cf3f9695ca370d8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112387"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="4aad1-102">DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="4aad1-102">Creating a DataTable</span></span>
<span data-ttu-id="4aad1-103"><xref:System.Data.DataTable>은 메모리 내 관계형 데이터가 포함된 하나의 테이블을 나타내며, 독립적으로 만들어 사용하거나 다른 .NET Framework 개체에 의해 사용될 수도 있습니다. 이 경우에는 주로 <xref:System.Data.DataSet>의 멤버로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="4aad1-104">만들 수 있습니다는 **DataTable** 개체를 사용 하 여 **DataTable** 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="4aad1-105">에 추가할 수 있습니다는 **데이터 집합** 사용 하 여를 **추가** 에 추가 하는 방법의 **DataTable** 개체의 **테이블** 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="4aad1-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="4aad1-106">만들 수도 있습니다 **DataTable** 내에서 개체를 **데이터 집합** 사용 하 여는 **채우기** 또는 **FillSchema** 의 메서드는  **DataAdapter** 개체는 미리 정의 되거나 유추 된 XML 스키마를 사용 하 여 또는 합니다 **ReadXml**, **ReadXmlSchema**, 또는 **InferXmlSchema** 메서드를 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="4aad1-107">추가한 후를 **DataTable** 의 구성원으로는 **테이블** 하나의 컬렉션 **DataSet**, 기타 테이블의컬렉션에추가할수없습니다**데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="4aad1-108">처음 만들 때는 **DataTable**, 스키마 (구조) 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="4aad1-109">테이블의 스키마를 정의 하려면 만들기 및 추가 해야 합니다 <xref:System.Data.DataColumn> 개체를 **열** 테이블의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="4aad1-110">또한 테이블에 대 한 기본 키 열 정의 및 만들기 추가 하는 **제약 조건** 개체를 **제약 조건** 테이블의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="4aad1-111">에 대 한 스키마를 정의한 후는 **DataTable**를 추가 하 여 테이블에 데이터 행을 추가할 수 있습니다 **DataRow** 개체를 합니다 **행** 테이블의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="4aad1-112">에 대 한 값을 제공 하지 않아도 됩니다 합니다 <xref:System.Data.DataTable.TableName%2A> 만들 때 속성을 **DataTable**; 다른 시간에 속성을 지정 하거나 비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="4aad1-113">그러나 없는 테이블을 추가 하는 하면를 **TableName** 값을 **데이터 집합**, 테이블은 증분 기본 이름인 Table 주어 집니다*N*"Table" table0부터.</span><span class="sxs-lookup"><span data-stu-id="4aad1-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aad1-114">사용 하지 않는 것이 좋습니다는 "테이블*N*" 제공 하는 경우 명명 규칙을 **TableName** 값을 제공한 이름에 있는 기존의 기본 테이블 이름과 충돌이 발생할 수 있습니다는 **데이터 집합** .</span><span class="sxs-lookup"><span data-stu-id="4aad1-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="4aad1-115">이미 있는 이름을 입력하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="4aad1-116">다음 예제에서는 인스턴스를 **DataTable** 개체 및 이름을 지정한 "고객"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="4aad1-117">다음 예제에서는 인스턴스를 만듭니다는 **DataTable** 추가 하 여 합니다 **테이블** 의 컬렉션을 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="4aad1-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="4aad1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="4aad1-118">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="4aad1-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="4aad1-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="4aad1-120">DataAdapter에서 DataSet 채우기</span><span class="sxs-lookup"><span data-stu-id="4aad1-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="4aad1-121">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="4aad1-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="4aad1-122">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="4aad1-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="4aad1-123">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="4aad1-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
