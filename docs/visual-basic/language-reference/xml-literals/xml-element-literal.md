---
description: '자세한 정보: XML 요소 리터럴 (Visual Basic)'
title: XML 요소 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: dfc78beded5c6f472b67fa272835ef0aa29d0187
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787541"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="7cab7-103">XML 요소 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7cab7-103">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="7cab7-104">개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="7cab7-104">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="7cab7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cab7-105">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="7cab7-106">부분</span><span class="sxs-lookup"><span data-stu-id="7cab7-106">Parts</span></span>

- `<`

  <span data-ttu-id="7cab7-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-107">Required.</span></span> <span data-ttu-id="7cab7-108">시작 요소 태그를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-108">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="7cab7-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-109">Required.</span></span> <span data-ttu-id="7cab7-110">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-110">Name of the element.</span></span> <span data-ttu-id="7cab7-111">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-111">The format is one of the following:</span></span>

  - <span data-ttu-id="7cab7-112">다음 형식의 요소 이름에 대 한 리터럴 텍스트입니다 `[ePrefix:]eName` .</span><span class="sxs-lookup"><span data-stu-id="7cab7-112">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="7cab7-113">파트</span><span class="sxs-lookup"><span data-stu-id="7cab7-113">Part</span></span>|<span data-ttu-id="7cab7-114">설명</span><span class="sxs-lookup"><span data-stu-id="7cab7-114">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="7cab7-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-115">Optional.</span></span> <span data-ttu-id="7cab7-116">요소에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-116">XML namespace prefix for the element.</span></span> <span data-ttu-id="7cab7-117">`Imports`는 파일이 나 프로젝트 수준의 문으로 정의 되거나이 요소 또는 부모 요소에 정의 된 로컬 xml 네임 스페이스에 정의 된 전역 xml 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-117">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="7cab7-118">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-118">Required.</span></span> <span data-ttu-id="7cab7-119">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-119">Name of the element.</span></span> <span data-ttu-id="7cab7-120">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-120">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="7cab7-121">-리터럴 텍스트</span><span class="sxs-lookup"><span data-stu-id="7cab7-121">- Literal text.</span></span> <span data-ttu-id="7cab7-122">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cab7-122">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="7cab7-123">-폼의 포함 식 `<%= eNameExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-123">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="7cab7-124">의 형식은 `eNameExp` `String` 이거나로 암시적으로 변환할 수 있는 형식 이어야 합니다 <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="7cab7-124">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="7cab7-125">형식의 포함 된 식 `<%= nameExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-125">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="7cab7-126">의 형식은 `nameExp` `String` 이거나로 암시적으로 변환할 수 있는 형식 이어야 합니다 <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="7cab7-126">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="7cab7-127">요소의 닫는 태그에는 포함 식이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-127">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="7cab7-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-128">Optional.</span></span> <span data-ttu-id="7cab7-129">리터럴에 선언 된 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-129">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="7cab7-130">각 `attribute` 에는 다음 구문 중 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-130">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="7cab7-131">형식의 특성 할당은 `[aPrefix:]aName=aValue` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-131">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="7cab7-132">파트</span><span class="sxs-lookup"><span data-stu-id="7cab7-132">Part</span></span>|<span data-ttu-id="7cab7-133">설명</span><span class="sxs-lookup"><span data-stu-id="7cab7-133">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="7cab7-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-134">Optional.</span></span> <span data-ttu-id="7cab7-135">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-135">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="7cab7-136">는 `Imports` 문 또는이 요소 또는 부모 요소에 정의 된 로컬 xml 네임 스페이스를 사용 하 여 정의 된 전역 xml 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-136">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="7cab7-137">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-137">Required.</span></span> <span data-ttu-id="7cab7-138">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-138">Name of the attribute.</span></span> <span data-ttu-id="7cab7-139">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-139">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="7cab7-140">-리터럴 텍스트</span><span class="sxs-lookup"><span data-stu-id="7cab7-140">- Literal text.</span></span> <span data-ttu-id="7cab7-141">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cab7-141">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="7cab7-142">-폼의 포함 식 `<%= aNameExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-142">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="7cab7-143">의 형식은 `aNameExp` `String` 이거나로 암시적으로 변환할 수 있는 형식 이어야 합니다 <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="7cab7-143">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="7cab7-144">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-144">Optional.</span></span> <span data-ttu-id="7cab7-145">특성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-145">Value of the attribute.</span></span> <span data-ttu-id="7cab7-146">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-146">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="7cab7-147">-따옴표로 묶인 리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-147">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="7cab7-148">-폼의 포함 식 `<%= aValueExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-148">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="7cab7-149">모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-149">Any type is allowed.</span></span>|

  - <span data-ttu-id="7cab7-150">형식의 포함 된 식 `<%= aExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-150">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="7cab7-151">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-151">Optional.</span></span> <span data-ttu-id="7cab7-152">요소가 콘텐츠가 없는 빈 요소 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-152">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="7cab7-153">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-153">Required.</span></span> <span data-ttu-id="7cab7-154">시작 또는 빈 요소 태그를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-154">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="7cab7-155">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-155">Optional.</span></span> <span data-ttu-id="7cab7-156">요소의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-156">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="7cab7-157">각 `content` 항목은 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-157">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="7cab7-158">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-158">Literal text.</span></span> <span data-ttu-id="7cab7-159">리터럴 텍스트가 있는 경우의 모든 공백은 `elementContents` 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-159">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="7cab7-160">형식의 포함 된 식 `<%= contentExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-160">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="7cab7-161">XML 요소 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-161">XML element literal.</span></span>

  - <span data-ttu-id="7cab7-162">XML 주석 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-162">XML comment literal.</span></span> <span data-ttu-id="7cab7-163">[XML 주석 리터럴](xml-comment-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cab7-163">See [XML Comment Literal](xml-comment-literal.md).</span></span>

  - <span data-ttu-id="7cab7-164">XML 처리 명령 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-164">XML processing instruction literal.</span></span> <span data-ttu-id="7cab7-165">[XML 처리 명령 리터럴](xml-processing-instruction-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cab7-165">See [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="7cab7-166">XML CDATA 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-166">XML CDATA literal.</span></span> <span data-ttu-id="7cab7-167">[XML CDATA 리터럴](xml-cdata-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cab7-167">See [XML CDATA Literal](xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="7cab7-168">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-168">Optional.</span></span> <span data-ttu-id="7cab7-169">요소의 닫는 태그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-169">Represents the closing tag for the element.</span></span> <span data-ttu-id="7cab7-170">선택적 `name` 매개 변수는 포함 된 식의 결과일 때 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-170">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="7cab7-171">Return Value</span><span class="sxs-lookup"><span data-stu-id="7cab7-171">Return Value</span></span>

<span data-ttu-id="7cab7-172"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-172">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7cab7-173">설명</span><span class="sxs-lookup"><span data-stu-id="7cab7-173">Remarks</span></span>

<span data-ttu-id="7cab7-174">XML 요소 리터럴 구문을 사용 하 여 코드에서 개체를 만들 수 있습니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="7cab7-174">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="7cab7-175">XML 리터럴은 줄 연속 문자를 사용 하지 않고 여러 줄에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-175">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="7cab7-176">이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-176">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="7cab7-177">양식의 포함 식을 `<%= exp %>` 사용 하면 XML 요소 리터럴에 동적 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-177">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="7cab7-178">자세한 내용은 [XML의 포함 식](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cab7-178">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="7cab7-179">Visual Basic 컴파일러는 XML 요소 리터럴을 생성자에 대 한 호출로 변환 <xref:System.Xml.Linq.XElement.%23ctor%2A> 하 고 필요한 경우 생성자를 호출 합니다 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="7cab7-179">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="7cab7-180">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7cab7-180">XML Namespaces</span></span>

<span data-ttu-id="7cab7-181">XML 네임 스페이스 접두사는 동일한 네임 스페이스의 요소를 사용 하 여 코드에서 여러 번 XML 리터럴을 만들어야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-181">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="7cab7-182">문을 사용 하 여 정의 하는 전역 XML 네임 스페이스 접두사 `Imports` 또는 특성 구문을 사용 하 여 정의 하는 로컬 접두사를 사용할 수 있습니다 `xmlns:xmlPrefix="xmlNamespace"` .</span><span class="sxs-lookup"><span data-stu-id="7cab7-182">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="7cab7-183">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cab7-183">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="7cab7-184">XML 네임 스페이스에 대 한 범위 지정 규칙에 따라 지역 접두사는 전역 접두사 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-184">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="7cab7-185">그러나 XML 리터럴이 XML 네임 스페이스를 정의 하는 경우 해당 네임 스페이스는 포함 된 식에 표시 되는 식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-185">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="7cab7-186">포함 된 식은 전역 XML 네임 스페이스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-186">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="7cab7-187">Visual Basic 컴파일러는 XML 리터럴에 사용 되는 각 전역 XML 네임 스페이스를 생성 된 코드에서 하나의 로컬 네임 스페이스 정의로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-187">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="7cab7-188">사용 되지 않는 전역 XML 네임 스페이스는 생성 된 코드에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-188">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="7cab7-189">예제</span><span class="sxs-lookup"><span data-stu-id="7cab7-189">Example</span></span>

<span data-ttu-id="7cab7-190">다음 예제에서는 두 개의 중첩 된 빈 요소가 있는 간단한 XML 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-190">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="7cab7-191">이 예제에서는 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-191">The example displays the following text.</span></span> <span data-ttu-id="7cab7-192">리터럴은 빈 요소의 구조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-192">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="7cab7-193">예제</span><span class="sxs-lookup"><span data-stu-id="7cab7-193">Example</span></span>

<span data-ttu-id="7cab7-194">다음 예제에서는 포함 식을 사용 하 여 요소의 이름을로 하 고 특성을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-194">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="7cab7-195">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-195">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="7cab7-196">예제</span><span class="sxs-lookup"><span data-stu-id="7cab7-196">Example</span></span>

<span data-ttu-id="7cab7-197">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="7cab7-197">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="7cab7-198">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 요소의 최종 형식을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-198">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="7cab7-199">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-199">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="7cab7-200">컴파일러가 전역 XML 네임 스페이스의 접두사를 XML 네임 스페이스에 대 한 접두사 정의로 변환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7cab7-200">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="7cab7-201">\<ns:middle>요소는 요소에 대 한 XML 네임 스페이스 접두사를 다시 정의 합니다 \<ns:inner1> .</span><span class="sxs-lookup"><span data-stu-id="7cab7-201">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="7cab7-202">그러나 요소는 \<ns:inner2> 문에 의해 정의 된 네임 스페이스를 사용 합니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="7cab7-202">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cab7-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7cab7-203">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="7cab7-204">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="7cab7-204">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="7cab7-205">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="7cab7-205">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="7cab7-206">XML CDATA 리터럴</span><span class="sxs-lookup"><span data-stu-id="7cab7-206">XML CDATA Literal</span></span>](xml-cdata-literal.md)
- [<span data-ttu-id="7cab7-207">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="7cab7-207">XML Literals</span></span>](index.md)
- [<span data-ttu-id="7cab7-208">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="7cab7-208">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="7cab7-209">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="7cab7-209">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="7cab7-210">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="7cab7-210">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
