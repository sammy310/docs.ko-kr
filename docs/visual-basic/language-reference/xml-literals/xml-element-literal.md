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
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400191"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="a2cfa-102">XML 요소 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2cfa-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="a2cfa-103">개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2cfa-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2cfa-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="a2cfa-105">부분</span><span class="sxs-lookup"><span data-stu-id="a2cfa-105">Parts</span></span>

- `<`

  <span data-ttu-id="a2cfa-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-106">Required.</span></span> <span data-ttu-id="a2cfa-107">시작 요소 태그를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="a2cfa-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-108">Required.</span></span> <span data-ttu-id="a2cfa-109">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-109">Name of the element.</span></span> <span data-ttu-id="a2cfa-110">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-110">The format is one of the following:</span></span>

  - <span data-ttu-id="a2cfa-111">다음 형식의 요소 이름에 대 한 리터럴 텍스트입니다 `[ePrefix:]eName` .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="a2cfa-112">부분</span><span class="sxs-lookup"><span data-stu-id="a2cfa-112">Part</span></span>|<span data-ttu-id="a2cfa-113">Description</span><span class="sxs-lookup"><span data-stu-id="a2cfa-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="a2cfa-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-114">Optional.</span></span> <span data-ttu-id="a2cfa-115">요소에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="a2cfa-116">`Imports`는 파일이 나 프로젝트 수준의 문으로 정의 되거나이 요소 또는 부모 요소에 정의 된 로컬 xml 네임 스페이스에 정의 된 전역 xml 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="a2cfa-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-117">Required.</span></span> <span data-ttu-id="a2cfa-118">요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-118">Name of the element.</span></span> <span data-ttu-id="a2cfa-119">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="a2cfa-120">-리터럴 텍스트</span><span class="sxs-lookup"><span data-stu-id="a2cfa-120">- Literal text.</span></span> <span data-ttu-id="a2cfa-121">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-121">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="a2cfa-122">-폼의 포함 식 `<%= eNameExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="a2cfa-123">의 형식은 `eNameExp` `String` 이거나로 암시적으로 변환할 수 있는 형식 이어야 합니다 <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="a2cfa-124">형식의 포함 된 식 `<%= nameExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="a2cfa-125">의 형식은 `nameExp` `String` 이거나로 암시적으로 변환할 수 있는 형식 이어야 합니다 <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="a2cfa-126">요소의 닫는 태그에는 포함 식이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="a2cfa-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-127">Optional.</span></span> <span data-ttu-id="a2cfa-128">리터럴에 선언 된 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="a2cfa-129">각 `attribute` 에는 다음 구문 중 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="a2cfa-130">형식의 특성 할당은 `[aPrefix:]aName=aValue` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="a2cfa-131">부분</span><span class="sxs-lookup"><span data-stu-id="a2cfa-131">Part</span></span>|<span data-ttu-id="a2cfa-132">Description</span><span class="sxs-lookup"><span data-stu-id="a2cfa-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="a2cfa-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-133">Optional.</span></span> <span data-ttu-id="a2cfa-134">특성에 대 한 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="a2cfa-135">는 `Imports` 문 또는이 요소 또는 부모 요소에 정의 된 로컬 xml 네임 스페이스를 사용 하 여 정의 된 전역 xml 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="a2cfa-136">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-136">Required.</span></span> <span data-ttu-id="a2cfa-137">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-137">Name of the attribute.</span></span> <span data-ttu-id="a2cfa-138">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="a2cfa-139">-리터럴 텍스트</span><span class="sxs-lookup"><span data-stu-id="a2cfa-139">- Literal text.</span></span> <span data-ttu-id="a2cfa-140">[선언 된 XML 요소 및 특성의 이름](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-140">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="a2cfa-141">-폼의 포함 식 `<%= aNameExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="a2cfa-142">의 형식은 `aNameExp` `String` 이거나로 암시적으로 변환할 수 있는 형식 이어야 합니다 <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="a2cfa-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-143">Optional.</span></span> <span data-ttu-id="a2cfa-144">특성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-144">Value of the attribute.</span></span> <span data-ttu-id="a2cfa-145">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="a2cfa-146">-따옴표로 묶인 리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="a2cfa-147">-폼의 포함 식 `<%= aValueExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="a2cfa-148">모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="a2cfa-149">형식의 포함 된 식 `<%= aExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="a2cfa-150">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-150">Optional.</span></span> <span data-ttu-id="a2cfa-151">요소가 콘텐츠가 없는 빈 요소 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="a2cfa-152">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-152">Required.</span></span> <span data-ttu-id="a2cfa-153">시작 또는 빈 요소 태그를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="a2cfa-154">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-154">Optional.</span></span> <span data-ttu-id="a2cfa-155">요소의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="a2cfa-156">각 `content` 항목은 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="a2cfa-157">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-157">Literal text.</span></span> <span data-ttu-id="a2cfa-158">리터럴 텍스트가 있는 경우의 모든 공백은 `elementContents` 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="a2cfa-159">형식의 포함 된 식 `<%= contentExp %>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="a2cfa-160">XML 요소 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-160">XML element literal.</span></span>

  - <span data-ttu-id="a2cfa-161">XML 주석 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-161">XML comment literal.</span></span> <span data-ttu-id="a2cfa-162">[XML 주석 리터럴](xml-comment-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-162">See [XML Comment Literal](xml-comment-literal.md).</span></span>

  - <span data-ttu-id="a2cfa-163">XML 처리 명령 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-163">XML processing instruction literal.</span></span> <span data-ttu-id="a2cfa-164">[XML 처리 명령 리터럴](xml-processing-instruction-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-164">See [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="a2cfa-165">XML CDATA 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-165">XML CDATA literal.</span></span> <span data-ttu-id="a2cfa-166">[XML CDATA 리터럴](xml-cdata-literal.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-166">See [XML CDATA Literal](xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="a2cfa-167">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-167">Optional.</span></span> <span data-ttu-id="a2cfa-168">요소의 닫는 태그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="a2cfa-169">선택적 `name` 매개 변수는 포함 된 식의 결과일 때 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="a2cfa-170">반환 값</span><span class="sxs-lookup"><span data-stu-id="a2cfa-170">Return Value</span></span>

<span data-ttu-id="a2cfa-171"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2cfa-172">설명</span><span class="sxs-lookup"><span data-stu-id="a2cfa-172">Remarks</span></span>

<span data-ttu-id="a2cfa-173">XML 요소 리터럴 구문을 사용 하 여 코드에서 개체를 만들 수 있습니다 <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="a2cfa-174">XML 리터럴은 줄 연속 문자를 사용 하지 않고 여러 줄에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="a2cfa-175">이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="a2cfa-176">양식의 포함 식을 `<%= exp %>` 사용 하면 XML 요소 리터럴에 동적 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="a2cfa-177">자세한 내용은 [XML의 포함 식](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-177">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="a2cfa-178">Visual Basic 컴파일러는 XML 요소 리터럴을 생성자에 대 한 호출로 변환 <xref:System.Xml.Linq.XElement.%23ctor%2A> 하 고 필요한 경우 생성자를 호출 합니다 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="a2cfa-179">XML 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a2cfa-179">XML Namespaces</span></span>

<span data-ttu-id="a2cfa-180">XML 네임 스페이스 접두사는 동일한 네임 스페이스의 요소를 사용 하 여 코드에서 여러 번 XML 리터럴을 만들어야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="a2cfa-181">문을 사용 하 여 정의 하는 전역 XML 네임 스페이스 접두사 `Imports` 또는 특성 구문을 사용 하 여 정의 하는 로컬 접두사를 사용할 수 있습니다 `xmlns:xmlPrefix="xmlNamespace"` .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="a2cfa-182">자세한 내용은 [Imports 문 (XML 네임 스페이스)](../statements/imports-statement-xml-namespace.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-182">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="a2cfa-183">XML 네임 스페이스에 대 한 범위 지정 규칙에 따라 지역 접두사는 전역 접두사 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="a2cfa-184">그러나 XML 리터럴이 XML 네임 스페이스를 정의 하는 경우 해당 네임 스페이스는 포함 된 식에 표시 되는 식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="a2cfa-185">포함 된 식은 전역 XML 네임 스페이스에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="a2cfa-186">Visual Basic 컴파일러는 XML 리터럴에 사용 되는 각 전역 XML 네임 스페이스를 생성 된 코드에서 하나의 로컬 네임 스페이스 정의로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="a2cfa-187">사용 되지 않는 전역 XML 네임 스페이스는 생성 된 코드에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="a2cfa-188">예제</span><span class="sxs-lookup"><span data-stu-id="a2cfa-188">Example</span></span>

<span data-ttu-id="a2cfa-189">다음 예제에서는 두 개의 중첩 된 빈 요소가 있는 간단한 XML 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="a2cfa-190">이 예제에서는 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-190">The example displays the following text.</span></span> <span data-ttu-id="a2cfa-191">리터럴은 빈 요소의 구조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="a2cfa-192">예제</span><span class="sxs-lookup"><span data-stu-id="a2cfa-192">Example</span></span>

<span data-ttu-id="a2cfa-193">다음 예제에서는 포함 식을 사용 하 여 요소의 이름을로 하 고 특성을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="a2cfa-194">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="a2cfa-195">예제</span><span class="sxs-lookup"><span data-stu-id="a2cfa-195">Example</span></span>

<span data-ttu-id="a2cfa-196">다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="a2cfa-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="a2cfa-197">그런 다음 네임 스페이스의 접두사를 사용 하 여 XML 리터럴을 만들고 요소의 최종 형식을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="a2cfa-198">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="a2cfa-199">컴파일러가 전역 XML 네임 스페이스의 접두사를 XML 네임 스페이스에 대 한 접두사 정의로 변환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cfa-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="a2cfa-200">\<ns:middle>요소는 요소에 대 한 XML 네임 스페이스 접두사를 다시 정의 합니다 \<ns:inner1> .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="a2cfa-201">그러나 요소는 \<ns:inner2> 문에 의해 정의 된 네임 스페이스를 사용 합니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="a2cfa-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2cfa-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2cfa-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="a2cfa-203">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="a2cfa-203">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="a2cfa-204">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="a2cfa-204">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="a2cfa-205">XML CDATA 리터럴</span><span class="sxs-lookup"><span data-stu-id="a2cfa-205">XML CDATA Literal</span></span>](xml-cdata-literal.md)
- [<span data-ttu-id="a2cfa-206">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="a2cfa-206">XML Literals</span></span>](index.md)
- [<span data-ttu-id="a2cfa-207">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="a2cfa-207">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="a2cfa-208">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="a2cfa-208">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="a2cfa-209">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="a2cfa-209">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
