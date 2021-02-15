---
description: '자세한 정보: 방법: 파일, 문자열 또는 스트림에서 XML 로드 (Visual Basic)'
title: '방법: 파일, 문자열 또는 스트림에서 XML 로드'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 375190642c93d929abe2ae10bb6ccba927e3bc8a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480065"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="59b28-103">방법: 파일, 문자열 또는 스트림에서 XML 로드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59b28-103">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="59b28-104">[XML 리터럴을](../../../language-reference/xml-literals/index.md) 만들고 여러 메서드를 사용 하 여 파일, 문자열 또는 스트림과 같은 외부 소스의 콘텐츠로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59b28-104">You can create [XML Literals](../../../language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="59b28-105">이러한 메서드는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59b28-105">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="59b28-106">파일에서 XML을 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="59b28-106">To load XML from a file</span></span>

<span data-ttu-id="59b28-107">파일에서 또는 개체와 같은 XML 리터럴을 <xref:System.Xml.Linq.XElement> 채우려면 <xref:System.Xml.Linq.XDocument> 메서드를 사용 `Load` 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b28-107">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="59b28-108">이 메서드는 파일 경로, 텍스트 스트림 또는 XML 스트림을 입력으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59b28-108">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="59b28-109">다음 코드 예제에서는 메서드를 사용 하 여 <xref:System.Xml.Linq.XDocument.Load%28System.String%29> <xref:System.Xml.Linq.XDocument> 텍스트 파일의 XML로 개체를 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59b28-109">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="59b28-110">문자열에서 XML을 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="59b28-110">To load XML from a string</span></span>

<span data-ttu-id="59b28-111">문자열에서 또는 개체와 같은 XML 리터럴을 <xref:System.Xml.Linq.XElement> 채우려면 <xref:System.Xml.Linq.XDocument> 메서드를 사용할 수 있습니다 `Parse` .</span><span class="sxs-lookup"><span data-stu-id="59b28-111">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="59b28-112">다음 코드 예제에서는 메서드를 사용 하 여 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> <xref:System.Xml.Linq.XDocument> 문자열에서 XML로 개체를 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59b28-112">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="59b28-113">스트림에서 XML을 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="59b28-113">To load XML from a stream</span></span>

<span data-ttu-id="59b28-114">스트림에서 또는 개체와 같은 XML 리터럴을 채우려면 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> 메서드 또는 메서드를 사용할 수 있습니다 `Load` <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="59b28-114">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="59b28-115">다음 코드 예제에서는 메서드를 사용 하 여 <xref:System.Xml.Linq.XNode.ReadFrom%2A> <xref:System.Xml.Linq.XDocument> XML 스트림의 xml로 개체를 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59b28-115">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="59b28-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="59b28-116">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="59b28-117">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="59b28-117">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
- [<span data-ttu-id="59b28-118">XML</span><span class="sxs-lookup"><span data-stu-id="59b28-118">XML</span></span>](index.md)
- [<span data-ttu-id="59b28-119">Visual Basic에서 XML 조작</span><span class="sxs-lookup"><span data-stu-id="59b28-119">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
