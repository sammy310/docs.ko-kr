---
title: 강력한 형식의 데이터 세트 생성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 25883b7be10c68e527e4e04182b7162574b994d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149632"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="7535f-102">강력한 형식의 데이터 세트 생성</span><span class="sxs-lookup"><span data-stu-id="7535f-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="7535f-103">XSD(XML 스키마 정의 언어) 표준과 호환되는 XML 스키마가 있으면 <xref:System.Data.DataSet>에 제공된 XSD.exe 도구를 사용하여 강력한 형식의 [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)]을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="7535f-104">(데이터베이스 테이블에서 xsd를 만들려면, 참조 <xref:System.Data.DataSet.WriteXmlSchema%2A> 나 [Visual Studio에서 데이터 집합 작업](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span><span class="sxs-lookup"><span data-stu-id="7535f-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="7535f-105">다음 코드를 생성 하기 위한 구문을 보여 줍니다.는 **데이터 집합** 이 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="7535f-106">이 구문에서은 `/d` 지시문은 생성 하는 도구를 **데이터 집합**, 및 `/l:` 도구 (예: C# 또는 Visual Basic.NET) 사용 하는 언어를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="7535f-107">선택적 `/eld` 지시문을 사용할 수 있는 지정 [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] 생성 된 쿼리 **데이터 집합입니다.**</span><span class="sxs-lookup"><span data-stu-id="7535f-107">The optional `/eld` directive specifies that you can use [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] to query against the generated **DataSet.**</span></span> <span data-ttu-id="7535f-108">이 옵션은 `/d` 옵션도 함께 지정한 경우에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="7535f-109">자세한 내용은 [형식화 된 데이터 집합 쿼리](../../../../../docs/framework/data/adonet/querying-typed-datasets.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-109">For more information, see [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="7535f-110">선택적 `/n:` 지시문은 또한 네임 스페이스를 생성 하는 도구를 **데이터 집합** 호출 **XSDSchema.Namespace**합니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="7535f-111">이 명령을 실행하면 XSDSchemaFileName.cs가 생성되며, 이 파일을 컴파일하여 ADO.NET 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="7535f-112">생성된 코드는 라이브러리나 모듈로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="7535f-113">다음 코드는 생성된 코드를 C# 컴파일러(csc.exe)를 사용하여 라이브러리로 컴파일하는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="7535f-114">`/t:` 지시문은 도구에 라이브러리로 컴파일하라는 것을, `/r:` 지시문은 컴파일에 필요한 종속 라이브러리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="7535f-115">이 명령을 실행하면 XSDSchemaFileName.dll이 생성되며, 이 dll은 `/r:` 지시문으로 ADO.NET 응용 프로그램을 컴파일할 때 컴파일러로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="7535f-116">다음 코드는 ADO.NET 응용 프로그램에서 XSD.exe로 전달된 네임스페이스에 액세스하는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="7535f-117">다음 코드 예제에서는 형식화 된 **데이터 집합** 라는 **CustomerDataSet** 의 고객 목록을 로드 하는 **Northwind** 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="7535f-118">데이터를 사용 하 여 로드 되 면를 **채우기** 메서드를 각 고객에 대해 반복 실행 합니다 **고객** 사용 하 여 형식화 된 테이블 **CustomersRow** ( **DataRow**) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="7535f-119">이에 대 한 직접 액세스를 제공 합니다 **CustomerID** 열을 통하지 합니다 **DataColumnCollection**합니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 <span data-ttu-id="7535f-120">다음은 예제에서 사용한 XML 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="7535f-120">Following is the XML Schema used for the example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7535f-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="7535f-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="7535f-122">형식화된 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="7535f-122">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [<span data-ttu-id="7535f-123">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="7535f-123">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="7535f-124">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="7535f-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
