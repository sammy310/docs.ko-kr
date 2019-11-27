---
title: XML 요소 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347022"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="65d48-102">XML 요소 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65d48-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="65d48-103"><xref:System.Xml.Linq.XElement> 개체를 나타내는 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="65d48-104">구문</span><span class="sxs-lookup"><span data-stu-id="65d48-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="65d48-105">요소</span><span class="sxs-lookup"><span data-stu-id="65d48-105">Parts</span></span>

- `<`

  <span data-ttu-id="65d48-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-106">Required.</span></span> <span data-ttu-id="65d48-107">시작 요소 태그를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="65d48-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-108">Required.</span></span> <span data-ttu-id="65d48-109">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-109">Name of the element.</span></span> <span data-ttu-id="65d48-110">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-110">The format is one of the following:</span></span>

  - <span data-ttu-id="65d48-111">`[ePrefix:]eName`폼의 요소 이름에 대 한 리터럴 텍스트입니다. 여기에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="65d48-112">파트</span><span class="sxs-lookup"><span data-stu-id="65d48-112">Part</span></span>|<span data-ttu-id="65d48-113">설명</span><span class="sxs-lookup"><span data-stu-id="65d48-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="65d48-114">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="65d48-114">Optional.</span></span> <span data-ttu-id="65d48-115">요소에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="65d48-116">는 파일이 나 프로젝트 수준에서 `Imports` 문으로 정의 된 전역 XML 네임 스페이스 또는이 요소 또는 부모 요소에 정의 된 로컬 XML 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="65d48-117">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-117">Required.</span></span> <span data-ttu-id="65d48-118">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-118">Name of the element.</span></span> <span data-ttu-id="65d48-119">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="65d48-120">-리터럴 텍스트</span><span class="sxs-lookup"><span data-stu-id="65d48-120">- Literal text.</span></span> <span data-ttu-id="65d48-121">[선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65d48-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="65d48-122">-`<%= eNameExp %>`폼의 포함 식입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="65d48-123">`eNameExp` 형식은 `String` 이거나 <xref:System.Xml.Linq.XName>으로 암시적으로 변환할 수 있는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="65d48-124">`<%= nameExp %>`폼의 포함 된 식입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="65d48-125">`nameExp` 형식은 `String` 이거나 <xref:System.Xml.Linq.XName>으로 암시적으로 변환할 수 있는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="65d48-126">요소의 닫는 태그에는 포함 식이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="65d48-127">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="65d48-127">Optional.</span></span> <span data-ttu-id="65d48-128">리터럴에 선언 된 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="65d48-129">각 `attribute`에는 다음 구문 중 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="65d48-130">`[aPrefix:]aName=aValue`형식의 특성 할당:</span><span class="sxs-lookup"><span data-stu-id="65d48-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="65d48-131">파트</span><span class="sxs-lookup"><span data-stu-id="65d48-131">Part</span></span>|<span data-ttu-id="65d48-132">설명</span><span class="sxs-lookup"><span data-stu-id="65d48-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="65d48-133">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="65d48-133">Optional.</span></span> <span data-ttu-id="65d48-134">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="65d48-135">는이 요소 또는 부모 요소에 정의 된 `Imports` 문 또는 로컬 XML 네임 스페이스를 사용 하 여 정의 된 전역 XML 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="65d48-136">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-136">Required.</span></span> <span data-ttu-id="65d48-137">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-137">Name of the attribute.</span></span> <span data-ttu-id="65d48-138">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="65d48-139">-리터럴 텍스트</span><span class="sxs-lookup"><span data-stu-id="65d48-139">- Literal text.</span></span> <span data-ttu-id="65d48-140">[선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65d48-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="65d48-141">-`<%= aNameExp %>`폼의 포함 식입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="65d48-142">`aNameExp` 형식은 `String` 이거나 <xref:System.Xml.Linq.XName>으로 암시적으로 변환할 수 있는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="65d48-143">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="65d48-143">Optional.</span></span> <span data-ttu-id="65d48-144">특성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-144">Value of the attribute.</span></span> <span data-ttu-id="65d48-145">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="65d48-146">-따옴표로 묶인 리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="65d48-147">-`<%= aValueExp %>`폼의 포함 식입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="65d48-148">모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="65d48-149">`<%= aExp %>`폼의 포함 된 식입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="65d48-150">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="65d48-150">Optional.</span></span> <span data-ttu-id="65d48-151">요소가 콘텐츠가 없는 빈 요소 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="65d48-152">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-152">Required.</span></span> <span data-ttu-id="65d48-153">시작 또는 빈 요소 태그를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="65d48-154">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="65d48-154">Optional.</span></span> <span data-ttu-id="65d48-155">요소의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="65d48-156">각 `content` 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="65d48-157">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-157">Literal text.</span></span> <span data-ttu-id="65d48-158">리터럴 텍스트가 있는 경우 `elementContents`의 모든 공백은 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="65d48-159">`<%= contentExp %>`폼의 포함 된 식입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="65d48-160">XML 요소 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-160">XML element literal.</span></span>

  - <span data-ttu-id="65d48-161">XML 주석 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-161">XML comment literal.</span></span> <span data-ttu-id="65d48-162">[XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65d48-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>

  - <span data-ttu-id="65d48-163">XML 처리 명령 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-163">XML processing instruction literal.</span></span> <span data-ttu-id="65d48-164">[XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65d48-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="65d48-165">XML CDATA 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-165">XML CDATA literal.</span></span> <span data-ttu-id="65d48-166">[XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65d48-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="65d48-167">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="65d48-167">Optional.</span></span> <span data-ttu-id="65d48-168">요소의 닫는 태그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="65d48-169">선택적인 `name` 매개 변수는 포함 된 식의 결과일 때 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="65d48-170">반환 값</span><span class="sxs-lookup"><span data-stu-id="65d48-170">Return Value</span></span>

<span data-ttu-id="65d48-171"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="65d48-172">주의</span><span class="sxs-lookup"><span data-stu-id="65d48-172">Remarks</span></span>

<span data-ttu-id="65d48-173">XML 요소 리터럴 구문을 사용 하 여 코드에 <xref:System.Xml.Linq.XElement> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="65d48-174">XML 리터럴은 줄 연속 문자를 사용 하지 않고 여러 줄에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="65d48-175">이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="65d48-176">`<%= exp %>` 형식의 포함 식을 사용 하면 XML 요소 리터럴에 동적 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="65d48-177">자세한 내용은 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65d48-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="65d48-178">Visual Basic 컴파일러는 XML 요소 리터럴을 <xref:System.Xml.Linq.XElement.%23ctor%2A> 생성자에 대 한 호출로 변환 하 고 필요한 경우 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="65d48-179">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="65d48-179">XML Namespaces</span></span>

<span data-ttu-id="65d48-180">XML 네임 스페이스 접두사는 동일한 네임 스페이스의 요소를 사용 하 여 코드에서 여러 번 XML 리터럴을 만들어야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="65d48-181">`xmlns:xmlPrefix="xmlNamespace"` 특성 구문을 사용 하 여 정의 하는 `Imports` 문 또는 로컬 접두사를 사용 하 여 정의 하는 전역 XML 네임 스페이스 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="65d48-182">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65d48-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="65d48-183">XML 네임 스페이스에 대 한 범위 지정 규칙에 따라 지역 접두사는 전역 접두사 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="65d48-184">그러나 XML 리터럴이 XML 네임 스페이스를 정의 하는 경우 해당 네임 스페이스는 포함 된 식에 표시 되는 식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="65d48-185">포함 된 식은 전역 XML 네임 스페이스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="65d48-186">Visual Basic 컴파일러는 XML 리터럴에 사용 되는 각 전역 XML 네임 스페이스를 생성 된 코드에서 하나의 로컬 네임 스페이스 정의로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="65d48-187">사용 되지 않는 전역 XML 네임 스페이스는 생성 된 코드에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="65d48-188">예제</span><span class="sxs-lookup"><span data-stu-id="65d48-188">Example</span></span>

<span data-ttu-id="65d48-189">다음 예제에서는 두 개의 중첩 된 빈 요소가 있는 간단한 XML 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="65d48-190">이 예제에서는 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-190">The example displays the following text.</span></span> <span data-ttu-id="65d48-191">리터럴은 빈 요소의 구조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="65d48-192">예제</span><span class="sxs-lookup"><span data-stu-id="65d48-192">Example</span></span>

<span data-ttu-id="65d48-193">다음 예제에서는 포함 식을 사용 하 여 요소의 이름을로 하 고 특성을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="65d48-194">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="65d48-195">예제</span><span class="sxs-lookup"><span data-stu-id="65d48-195">Example</span></span>

<span data-ttu-id="65d48-196">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="65d48-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="65d48-197">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 요소의 최종 형식을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="65d48-198">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="65d48-199">컴파일러가 전역 XML 네임 스페이스의 접두사를 XML 네임 스페이스에 대 한 접두사 정의로 변환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="65d48-200">\<ns: 중간 > 요소는 \<ns: inner1 > 요소에 대 한 XML 네임 스페이스 접두사를 다시 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="65d48-201">그러나 \<ns: inner2 > 요소는 `Imports` 문에 의해 정의 된 네임 스페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d48-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="65d48-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65d48-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="65d48-203">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="65d48-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="65d48-204">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="65d48-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="65d48-205">XML CDATA 리터럴</span><span class="sxs-lookup"><span data-stu-id="65d48-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="65d48-206">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="65d48-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="65d48-207">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="65d48-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="65d48-208">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="65d48-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="65d48-209">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="65d48-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
