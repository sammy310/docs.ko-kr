---
title: Imports 문-XML 네임 스페이스 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 0fca0caecfd69580510a539317856209108e5a32
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581761"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="27dc9-102">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="27dc9-102">Imports Statement (XML Namespace)</span></span>

<span data-ttu-id="27dc9-103">Xml 리터럴 및 XML 축 속성에 사용할 XML 네임 스페이스 접두사를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="27dc9-104">구문</span><span class="sxs-lookup"><span data-stu-id="27dc9-104">Syntax</span></span>

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a><span data-ttu-id="27dc9-105">요소</span><span class="sxs-lookup"><span data-stu-id="27dc9-105">Parts</span></span>

`xmlNamespacePrefix`  
<span data-ttu-id="27dc9-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="27dc9-106">Optional.</span></span> <span data-ttu-id="27dc9-107">XML 요소와 특성이 `xmlNamespaceName`를 참조할 수 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="27dc9-108">@No__t_0 제공 되지 않으면 가져온 XML 네임 스페이스가 기본 XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="27dc9-109">유효한 XML 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="27dc9-110">자세한 내용은 [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27dc9-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>

`xmlNamespaceName`  
<span data-ttu-id="27dc9-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="27dc9-111">Required.</span></span> <span data-ttu-id="27dc9-112">가져올 XML 네임 스페이스를 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-112">The string identifying the XML namespace being imported.</span></span>

## <a name="remarks"></a><span data-ttu-id="27dc9-113">주의</span><span class="sxs-lookup"><span data-stu-id="27dc9-113">Remarks</span></span>

<span data-ttu-id="27dc9-114">@No__t_0 문을 사용 하 여 XML 리터럴 및 XML 축 속성에 사용할 수 있는 전역 XML 네임 스페이스를 정의 하거나 `GetXmlNamespace` 연산자에 전달 되는 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="27dc9-115">@No__t_0 문을 사용 하 여 코드에서 형식 이름을 사용 하는 데 사용할 수 있는 별칭을 가져오는 방법에 대 한 자세한 내용은 [Imports 문 (.Net 네임 스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조 하세요. @No__t_2 문을 사용 하 여 XML 네임 스페이스를 선언 하는 구문은 XML에서 사용 되는 구문과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="27dc9-116">따라서 XML 파일에서 네임 스페이스 선언을 복사 하 여 `Imports` 문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>

<span data-ttu-id="27dc9-117">XML 네임 스페이스 접두사는 동일한 네임 스페이스에 있는 XML 요소를 반복 해 서 만들려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="27dc9-118">@No__t_0 문으로 선언 된 XML 네임 스페이스 접두사는 파일의 모든 코드에서 사용할 수 있다는 점에서 전역적입니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="27dc9-119">Xml 요소 리터럴을 만들 때와 XML 축 속성에 액세스할 때이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="27dc9-120">자세한 내용은 [Xml 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [xml 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27dc9-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

<span data-ttu-id="27dc9-121">네임 스페이스 접두사 없이 전역 XML 네임 스페이스를 정의 하는 경우 (예: `Imports <xmlns="http://SomeNameSpace>"`) 해당 네임 스페이스는 기본 XML 네임 스페이스로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="27dc9-122">기본 XML 네임 스페이스는 네임 스페이스를 명시적으로 지정 하지 않는 모든 XML 요소 리터럴 또는 XML 특성 축 속성에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="27dc9-123">기본 네임 스페이스는 지정 된 네임 스페이스가 빈 네임 스페이스 (즉, `xmlns=""`) 인 경우에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="27dc9-124">기본 XML 네임 스페이스는 xml 리터럴의 XML 특성이 나 네임 스페이스를 포함 하지 않는 XML 특성 축 속성에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>

<span data-ttu-id="27dc9-125">*로컬 xml 네임 스페이스*라고 하는 xml 리터럴에 정의 된 xml 네임 스페이스는 `Imports` 문에서 전역으로 정의 된 xml 네임 스페이스 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="27dc9-126">@No__t_0 문으로 정의 된 XML 네임 스페이스는 Visual Basic 프로젝트에 대해 가져온 XML 네임 스페이스 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="27dc9-127">Xml 리터럴이 XML 네임 스페이스를 정의 하는 경우 해당 로컬 네임 스페이스는 포함 식에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>

<span data-ttu-id="27dc9-128">전역 XML 네임 스페이스는 .NET Framework 네임 스페이스와 동일한 범위 지정 및 정의 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="27dc9-129">따라서 `Imports` 문을 포함 하 여 .NET Framework 네임 스페이스를 가져올 수 있는 위치에 전역 XML 네임 스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="27dc9-130">여기에는 코드 파일과 프로젝트 수준 가져온 네임 스페이스가 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="27dc9-131">프로젝트 수준에서 가져온 네임 스페이스에 대 한 자세한 내용은 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27dc9-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="27dc9-132">각 소스 파일에는 개수에 관계 없이 `Imports` 문이 모두 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="27dc9-133">이는 `Option Strict` 문과 같은 옵션 선언을 따라야 하며 `Module` 또는 `Class` 문과 같은 프로그래밍 요소 선언 앞에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>

## <a name="example"></a><span data-ttu-id="27dc9-134">예제</span><span class="sxs-lookup"><span data-stu-id="27dc9-134">Example</span></span>

<span data-ttu-id="27dc9-135">다음 예에서는 `ns` 접두사를 사용 하 여 식별 되는 기본 XML 네임 스페이스와 XML 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="27dc9-136">그런 다음 두 네임 스페이스를 모두 사용 하는 XML 리터럴을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-136">It then creates XML literals that use both namespaces.</span></span>

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

<span data-ttu-id="27dc9-137">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-137">This code displays the following text:</span></span>

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a><span data-ttu-id="27dc9-138">예제</span><span class="sxs-lookup"><span data-stu-id="27dc9-138">Example</span></span>

<span data-ttu-id="27dc9-139">다음 예에서는 `ns` XML 네임 스페이스 접두사를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="27dc9-140">그런 다음 네임 스페이스 접두사를 사용 하 고 요소의 최종 형식을 표시 하는 XML 리터럴을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="27dc9-141">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-141">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="27dc9-142">컴파일러는 XML 네임 스페이스 접두사를 전역 접두사에서 로컬 접두사 정의로 변환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>

## <a name="example"></a><span data-ttu-id="27dc9-143">예제</span><span class="sxs-lookup"><span data-stu-id="27dc9-143">Example</span></span>

<span data-ttu-id="27dc9-144">다음 예에서는 `ns` XML 네임 스페이스 접두사를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="27dc9-145">네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

<span data-ttu-id="27dc9-146">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27dc9-146">This code displays the following text:</span></span>

`Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="27dc9-147">참조</span><span class="sxs-lookup"><span data-stu-id="27dc9-147">See also</span></span>

- [<span data-ttu-id="27dc9-148">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="27dc9-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="27dc9-149">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="27dc9-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="27dc9-150">선언된 XML 요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="27dc9-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="27dc9-151">GetXmlNamespace 연산자</span><span class="sxs-lookup"><span data-stu-id="27dc9-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
