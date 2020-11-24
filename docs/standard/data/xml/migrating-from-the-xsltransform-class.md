---
title: XslTransform 클래스에서 마이그레이션
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9404d758-679f-4ffb-995d-3d07d817659e
ms.openlocfilehash: b441e23b13983a0fdb54b7785e249a04bf1407c8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830209"
---
# <a name="migrating-from-the-xsltransform-class"></a><span data-ttu-id="492f8-102">XslTransform 클래스에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="492f8-102">Migrating From the XslTransform Class</span></span>

<span data-ttu-id="492f8-103">XSLT 아키텍처는 Visual Studio 2005 릴리스에서 다시 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-103">The XSLT architecture was redesigned in the Visual Studio 2005 release.</span></span> <span data-ttu-id="492f8-104"><xref:System.Xml.Xsl.XslTransform> 클래스는 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-104">The <xref:System.Xml.Xsl.XslTransform> class was replaced by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>

<span data-ttu-id="492f8-105">다음 단원에서는 <xref:System.Xml.Xsl.XslCompiledTransform> 및 <xref:System.Xml.Xsl.XslTransform> 클래스 사이의 주요 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-105">The following sections describe some of the main differences between the <xref:System.Xml.Xsl.XslCompiledTransform> and the <xref:System.Xml.Xsl.XslTransform> classes.</span></span>

## <a name="performance"></a><span data-ttu-id="492f8-106">성능</span><span class="sxs-lookup"><span data-stu-id="492f8-106">Performance</span></span>

<span data-ttu-id="492f8-107"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 여러 가지로 성능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class includes many performance improvements.</span></span> <span data-ttu-id="492f8-108">CLR(공용 언어 런타임)이 다른 프로그래밍 언어에 대해 수행하는 것과 비슷하게 새 XSLT 프로세서는 XSLT 스타일시트를 공용 중간 형식으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-108">The new XSLT processor compiles the XSLT style sheet down to a common intermediate format, similar to what the common language runtime (CLR) does for other programming languages.</span></span> <span data-ttu-id="492f8-109">스타일시트를 컴파일한 후 캐시하고 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-109">Once the style sheet is compiled, it can be cached and reused.</span></span>

<span data-ttu-id="492f8-110">또한 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 <xref:System.Xml.Xsl.XslTransform> 클래스보다 훨씬 빠르게 작동하도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-110">The <xref:System.Xml.Xsl.XslCompiledTransform> class also includes other optimizations that make it much faster than the <xref:System.Xml.Xsl.XslTransform> class.</span></span>

> [!NOTE]
> <span data-ttu-id="492f8-111"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스의 전체적인 성능이 <xref:System.Xml.Xsl.XslTransform> 클래스보다 좋지만 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스의 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 메서드는 변환에 대해 처음 호출될 때 <xref:System.Xml.Xsl.XslTransform> 클래스의 <xref:System.Xml.Xsl.XslTransform.Load%2A> 메서드보다 느리게 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-111">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="492f8-112">이는 XSLT 파일이 로드되기 전에 컴파일되어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-112">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="492f8-113">자세한 내용은 다음 블로그 게시물을 참조하세요. [XslCompiledTransform이 XslTransform보다 느리나요?](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span><span class="sxs-lookup"><span data-stu-id="492f8-113">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>

## <a name="security"></a><span data-ttu-id="492f8-114">보안</span><span class="sxs-lookup"><span data-stu-id="492f8-114">Security</span></span>

<span data-ttu-id="492f8-115"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 기본적으로 XSLT `document()` 함수 및 포함된 스크립팅에 대한 지원을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-115">By default, the <xref:System.Xml.Xsl.XslCompiledTransform> class disables support for the XSLT `document()` function and embedded scripting.</span></span> <span data-ttu-id="492f8-116">이 기능을 활성화하는 <xref:System.Xml.Xsl.XsltSettings> 개체를 만들고 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 메서드에 전달하여 이러한 기능을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-116">These features can be enabled by creating an <xref:System.Xml.Xsl.XsltSettings> object that has the features enabled and passing it to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span> <span data-ttu-id="492f8-117">다음 예제에서는 스크립팅을 활성화하고 XSLT 변환을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-117">The following example shows how to enable scripting and perform an XSLT transformation.</span></span>

[!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
[!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]

<span data-ttu-id="492f8-118">자세한 내용은 [XSLT 보안 고려 사항](xslt-security-considerations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="492f8-118">For more information, see [XSLT Security Considerations](xslt-security-considerations.md).</span></span>

## <a name="new-features"></a><span data-ttu-id="492f8-119">새 기능</span><span class="sxs-lookup"><span data-stu-id="492f8-119">New Features</span></span>

### <a name="temporary-files"></a><span data-ttu-id="492f8-120">임시 파일</span><span class="sxs-lookup"><span data-stu-id="492f8-120">Temporary Files</span></span>

<span data-ttu-id="492f8-121">XSLT를 처리하는 동안 임시 파일이 생성되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-121">Temporary files are sometimes generated during XSLT processing.</span></span> <span data-ttu-id="492f8-122">스타일시트에 스크립트 블록이 포함되었거나 디버그 설정이 true로 설정된 상태에서 스타일시트가 컴파일된 경우 %TEMP% 폴더에 임시 파일이 만들어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-122">If a style sheet contains script blocks, or if it is compiled with the debug setting set to true, temporary files may be created in the %TEMP% folder.</span></span> <span data-ttu-id="492f8-123">타이밍 문제로 인해 일부 임시 파일이 삭제되지 않을 때 이러한 경우가 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-123">There may be instances when some temporary files are not deleted due to timing issues.</span></span> <span data-ttu-id="492f8-124">예를 들어 파일이 현재 AppDomain 또는 디버거에서 사용 중인 경우 <xref:System.CodeDom.Compiler.TempFileCollection> 개체의 종료자는 파일을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-124">For example, if the files are in use by the current AppDomain or by the debugger, the finalizer of the <xref:System.CodeDom.Compiler.TempFileCollection> object will not be able to remove them.</span></span>

<span data-ttu-id="492f8-125">모든 임시 파일이 클라이언트에서 제거되도록 <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> 속성을 사용하여 추가 정리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-125">The <xref:System.Xml.Xsl.XslCompiledTransform.TemporaryFiles%2A> property can be used for additional cleanup to make sure that all temporary files are removed from the client.</span></span>

### <a name="support-for-the-xsloutput-element-and-xmlwriter"></a><span data-ttu-id="492f8-126">xsl:output 요소 및 XmlWriter 지원</span><span class="sxs-lookup"><span data-stu-id="492f8-126">Support for the xsl:output Element and XmlWriter</span></span>

<span data-ttu-id="492f8-127">변형 출력을 <xref:System.Xml.Xsl.XslTransform> 개체로 보낸 경우 `xsl:output` 클래스에서는 <xref:System.Xml.XmlWriter> 설정을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-127">The <xref:System.Xml.Xsl.XslTransform> class ignored `xsl:output` settings when the transform output was sent to an <xref:System.Xml.XmlWriter> object.</span></span> <span data-ttu-id="492f8-128"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 스타일시트의 <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A> 요소에서 파생된 출력 정보가 있는 <xref:System.Xml.XmlWriterSettings> 개체를 반환하는 `xsl:output` 개체를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-128">The <xref:System.Xml.Xsl.XslCompiledTransform> class has an <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A> property that returns an <xref:System.Xml.XmlWriterSettings> object containing the output information derived from the `xsl:output` element of the style sheet.</span></span> <span data-ttu-id="492f8-129"><xref:System.Xml.XmlWriterSettings> 개체를 사용하여 <xref:System.Xml.XmlWriter> 메서드로 전달될 수 있는 올바른 설정을 가진 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-129">The <xref:System.Xml.XmlWriterSettings> object is used to create an <xref:System.Xml.XmlWriter> object with the correct settings that can be passed to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span> <span data-ttu-id="492f8-130">다음 C# 코드에서는 이 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-130">The following C# code illustrates this behavior:</span></span>

```csharp
// Create the XslTransform object and load the style sheet.
XslCompiledTransform xslt = new XslCompiledTransform();
xslt.Load(stylesheet);

// Load the file to transform.
XPathDocument doc = new XPathDocument(filename);

// Create the writer.
XmlWriter writer = XmlWriter.Create(Console.Out, xslt.OutputSettings);

// Transform the file and send the output to the console.
xslt.Transform(doc, writer);
writer.Close();
```

### <a name="debug-option"></a><span data-ttu-id="492f8-131">디버그 옵션</span><span class="sxs-lookup"><span data-stu-id="492f8-131">Debug Option</span></span>

<span data-ttu-id="492f8-132"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 Microsoft Visual Studio Debugger에서 스타일시트를 디버그할 수 있는 디버그 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-132">The <xref:System.Xml.Xsl.XslCompiledTransform> class can generate debug information, which enables you to debug the style sheet with the Microsoft Visual Studio Debugger.</span></span> <span data-ttu-id="492f8-133">자세한 내용은 <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="492f8-133">See <xref:System.Xml.Xsl.XslCompiledTransform.%23ctor%28System.Boolean%29> for more information.</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="492f8-134">동작 차이점</span><span class="sxs-lookup"><span data-stu-id="492f8-134">Behavioral Differences</span></span>

### <a name="transforming-to-an-xmlreader"></a><span data-ttu-id="492f8-135">XmlReader로 변환</span><span class="sxs-lookup"><span data-stu-id="492f8-135">Transforming to an XmlReader</span></span>

<span data-ttu-id="492f8-136"><xref:System.Xml.Xsl.XslTransform> 클래스에는 변형 결과를 <xref:System.Xml.XmlReader> 개체로 반환하는 여러 변형 오버로드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-136">The <xref:System.Xml.Xsl.XslTransform> class has several Transform overloads that return transformation results as an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="492f8-137">이러한 오버로드를 사용하여 결과 XML 트리의 serialization 및 deserialization 오버헤드 없이 변형 결과를 메모리 내 표현(예: <xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathDocument>)으로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-137">These overloads can be used to load the transformation results into an in-memory representation (such as <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument>) without incurring the overhead of serialization and deserialization of the resulting XML tree.</span></span> <span data-ttu-id="492f8-138">다음 C# 코드에서는 변형 결과를 <xref:System.Xml.XmlDocument> 개체로 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-138">The following C# code shows how to load the transformation results into an <xref:System.Xml.XmlDocument> object.</span></span>

```csharp
// Load the style sheet
XslTransform xslt = new XslTransform();
xslt.Load("MyStylesheet.xsl");

// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
doc.Load(xslt.Transform(input, (XsltArgumentList)null));
```

<span data-ttu-id="492f8-139"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스에서는 <xref:System.Xml.XmlReader> 개체로 변환하는 작업을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-139">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not support transforming to an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="492f8-140">그러나 <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A>에서 직접 결과 XML 트리를 로드하기 위해 <xref:System.Xml.XmlWriter> 메서드를 사용하여 유사한 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-140">However, you can do something similar by using the <xref:System.Xml.XPath.XPathNavigator.CreateNavigator%2A> method to load the resulting XML tree directly from an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="492f8-141">다음 C# 코드에서는 <xref:System.Xml.Xsl.XslCompiledTransform>을 사용하여 동일한 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-141">The following C# code shows how to accomplish the same task using <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

```csharp
// Transform input document to XmlDocument for additional processing
XmlDocument doc = new XmlDocument();
using (XmlWriter writer = doc.CreateNavigator().AppendChild()) {
    xslt.Transform(input, (XsltArgumentList)null, writer);
}
```

### <a name="discretionary-behavior"></a><span data-ttu-id="492f8-142">임의 동작</span><span class="sxs-lookup"><span data-stu-id="492f8-142">Discretionary Behavior</span></span>

<span data-ttu-id="492f8-143">W3C XSLT(XSL Transformations) 버전 1.0 권장 사항에는 구현 공급자가 특정 상황을 처리하는 방법을 결정할 수 있는 영역이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-143">The W3C XSL Transformations (XSLT) Version 1.0 Recommendation includes areas in which the implementation provider may decide how to handle a situation.</span></span> <span data-ttu-id="492f8-144">이러한 영역은 임의 동작으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-144">These areas are considered to be discretionary behavior.</span></span> <span data-ttu-id="492f8-145"><xref:System.Xml.Xsl.XslCompiledTransform>이 <xref:System.Xml.Xsl.XslTransform> 클래스와 다르게 동작하는 여러 상황이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-145">There are several areas where the <xref:System.Xml.Xsl.XslCompiledTransform> behaves differently than the <xref:System.Xml.Xsl.XslTransform> class.</span></span> <span data-ttu-id="492f8-146">자세한 내용은 [복구 가능한 XSLT 오류](recoverable-xslt-errors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="492f8-146">For more information, see [Recoverable XSLT Errors](recoverable-xslt-errors.md).</span></span>

### <a name="extension-objects-and-script-functions"></a><span data-ttu-id="492f8-147">확장 개체 및 스크립트 함수</span><span class="sxs-lookup"><span data-stu-id="492f8-147">Extension Objects and Script Functions</span></span>

<span data-ttu-id="492f8-148"><xref:System.Xml.Xsl.XslCompiledTransform>에는 스크립트 함수 사용에 대한 새로운 두 가지 제한 사항이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-148"><xref:System.Xml.Xsl.XslCompiledTransform> introduces two new restrictions on the use of script functions:</span></span>

- <span data-ttu-id="492f8-149">공용 메서드만 XPath 식에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-149">Only public methods may be called from XPath expressions.</span></span>

- <span data-ttu-id="492f8-150">오버로드는 인수 수에 따라 서로 다르게 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-150">Overloads are distinguishable from each other based on the number of arguments.</span></span> <span data-ttu-id="492f8-151">둘 이상의 오버로드에 동일한 수의 인수가 있는 경우 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-151">If more than one overload has the same number of arguments, an exception will be raised.</span></span>

<span data-ttu-id="492f8-152"><xref:System.Xml.Xsl.XslCompiledTransform>에서 함수를 스크립팅하는 바인딩(메서드 이름 lookup)은 컴파일 시간에 발생하므로 XslTransform에서 작동하는 스타일시트가 <xref:System.Xml.Xsl.XslCompiledTransform>에서 로드될 때 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-152">In <xref:System.Xml.Xsl.XslCompiledTransform>, a binding (method name lookup) to script functions occurs at compile time, and style sheets that worked with XslTransform may cause an exception when they are loaded with <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

<span data-ttu-id="492f8-153"><xref:System.Xml.Xsl.XslCompiledTransform>에서는 `msxsl:using` 요소 내에 `msxsl:assembly` 및 `msxsl:script` 자식 요소를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-153"><xref:System.Xml.Xsl.XslCompiledTransform> supports having `msxsl:using` and `msxsl:assembly` child elements within the `msxsl:script` element.</span></span> <span data-ttu-id="492f8-154">`msxsl:using` 및 `msxsl:assembly` 요소를 사용하여 스크립트 블록에서 사용할 추가 네임스페이스 및 어셈블리를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-154">The `msxsl:using` and `msxsl:assembly` elements are used to declare additional namespaces and assemblies for use in the script block.</span></span> <span data-ttu-id="492f8-155">자세한 내용은 [msxsl:script를 사용하는 스크립트 블록](script-blocks-using-msxsl-script.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="492f8-155">See [Script Blocks Using msxsl:script](script-blocks-using-msxsl-script.md) for more information.</span></span>

<span data-ttu-id="492f8-156"><xref:System.Xml.Xsl.XslCompiledTransform>에서는 확장 개체가 동일한 수의 인수를 가지는 여러 개의 오버로드를 포함하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-156"><xref:System.Xml.Xsl.XslCompiledTransform> prohibits extension objects that have multiple overloads with the same number of arguments.</span></span>

### <a name="msxml-functions"></a><span data-ttu-id="492f8-157">MSXML 함수</span><span class="sxs-lookup"><span data-stu-id="492f8-157">MSXML Functions</span></span>

<span data-ttu-id="492f8-158"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스에 추가된 추가 MSXML 함수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-158">Support for additional MSXML functions have been added to the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="492f8-159">다음 목록에서는 새 기능 또는 향상된 기능을 설명합니다</span><span class="sxs-lookup"><span data-stu-id="492f8-159">The following list describes new or improved functionality:</span></span>

- <span data-ttu-id="492f8-160">msxsl:node-set: <xref:System.Xml.Xsl.XslTransform>에서 [node-set 함수](/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100))의 인수는 결과 트리 조각이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-160">msxsl:node-set: <xref:System.Xml.Xsl.XslTransform> required the argument of the [node-set Function](/previous-versions/dotnet/netframework-4.0/ms256197(v=vs.100)) function to be a result tree fragment.</span></span> <span data-ttu-id="492f8-161"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스에는 이러한 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-161">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not have this requirement.</span></span>

- <span data-ttu-id="492f8-162">msxsl:version: 이 함수는 <xref:System.Xml.Xsl.XslCompiledTransform>에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-162">msxsl:version: This function is supported in <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>

- <span data-ttu-id="492f8-163">XPath 확장 함수: [ms:string-compare 함수](/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc 함수](/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri 함수](/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name 함수](/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number 함수](/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date 함수](/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)) 및 [ms:format-time 함수](/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100))가 이제 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-163">XPath extension functions: The [ms:string-compare Function](/previous-versions/dotnet/netframework-4.0/ms256114(v=vs.100)), [ms:utc Function](/previous-versions/dotnet/netframework-4.0/ms256474(v=vs.100)), [ms:namespace-uri Function](/previous-versions/dotnet/netframework-4.0/ms256231(v=vs.100)), [ms:local-name Function](/previous-versions/dotnet/netframework-4.0/ms256055(v=vs.100)), [ms:number Function](/previous-versions/dotnet/netframework-4.0/ms256155(v=vs.100)), [ms:format-date Function](/previous-versions/dotnet/netframework-4.0/ms256099(v=vs.100)), and [ms:format-time Function](/previous-versions/dotnet/netframework-4.0/ms256467(v=vs.100)) functions are now supported.</span></span>

- <span data-ttu-id="492f8-164">스키마 관련 XPath 확장 함수: 이러한 함수는 기본적으로 <xref:System.Xml.Xsl.XslCompiledTransform>에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-164">Schema-related XPath extension functions: These functions are not supported natively by <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span> <span data-ttu-id="492f8-165">그러나 이러한 함수를 확장명 함수로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492f8-165">However, they can be implemented as extension functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="492f8-166">참조</span><span class="sxs-lookup"><span data-stu-id="492f8-166">See also</span></span>

- [<span data-ttu-id="492f8-167">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="492f8-167">XSLT Transformations</span></span>](xslt-transformations.md)
- [<span data-ttu-id="492f8-168">XslCompiledTransform 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="492f8-168">Using the XslCompiledTransform Class</span></span>](using-the-xslcompiledtransform-class.md)
