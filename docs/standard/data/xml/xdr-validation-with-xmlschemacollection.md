---
title: XmlSchemaCollection을 사용하여 XDR 유효성 검사
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
ms.openlocfilehash: c1383dbb5419eadbfb7c07f288ee46b1ca11cf5c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710000"
---
# <a name="xdr-validation-with-xmlschemacollection"></a><span data-ttu-id="78897-102">XmlSchemaCollection을 사용하여 XDR 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="78897-102">XDR Validation with XmlSchemaCollection</span></span>

<span data-ttu-id="78897-103">유효성을 검사하려는 XDR(XML 데이터 축소) 스키마가 **XmlSchemaCollection**에 저장된 경우 스키마를 컬렉션에 추가할 때 지정한 네임스페이스 URI와 연관됩니다.</span><span class="sxs-lookup"><span data-stu-id="78897-103">If the XML-Data Reduced (XDR) schema you are validating against is stored in the **XmlSchemaCollection**, it is associated with the namespace URI specified when the schema was added to the collection.</span></span> <span data-ttu-id="78897-104">**XmlValidatingReader**에서는 XML 문서의 네임스페이스 URI를 컬렉션의 해당 URI에 상응하는 스키마로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="78897-104">**XmlValidatingReader** maps the namespace URI in the XML document to the schema that corresponds to that URI in the collection.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78897-105">이제 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스는 사용되지 않으며 <xref:System.Xml.Schema.XmlSchemaSet> 클래스로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="78897-105">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="78897-106"><xref:System.Xml.Schema.XmlSchemaSet> 클래스에 대한 자세한 내용은 [스키마 컴파일을 위한 XmlSchemaSet](xmlschemaset-for-schema-compilation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78897-106">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](xmlschemaset-for-schema-compilation.md).</span></span>

<span data-ttu-id="78897-107">예를 들어, XML 문서의 루트 요소가 `<bookstore>`일 경우 스키마를 **XmlSchemaCollection**에 추가하면 다음과 같이 동일한 네임스페이스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="78897-107">For example, if the root element of the XML document is `<bookstore>`, when the schema is added to the **XmlSchemaCollection** it references the same namespace, as follows:</span></span>

```vb
xsc.Add("urn:newbooks-schema", "newbooks.xdr")
```

```csharp
xsc.Add("urn:newbooks-schema", "newbooks.xdr");
```

<span data-ttu-id="78897-108">다음 코드 예제에서는 **XmlTextReader** 를 사용 하는 **XMLVALIDATINGREADER** 를 만들고 xdr 스키마를 **XmlSchemaCollection**에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="78897-108">The following code example creates an **XmlValidatingReader** that takes an **XmlTextReader** and adds an XDR schema, HeadCount.xdr, to the **XmlSchemaCollection**:</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Schema

Namespace ValidationSample

    Class Sample

        Public Shared Sub Main()
            Dim tr As New XmlTextReader("HeadCount.xml")
            Dim vr As New XmlValidatingReader(tr)

            vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr")
            vr.ValidationType = ValidationType.XDR
            AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler

            While vr.Read()
                PrintTypeInfo(vr)
                If vr.NodeType = XmlNodeType.Element Then
                    While vr.MoveToNextAttribute()
                        PrintTypeInfo(vr)
                    End While
                End If
            End While
            Console.WriteLine("Validation finished")
        End Sub

        Public Shared Sub PrintTypeInfo(vr As XmlValidatingReader)
            If vr.SchemaType IsNot Nothing Then
                If TypeOf vr.SchemaType Is XmlSchemaDatatype Or TypeOf vr.SchemaType Is XmlSchemaSimpleType Then
                    Dim value As Object = vr.ReadTypedValue()
                    Console.WriteLine($"{vr.NodeType}({vr.Name},{value.GetType().Name}):{value}")
                End If
            End If
        End Sub

        Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)
            Console.WriteLine("***Validation error")
            Console.WriteLine($"Severity:{args.Severity}")
            Console.WriteLine($"Message:{args.Message}")
        End Sub
    End Class
End Namespace
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Schema;

namespace ValidationSample
{
    class Sample
    {
        public static void Main()
        {
            var tr = new XmlTextReader("HeadCount.xml");
            var vr = new XmlValidatingReader(tr);

            vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr");
            vr.ValidationType = ValidationType.XDR;
            vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);

            while(vr.Read())
            {
                PrintTypeInfo(vr);
                if (vr.NodeType == XmlNodeType.Element)
                {
                   while(vr.MoveToNextAttribute())
                       PrintTypeInfo(vr);
                }
            }
            Console.WriteLine("Validation finished");
        }

        public static void PrintTypeInfo(XmlValidatingReader vr)
        {
            if (vr.SchemaType != null)
            {
                if(vr.SchemaType is XmlSchemaDatatype || vr.SchemaType is XmlSchemaSimpleType)
                {
                    object value = vr.ReadTypedValue();
                    Console.WriteLine($"{vr.NodeType}({vr.Name},{value.GetType().Name}):{value}");
                }
            }
        }

        public static void ValidationHandler(object sender, ValidationEventArgs args)
        {
            Console.WriteLine("***Validation error");
            Console.WriteLine($"\tSeverity:{args.Severity}");
            Console.WriteLine($"\tMessage:{args.Message}");
        }
    }
}
```

<span data-ttu-id="78897-109">다음에서는 유효성을 검사할 입력 파일 *HeadCount.xml*의 내용을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="78897-109">The following outlines the contents of the input file, *HeadCount.xml*, to be validated:</span></span>

```xml
<!--Load HeadCount.xdr in SchemaCollection for Validation-->
<HeadCount xmlns='xdrHeadCount'>
   <Name>Waldo Pepper</Name>
   <Name>Red Pepper</Name>
</HeadCount>
```

<span data-ttu-id="78897-110">다음에서는 유효성을 검사할 XDR 스키마 파일 *HeadCount.xdr*의 내용을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="78897-110">The following outlines the contents of the XDR schema file, *HeadCount.xdr*, to be validated against:</span></span>

```xml
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">
   <ElementType name="Name" content="textOnly"/>
   <AttributeType name="Bldg" default="2"/>
   <ElementType name="HeadCount" content="eltOnly">
      <element type="Name"/>
      <attribute type="Bldg"/>
   </ElementType>
</Schema>
```

## <a name="see-also"></a><span data-ttu-id="78897-111">참조</span><span class="sxs-lookup"><span data-stu-id="78897-111">See also</span></span>

- <xref:System.Xml.XmlValidatingReader.ValidationType%2A>
- [<span data-ttu-id="78897-112">XmlSchemaCollection 스키마 컴파일</span><span class="sxs-lookup"><span data-stu-id="78897-112">XmlSchemaCollection Schema Compilation</span></span>](xmlschemacollection-schema-compilation.md)
