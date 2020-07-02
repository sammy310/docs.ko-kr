---
ms.openlocfilehash: fdec6671cbf2dae0d72dfaec07f162058b38cf9d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620511"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a><span data-ttu-id="162db-101">XmlTextReader DTD 엔터티 확장은 10,000,000자로 제한됨</span><span class="sxs-lookup"><span data-stu-id="162db-101">XmlTextReader DTD entity expansion is limited to 10,000,000 characters</span></span>

#### <a name="details"></a><span data-ttu-id="162db-102">설명</span><span class="sxs-lookup"><span data-stu-id="162db-102">Details</span></span>

<span data-ttu-id="162db-103">이제 DTD 엔터티 확장은 10,000,000자로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="162db-103">DTD entity expansion is now limited to 10,000,000 characters.</span></span> <span data-ttu-id="162db-104">DTD 엔터티 확장 없이 또는 제한된 DTD 엔터티 확장으로 XML 파일을 로드해도 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="162db-104">Loading XML files without DTD entity expansion or with limited DTD entity expansion is unaffected.</span></span> <span data-ttu-id="162db-105">이제 파일에 10,000,000자를 초과하는 문자로 확장되는 DTD 엔터티가 있으면 로드하지 못하고 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="162db-105">Files with DTD entities that expand to more than 10,000,000 characters fail to load, and now throw an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="162db-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="162db-106">Suggestion</span></span>

<span data-ttu-id="162db-107">DTD 엔터티 확장의 제한이 10,000,000보다 너무 작으면, 값은 <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> 속성으로 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="162db-107">If the limit of DTD entity expansion is too low 10,000,000, the value can be overridden with the <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> property.</span></span> <span data-ttu-id="162db-108">올바른 <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> 값을 가진 <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>은 <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>(즉, <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)을 취하도록 <code>XmlReader.Create</code>에 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="162db-108">An <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> with the proper <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> value can be passed to <code>XmlReader.Create</code> that takes <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (ie. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)</span></span>

| <span data-ttu-id="162db-109">이름</span><span class="sxs-lookup"><span data-stu-id="162db-109">Name</span></span>    | <span data-ttu-id="162db-110">값</span><span class="sxs-lookup"><span data-stu-id="162db-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="162db-111">Scope</span><span class="sxs-lookup"><span data-stu-id="162db-111">Scope</span></span>   |<span data-ttu-id="162db-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="162db-112">Edge</span></span>|
|<span data-ttu-id="162db-113">버전</span><span class="sxs-lookup"><span data-stu-id="162db-113">Version</span></span>|<span data-ttu-id="162db-114">4.5</span><span class="sxs-lookup"><span data-stu-id="162db-114">4.5</span></span>|
|<span data-ttu-id="162db-115">형식</span><span class="sxs-lookup"><span data-stu-id="162db-115">Type</span></span>|<span data-ttu-id="162db-116">런타임</span><span class="sxs-lookup"><span data-stu-id="162db-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="162db-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="162db-117">Affected APIs</span></span>

-<xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)></li></ul>|
