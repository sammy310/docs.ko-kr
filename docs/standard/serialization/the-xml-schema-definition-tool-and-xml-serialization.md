---
title: XML 스키마 정의 도구 및 XML Serialization
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: b51b9a0112893d9a7838155f4af051e7079c8cdd
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588382"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="59381-102">XML 스키마 정의 도구 및 XML Serialization</span><span class="sxs-lookup"><span data-stu-id="59381-102">The XML Schema Definition Tool and XML Serialization</span></span>

<span data-ttu-id="59381-103">XML 스키마 정의 도구(XML[스키마 정의 도구(Xsd.exe))는](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)Windows&reg; 소프트웨어 개발 키트(SDK)의 일부로 .NET 프레임워크 도구와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="59381-103">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows&reg; Software Development Kit (SDK).</span></span> <span data-ttu-id="59381-104">이 도구는 주로 다음 두 가지 목적으로 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59381-104">The tool is designed primarily for two purposes:</span></span>  
  
- <span data-ttu-id="59381-105">특정 XSD(XML 스키마 정의 언어) 스키마를 따르는 C# 또는 Visual Basic 클래스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="59381-105">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="59381-106">이 도구는 XML 스키마를 인수로 받아서 <xref:System.Xml.Serialization.XmlSerializer>로 serialize될 때 스키마를 따르는 여러 클래스가 포함된 파일을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="59381-106">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="59381-107">도구를 사용하여 특정 스키마를 따르는 클래스를 생성하는 방법에 대한 자세한 내용은 [방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59381-107">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
- <span data-ttu-id="59381-108">.dll 파일 또는 .exe 파일에서 XML 스키마 문서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="59381-108">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="59381-109">만들었거나 특성으로 수정한 파일 집합의 스키마를 보려면 DLL 또는 EXE를 도구에 인수로 전달하여 XML 스키마를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="59381-109">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="59381-110">도구를 사용하여 클래스 집합에서 XML 스키마 문서를 생성하는 방법에 대한 자세한 내용은 [방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59381-110">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
<span data-ttu-id="59381-111">도구 사용에 대한 자세한 내용은 [XML 스키마 정의 도구(Xsd.exe)를](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59381-111">For more information about using the tool, see [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59381-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59381-112">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="59381-113">XML Serialization 소개</span><span class="sxs-lookup"><span data-stu-id="59381-113">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="59381-114">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="59381-114">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="59381-115">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="59381-115">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="59381-116">방법: 개체 역직렬화</span><span class="sxs-lookup"><span data-stu-id="59381-116">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [<span data-ttu-id="59381-117">방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성</span><span class="sxs-lookup"><span data-stu-id="59381-117">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- <span data-ttu-id="59381-118">[XML 스키마의 바인딩 지원](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="59381-118">[XML Schema Binding Support](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span></span>
