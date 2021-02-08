---
description: '자세히 알아보기: 외부 매핑'
title: 외부 매핑
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: 8c09e3bdf1798757bedfac9e568a0384a8e6bb49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786084"
---
# <a name="external-mapping"></a><span data-ttu-id="a9be0-103">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="a9be0-103">External Mapping</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a9be0-104">는 별도의 XML 파일을 사용 하 여 데이터베이스의 데이터 모델과 개체 모델 간의 매핑을 지정 하는 프로세스에 대 한 *외부 매핑을* 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-104">supports *external mapping*, a process by which you use a separate XML file to specify mapping between the data model of the database and your object model.</span></span> <span data-ttu-id="a9be0-105">외부 매핑 파일을 사용하면 다음과 같은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-105">Advantages of using an external mapping file include the following:</span></span>  
  
- <span data-ttu-id="a9be0-106">매핑 코드를 애플리케이션 코드와 따로 유지할 수 있어</span><span class="sxs-lookup"><span data-stu-id="a9be0-106">You can keep your mapping code out of your application code.</span></span> <span data-ttu-id="a9be0-107">애플리케이션 코드를 간단하게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-107">This approach reduces clutter in your application code.</span></span>  
  
- <span data-ttu-id="a9be0-108">외부 매핑 파일을 구성 파일처럼 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-108">You can treat an external mapping file something like a configuration file.</span></span> <span data-ttu-id="a9be0-109">예를 들어 외부 매핑 파일을 바꾸는 방법으로 이진 파일을 배포한 후 애플리케이션의 동작을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-109">For example, you can update how your application behaves after shipping the binaries by just swapping out the external mapping file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9be0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9be0-110">Requirements</span></span>  

 <span data-ttu-id="a9be0-111">매핑 파일은 XML 파일이어야 하며 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 스키마 정의 파일(.xsd)에 대해 유효성이 검사되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-111">The mapping file must be an XML file, and the file must validate against a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] schema definition (.xsd) file.</span></span>  
  
 <span data-ttu-id="a9be0-112">다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-112">The following rules apply:</span></span>  
  
- <span data-ttu-id="a9be0-113">매핑 파일은 XML 파일이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-113">The mapping file must be an XML file.</span></span>  
  
- <span data-ttu-id="a9be0-114">XML 매핑 파일은 XML 스키마 정의 파일에 대해 유효해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-114">The XML mapping file must be valid against the XML schema definition file.</span></span> <span data-ttu-id="a9be0-115">자세한 내용은 [방법: DBML 및 외부 매핑 파일 유효성 검사](how-to-validate-dbml-and-external-mapping-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9be0-115">For more information, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
- <span data-ttu-id="a9be0-116">외부 매핑은 특성 기반 매핑을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-116">External mapping overrides attribute-based mapping.</span></span> <span data-ttu-id="a9be0-117">즉, 외부 매핑 소스를 사용하여 <xref:System.Data.Linq.DataContext>를 만들면 <xref:System.Data.Linq.DataContext>에서는 사용자가 클래스에 만든 모든 매핑 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-117">In other words, when you use an external mapping source to create a <xref:System.Data.Linq.DataContext>, the <xref:System.Data.Linq.DataContext> ignores all mapping attributes you have created on classes.</span></span> <span data-ttu-id="a9be0-118">이 동작은 외부 매핑 파일에 클래스가 포함되었는지 여부에 관계없이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-118">This behavior is true whether the class is included in the external mapping file.</span></span>  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a9be0-119">에서는 특성 기반 매핑과 외부 매핑의 혼합 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-119">does not support the hybrid use of the two mapping approaches (attribute-based and external).</span></span>  
  
## <a name="xml-schema-definition-file"></a><span data-ttu-id="a9be0-120">XML 스키마 정의 파일</span><span class="sxs-lookup"><span data-stu-id="a9be0-120">XML Schema Definition File</span></span>  

 <span data-ttu-id="a9be0-121">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 외부 매핑은 다음 XML 스키마 정의에 대해 유효해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-121">External mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be valid against the following XML schema definition.</span></span>  
  
 <span data-ttu-id="a9be0-122">이 스키마 정의 파일은 DBML 파일의 유효성을 검사하는 데 사용하는 스키마 정의 파일과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-122">Distinguish this schema definition file from the schema definition file that is used to validate a DBML file.</span></span> <span data-ttu-id="a9be0-123">자세한 내용은 [LINQ to SQL의 코드 생성](code-generation-in-linq-to-sql.md))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9be0-123">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9be0-124">또한 Visual Studio 사용자는 XML 스키마 대화 상자에서이 XSD 파일을 "Linqtosqlmapping.xsd"으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9be0-124">Visual Studio users will also find this XSD file in the XML Schemas dialog box as "LinqToSqlMapping.xsd".</span></span> <span data-ttu-id="a9be0-125">외부 매핑 파일의 유효성을 검사 하는 데이 파일을 제대로 사용 하려면 [방법: DBML 및 외부 매핑 파일 유효성 검사](how-to-validate-dbml-and-external-mapping-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9be0-125">To use this file correctly for validating an external mapping file, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9be0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9be0-126">See also</span></span>

- [<span data-ttu-id="a9be0-127">LINQ to SQL에서 코드 생성</span><span class="sxs-lookup"><span data-stu-id="a9be0-127">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="a9be0-128">참조</span><span class="sxs-lookup"><span data-stu-id="a9be0-128">Reference</span></span>](reference.md)
- [<span data-ttu-id="a9be0-129">방법: 외부 파일로 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="a9be0-129">How to: Generate the Object Model as an External File</span></span>](how-to-generate-the-object-model-as-an-external-file.md)
