---
title: 강력한 형식의 DataSets 생성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 25419f8a810b52103e6b862cfe2fe6ab5a1fd981
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040085"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="b32af-102">강력한 형식의 DataSets 생성</span><span class="sxs-lookup"><span data-stu-id="b32af-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="b32af-103">XSD (XML 스키마 정의 언어) 표준을 준수 하는 XML 스키마를 제공 하는 경우 Windows SDK (소프트웨어 개발 키트)와 함께 제공 되는 XSD.EXE 도구를 사용 하 여 강력한 형식의 <xref:System.Data.DataSet>를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="b32af-104">데이터베이스 테이블에서 xsd를 만들려면 <xref:System.Data.DataSet.WriteXmlSchema%2A> 또는 [Visual Studio에서 데이터 집합 작업](/visualstudio/data-tools/dataset-tools-in-visual-studio))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b32af-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="b32af-105">다음 코드에서는이 도구를 사용 하 여 **데이터 집합** 을 생성 하는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```console  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="b32af-106">이 구문에서 `/d` 지시문은 도구에 **데이터 집합**을 생성 하도록 지시 하 고 `/l:`는 도구에 사용할 언어 (예: C# 또는 Visual Basic .net)를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="b32af-107">선택적 `/eld` 지시문은 LINQ to DataSet를 사용 하 여 생성 된 **데이터 집합** 에 대해 쿼리할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-107">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="b32af-108">이 옵션은 `/d` 옵션도 함께 지정한 경우에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="b32af-109">자세한 내용은 [형식화 된 데이터 집합 쿼리](../querying-typed-datasets.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b32af-109">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="b32af-110">선택적 `/n:` 지시문은 도구에서 **Xsdschema. namespace**라는 **데이터 집합** 에 대 한 네임 스페이스도 생성 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="b32af-111">이 명령을 실행하면 XSDSchemaFileName.cs가 생성되며, 이 파일을 컴파일하여 ADO.NET 애플리케이션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="b32af-112">생성된 코드는 라이브러리나 모듈로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="b32af-113">다음 코드는 생성된 코드를 C# 컴파일러(csc.exe)를 사용하여 라이브러리로 컴파일하는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```console  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="b32af-114">`/t:` 지시문은 도구에 라이브러리로 컴파일하라는 것을, `/r:` 지시문은 컴파일에 필요한 종속 라이브러리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="b32af-115">이 명령을 실행하면 XSDSchemaFileName.dll이 생성되며, 이 dll은 `/r:` 지시문으로 ADO.NET 애플리케이션을 컴파일할 때 컴파일러로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="b32af-116">다음 코드는 ADO.NET 애플리케이션에서 XSD.exe로 전달된 네임스페이스에 액세스하는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="b32af-117">다음 코드 예제에서는 **customerdataset** 이라는 형식화 된 **데이터 집합** 을 사용 하 여 **Northwind** 데이터베이스에서 고객 목록을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="b32af-118">**Fill** 메서드를 사용 하 여 데이터가 로드 되 면이 예제에서는 형식화 된 **customersrow** (**DataRow**) 개체를 사용 하 여 **Customers** 테이블의 각 고객을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="b32af-119">이렇게 하면 **DataColumnCollection**를 통하지 않고 **CustomerID** 열에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="b32af-120">예제에 사용 되는 XML 스키마는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b32af-120">The following is the XML Schema used for the example:</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="b32af-121">참조</span><span class="sxs-lookup"><span data-stu-id="b32af-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="b32af-122">형식화된 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="b32af-122">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="b32af-123">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="b32af-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b32af-124">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b32af-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
