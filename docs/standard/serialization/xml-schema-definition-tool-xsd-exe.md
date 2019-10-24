---
title: XML Schema Definition Tool (Xsd.exe)
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: 9de4a195f34b0daedcfb3687dbb36495b985092d
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775256"
---
# <a name="xml-schema-definition-tool-xsdexe"></a><span data-ttu-id="a0466-102">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="a0466-102">XML Schema Definition Tool (Xsd.exe)</span></span>

<span data-ttu-id="a0466-103">XML 스키마 정의 도구(Xsd.exe)를 사용하면 XDR, XML 및 XSD 파일 또는 런타임 어셈블리의 클래스에서 XML 스키마 또는 공용 언어 런타임 클래스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-103">The XML Schema Definition (Xsd.exe) tool generates XML schema or common language runtime classes from XDR, XML, and XSD files, or from classes in a runtime assembly.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0466-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0466-104">Syntax</span></span>

```console
xsd file.xdr [-outputdir:directory][/parameters:file.xml]
xsd file.xml [-outputdir:directory] [/parameters:file.xml]
xsd file.xsd {/classes | /dataset} [/element:element]
             [/enableLinqDataSet] [/language:language]
                          [/namespace:namespace] [-outputdir:directory] [URI:uri]
                          [/parameters:file.xml]
xsd {file.dll | file.exe} [-outputdir:directory] [/type:typename [...]][/parameters:file.xml]
```

## <a name="argument"></a><span data-ttu-id="a0466-105">인수</span><span class="sxs-lookup"><span data-stu-id="a0466-105">Argument</span></span>

|<span data-ttu-id="a0466-106">인수</span><span class="sxs-lookup"><span data-stu-id="a0466-106">Argument</span></span>|<span data-ttu-id="a0466-107">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-107">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="a0466-108">*file.extension*</span><span class="sxs-lookup"><span data-stu-id="a0466-108">*file.extension*</span></span>|<span data-ttu-id="a0466-109">변환할 입력 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-109">Specifies the input file to convert.</span></span> <span data-ttu-id="a0466-110">다음 중 하나에 해당 하는 확장명을 xdr, .xml, .xsd, .dll 또는 .exe 중 하나로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-110">You must specify the extension as one of the following: .xdr, .xml, .xsd, .dll, or .exe.</span></span><br /><br /> <span data-ttu-id="a0466-111">XDR 스키마 파일(.xdr 확장명)을 지정하면 Xsd.exe는 XDR 스키마를 XSD 스키마로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-111">If you specify an XDR schema file (.xdr extension), Xsd.exe converts the XDR schema to an XSD schema.</span></span> <span data-ttu-id="a0466-112">출력 파일의 이름은 XDR 스키마와 동일하지만 확장명은 .xsd입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-112">The output file has the same name as the XDR schema, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="a0466-113">XML 파일(.xml 확장명)을 지정하면 Xsd.exe는 해당 파일에 있는 데이터에서 스키마를 유추하여 XSD 스키마가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-113">If you specify an XML file (.xml extension), Xsd.exe infers a schema from the data in the file and produces an XSD schema.</span></span> <span data-ttu-id="a0466-114">출력 파일의 이름은 XML 파일과 동일하지만 확장명은 .xsd입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-114">The output file has the same name as the XML file, but with the .xsd extension.</span></span><br /><br /> <span data-ttu-id="a0466-115">XML 스키마 파일(.xsd 확장명)을 지정하면 해당 XML 스키마에 해당하는 런타임 개체에 대한 소스 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-115">If you specify an XML schema file (.xsd extension), Xsd.exe generates source code for runtime objects that correspond to the XML schema.</span></span><br /><br /> <span data-ttu-id="a0466-116">런타임 어셈블리 파일(.exe 또는 .dll 확장명)을 지정하면 해당 어셈블리에 있는 하나 이상의 형식에 대해 스키마가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-116">If you specify a runtime assembly file (.exe or .dll extension), Xsd.exe generates schemas for one or more types in that assembly.</span></span> <span data-ttu-id="a0466-117">`/type` 옵션을 사용하면 스키마를 생성할 대상 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-117">You can use the `/type` option to specify the types for which to generate schemas.</span></span> <span data-ttu-id="a0466-118">출력 스키마의 이름은 schema0.xsd, schema1.xsd 등과 같이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-118">The output schemas are named schema0.xsd, schema1.xsd, and so on.</span></span> <span data-ttu-id="a0466-119">지정된 형식에서 `XMLRoot` 사용자 지정 특성을 사용하여 네임스페이스를 지정하는 경우에만 여러 개의 스키마가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-119">Xsd.exe produces multiple schemas only if the given types specify a namespace using the `XMLRoot` custom attribute.</span></span>|

## <a name="general-options"></a><span data-ttu-id="a0466-120">일반 옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-120">General Options</span></span>

|<span data-ttu-id="a0466-121">옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-121">Option</span></span>|<span data-ttu-id="a0466-122">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-122">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="a0466-123">**/h \[elp \]**</span><span class="sxs-lookup"><span data-stu-id="a0466-123">**/h\[elp\]**</span></span>|<span data-ttu-id="a0466-124">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-124">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="a0466-125">**/o \[utputdir \]:** _디렉터리_</span><span class="sxs-lookup"><span data-stu-id="a0466-125">**/o\[utputdir\]:**_directory_</span></span>|<span data-ttu-id="a0466-126">출력 파일의 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-126">Specifies the directory for output files.</span></span> <span data-ttu-id="a0466-127">이 인수는 한 번만 나타날 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="a0466-127">This argument can appear only once.</span></span> <span data-ttu-id="a0466-128">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-128">The default is the current directory.</span></span>|
|<span data-ttu-id="a0466-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="a0466-129">**/?**</span></span>|<span data-ttu-id="a0466-130">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-130">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="a0466-131">**/p \[arameters \]:** _파일 .xml_</span><span class="sxs-lookup"><span data-stu-id="a0466-131">**/p\[arameters\]:**_file.xml_</span></span>|<span data-ttu-id="a0466-132">지정한 .xml 파일의 여러 가지 작동 모드에 대한 읽기 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-132">Read options for various operation modes from the specified .xml file.</span></span> <span data-ttu-id="a0466-133">약식 표현은 `/p:`입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-133">The short form is `/p:`.</span></span> <span data-ttu-id="a0466-134">자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0466-134">For more information, see the [Remarks](#remarks) section.</span></span>|

## <a name="xsd-file-options"></a><span data-ttu-id="a0466-135">XSD 파일 옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-135">XSD File Options</span></span>
 <span data-ttu-id="a0466-136">.xsd 파일에는 다음 옵션 중 하나만 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-136">You must specify only one of the following options for .xsd files.</span></span>

|<span data-ttu-id="a0466-137">옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-137">Option</span></span>|<span data-ttu-id="a0466-138">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-138">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="a0466-139">**/c \[lasses \]**</span><span class="sxs-lookup"><span data-stu-id="a0466-139">**/c\[lasses\]**</span></span>|<span data-ttu-id="a0466-140">지정된 스키마에 해당하는 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-140">Generates classes that correspond to the specified schema.</span></span> <span data-ttu-id="a0466-141">XML 데이터를 개체로 읽어오려면 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-141">To read XML data into the object, use the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>|
|<span data-ttu-id="a0466-142">**/d \[ataset \]**</span><span class="sxs-lookup"><span data-stu-id="a0466-142">**/d\[ataset\]**</span></span>|<span data-ttu-id="a0466-143">지정된 스키마에 해당하는 <xref:System.Data.DataSet>에서 파생된 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-143">Generates a class derived from <xref:System.Data.DataSet> that corresponds to the specified schema.</span></span> <span data-ttu-id="a0466-144">XML 데이터를 파생 클래스로 읽어오려면 <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-144">To read XML data into the derived class, use the <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType> method.</span></span>|

 <span data-ttu-id="a0466-145">.xsd 파일에는 다음 옵션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-145">You can also specify any of the following options for .xsd files.</span></span>

|<span data-ttu-id="a0466-146">옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-146">Option</span></span>|<span data-ttu-id="a0466-147">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-147">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="a0466-148">**/e \[lement \]:** _요소_</span><span class="sxs-lookup"><span data-stu-id="a0466-148">**/e\[lement\]:**_element_</span></span>|<span data-ttu-id="a0466-149">코드를 생성할 대상 스키마 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-149">Specifies the element in the schema to generate code for.</span></span> <span data-ttu-id="a0466-150">기본적으로 모든 요소가 입력되며,</span><span class="sxs-lookup"><span data-stu-id="a0466-150">By default all elements are typed.</span></span> <span data-ttu-id="a0466-151">이 인수는 한 번 이상 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-151">You can specify this argument more than once.</span></span>|
|<span data-ttu-id="a0466-152">**/enableDataBinding**</span><span class="sxs-lookup"><span data-stu-id="a0466-152">**/enableDataBinding**</span></span>|<span data-ttu-id="a0466-153">생성된 모든 형식에 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하여 데이터 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-153">Implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all generated types to enable data binding.</span></span> <span data-ttu-id="a0466-154">약식 표현은 `/edb`입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-154">The short form is `/edb`.</span></span>|
|<span data-ttu-id="a0466-155">**/enableLinqDataSet**</span><span class="sxs-lookup"><span data-stu-id="a0466-155">**/enableLinqDataSet**</span></span>|<span data-ttu-id="a0466-156">(약식: `/eld`) LINQ to DataSet를 사용 하 여 생성 된 데이터 집합을 쿼리할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-156">(Short form: `/eld`.) Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="a0466-157">이 옵션은 /dataset 옵션이 지정된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-157">This option is used when the /dataset option is also specified.</span></span> <span data-ttu-id="a0466-158">자세한 내용은 [LINQ to DataSet 개요](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) 및 [형식화된 데이터 세트 쿼리](../../../docs/framework/data/adonet/querying-typed-datasets.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0466-158">For more information, see [LINQ to DataSet Overview](../../../docs/framework/data/adonet/linq-to-dataset-overview.md) and [Querying Typed DataSets](../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="a0466-159">Linq 사용에 대 한 일반적인 내용은 linq [( C# 통합 언어 쿼리](../../csharp/programming-guide/concepts/linq/index.md) ) 또는 [linq (통합 언어 쿼리)-Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0466-159">For general information about using LINQ, see [Language-Integrated Query (LINQ) - C#](../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>|
|<span data-ttu-id="a0466-160">**/f \[ields \]**</span><span class="sxs-lookup"><span data-stu-id="a0466-160">**/f\[ields\]**</span></span>|<span data-ttu-id="a0466-161">속성 대신 필드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-161">Generates fields instead of properties.</span></span> <span data-ttu-id="a0466-162">기본적으로 속성이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-162">By default, properties are generated.</span></span>|
|<span data-ttu-id="a0466-163">**/l \[anguage \]:** _language_</span><span class="sxs-lookup"><span data-stu-id="a0466-163">**/l\[anguage\]:**_language_</span></span>|<span data-ttu-id="a0466-164">사용할 프로그래밍 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-164">Specifies the programming language to use.</span></span> <span data-ttu-id="a0466-165">`CS`(C#, 기본값), `VB`(Visual Basic), `JS`(JScript) 또는 `VJS`(Visual J#) 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-165">Choose from `CS` (C#, which is the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="a0466-166"><xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>를 구현하는 클래스의 정규화된 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-166">You can also specify a fully qualified name for a class implementing <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType></span></span>|
|<span data-ttu-id="a0466-167">**/n \[amespace \]:** _네임 스페이스_</span><span class="sxs-lookup"><span data-stu-id="a0466-167">**/n\[amespace\]:**_namespace_</span></span>|<span data-ttu-id="a0466-168">생성된 형식에 대한 런타임 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-168">Specifies the runtime namespace for the generated types.</span></span> <span data-ttu-id="a0466-169">기본 네임스페이스는 `Schemas`입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-169">The default namespace is `Schemas`.</span></span>|
|<span data-ttu-id="a0466-170">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="a0466-170">**/nologo**</span></span>|<span data-ttu-id="a0466-171">배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-171">Suppresses the banner.</span></span>|
|<span data-ttu-id="a0466-172">**/order**</span><span class="sxs-lookup"><span data-stu-id="a0466-172">**/order**</span></span>|<span data-ttu-id="a0466-173">모든 파티클 멤버에 대해 명시적인 순서 식별자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-173">Generates explicit order identifiers on all particle members.</span></span>|
|<span data-ttu-id="a0466-174">**/o \[ut \]:** _directoryName_</span><span class="sxs-lookup"><span data-stu-id="a0466-174">**/o\[ut\]:**_directoryName_</span></span>|<span data-ttu-id="a0466-175">파일을 배치할 출력 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-175">Specifies the output directory to place the files in.</span></span> <span data-ttu-id="a0466-176">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-176">The default is the current directory.</span></span>|
|<span data-ttu-id="a0466-177">**/u \[ri \]:** _uri_</span><span class="sxs-lookup"><span data-stu-id="a0466-177">**/u\[ri\]:**_uri_</span></span>|<span data-ttu-id="a0466-178">코드를 생성할 대상 스키마 요소의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-178">Specifies the URI for the elements in the schema to generate code for.</span></span> <span data-ttu-id="a0466-179">이 URI가 존재하는 경우 `/element` 옵션을 사용하여 지정된 모든 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-179">This URI, if present, applies to all elements specified with the `/element` option.</span></span>|

## <a name="dll-and-exe-file-options"></a><span data-ttu-id="a0466-180">DLL 및 EXE 파일 옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-180">DLL and EXE File Options</span></span>

|<span data-ttu-id="a0466-181">옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-181">Option</span></span>|<span data-ttu-id="a0466-182">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-182">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="a0466-183">**/t \[ype \]:** _typename_</span><span class="sxs-lookup"><span data-stu-id="a0466-183">**/t\[ype\]:**_typename_</span></span>|<span data-ttu-id="a0466-184">스키마를 생성할 대상 형식의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-184">Specifies the name of the type to create a schema for.</span></span> <span data-ttu-id="a0466-185">여러 개의 형식 인수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-185">You can specify multiple type arguments.</span></span> <span data-ttu-id="a0466-186">*typename*에서 네임스페이스를 지정하지 않으면 Xsd.exe는 해당 어셈블리의 모든 형식과 지정된 형식을 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-186">If *typename* does not specify a namespace, Xsd.exe matches all types in the assembly with the specified type.</span></span> <span data-ttu-id="a0466-187">*typename*에서 네임스페이스를 지정하면 지정한 형식만 일치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-187">If *typename* specifies a namespace, only that type is matched.</span></span> <span data-ttu-id="a0466-188">*typename*이 별표(\*)로 끝나는 경우에는 \* 앞의 문자열로 시작하는 모든 형식이 일치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-188">If *typename* ends with an asterisk character (\*), the tool matches all types that start with the string preceding the \*.</span></span> <span data-ttu-id="a0466-189">`/type` 옵션을 생략하면 Xsd.exe는 해당 어셈블리의 모든 형식에 대해 스키마가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-189">If you omit the `/type` option, Xsd.exe generates schemas for all types in the assembly.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a0466-190">주의</span><span class="sxs-lookup"><span data-stu-id="a0466-190">Remarks</span></span>

<span data-ttu-id="a0466-191">다음 표에서는 Xsd.exe에서 수행되는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-191">The following table shows the operations that Xsd.exe performs.</span></span>

| | |
|------------|-----------------|
|<span data-ttu-id="a0466-192">XDR에서 XSD로</span><span class="sxs-lookup"><span data-stu-id="a0466-192">XDR to XSD</span></span>|<span data-ttu-id="a0466-193">XDR 스키마 파일에서 XML 스키마를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-193">Generates an XML schema from an XML-Data-Reduced schema file.</span></span> <span data-ttu-id="a0466-194">XDR은 XML 기반 스키마의 초기 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-194">XDR is an early XML-based schema format.</span></span>|
|<span data-ttu-id="a0466-195">XML에서 XSD로</span><span class="sxs-lookup"><span data-stu-id="a0466-195">XML to XSD</span></span>|<span data-ttu-id="a0466-196">XML 파일에서 XML 스키마를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-196">Generates an XML schema from an XML file.</span></span>|
|<span data-ttu-id="a0466-197">XSD에서 DataSet으로</span><span class="sxs-lookup"><span data-stu-id="a0466-197">XSD to DataSet</span></span>|<span data-ttu-id="a0466-198">XSD 스키마 파일에서 공용 언어 런타임 <xref:System.Data.DataSet> 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-198">Generates common language runtime <xref:System.Data.DataSet> classes from an XSD schema file.</span></span> <span data-ttu-id="a0466-199">이렇게 생성된 클래스에서는 일반 XML 데이터에 대한 강력한 개체 모델이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-199">The generated classes provide a rich object model for regular XML data.</span></span>|
|<span data-ttu-id="a0466-200">XSD에서 클래스로</span><span class="sxs-lookup"><span data-stu-id="a0466-200">XSD to Classes</span></span>|<span data-ttu-id="a0466-201">XSD 스키마 파일에서 런타임 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-201">Generates runtime classes from an XSD schema file.</span></span> <span data-ttu-id="a0466-202">이렇게 생성된 클래스를 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>와 함께 사용하면 해당 스키마를 따르는 XML 코드를 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-202">The generated classes can be used in conjunction with <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> to read and write XML code that follows the schema.</span></span>|
|<span data-ttu-id="a0466-203">클래스를 XSD로</span><span class="sxs-lookup"><span data-stu-id="a0466-203">Classes to XSD</span></span>| <span data-ttu-id="a0466-204">런타임 어셈블리 파일의 형식에서 XML 스키마를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-204">Generates an XML schema from a type or types in a runtime assembly file.</span></span> <span data-ttu-id="a0466-205">생성 된 스키마는 <xref:System.Xml.Serialization.XmlSerializer>에서 사용 하는 XML 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-205">The generated schema defines the XML format used by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|

 <span data-ttu-id="a0466-206">Xsd.exe를 사용하면 W3C(World Wide Web 컨소시엄)에서 제시하는 XSD(XML Schema Definition) 언어를 따르는 XML 스키마만 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-206">Xsd.exe only allows you to manipulate XML schemas that follow the XML Schema Definition (XSD) language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="a0466-207">XML 스키마 정의 제안 또는 XML 표준에 대 한 자세한 내용은 <https://w3.org>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0466-207">For more information on the XML Schema Definition proposal or the XML standard, see <https://w3.org>.</span></span>

## <a name="setting-options-with-an-xml-file"></a><span data-ttu-id="a0466-208">XML 파일로 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="a0466-208">Setting Options with an XML File</span></span>

<span data-ttu-id="a0466-209">`/parameters` 스위치를 사용하여 여러 가지 옵션을 설정하는 단일 XML 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-209">By using the `/parameters` switch, you can specify a single XML file that sets various options.</span></span> <span data-ttu-id="a0466-210">설정할 수 있는 옵션은 XSD.exe 도구를 사용하는 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-210">The options you can set depend on how you are using the XSD.exe tool.</span></span> <span data-ttu-id="a0466-211">스키마 생성, 코드 파일 생성 또는 `DataSet` 기능이 있는 코드 파일 생성을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-211">Choices include generating schemas, generating code files, or generating code files that include `DataSet` features.</span></span> <span data-ttu-id="a0466-212">예를 들면, 스키마는 생성하지만 코드 파일은 생성하지 않을 때 `<assembly>` 요소를 실행 파일(.exe) 또는 형식 라이브러리 파일(.dll) 이름으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-212">For example, you can set the `<assembly>` element to the name of an executable (.exe) or type library (.dll) file when generating a schema, but not when generating a code file.</span></span> <span data-ttu-id="a0466-213">다음 XML에서는 지정된 실행 파일에 `<generateSchemas>` 요소를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-213">The following XML shows how to use the `<generateSchemas>` element with a specified executable:</span></span>

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

<span data-ttu-id="a0466-214">위의 XML이 GenerateSchemas.xml이라는 파일에 포함된 경우 명령 프롬프트에서 다음을 입력하고 Enter 키를 눌러 `/parameters` 스위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-214">If the preceding XML is contained in a file named GenerateSchemas.xml, then use the `/parameters` switch by typing the following at a command prompt and pressing ENTER:</span></span>

```console
 xsd /p:GenerateSchemas.xml
```

<span data-ttu-id="a0466-215">그러나 어셈블리에 있는 단일 형식의 스키마를 생성하는 경우 다음 XML을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-215">On the other hand, if you are generating a schema for a single type found in the assembly, you can use the following XML:</span></span>

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

<span data-ttu-id="a0466-216">위의 코드를 사용하려면 명령 프롬프트에서 어셈블리의 이름도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-216">But to use preceding code, you must also supply the name of the assembly at the command prompt.</span></span> <span data-ttu-id="a0466-217">명령 프롬프트에서 다음을 입력합니다. 이 경우 XML 파일 이름이 GenerateSchemaFromType.xml이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-217">Type the following at a command prompt (presuming the XML file is named GenerateSchemaFromType.xml):</span></span>

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

<span data-ttu-id="a0466-218">`<generateSchemas>` 요소에 대해 다음 옵션 중 하나만 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-218">You must specify only one of the following options for the `<generateSchemas>` element.</span></span>

|<span data-ttu-id="a0466-219">요소</span><span class="sxs-lookup"><span data-stu-id="a0466-219">Element</span></span>|<span data-ttu-id="a0466-220">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-220">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="a0466-221">\<assembly></span><span class="sxs-lookup"><span data-stu-id="a0466-221">\<assembly></span></span>|<span data-ttu-id="a0466-222">스키마를 생성하는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-222">Specifies an assembly to generate the schema from.</span></span>|
|<span data-ttu-id="a0466-223">\<type></span><span class="sxs-lookup"><span data-stu-id="a0466-223">\<type></span></span>|<span data-ttu-id="a0466-224">스키마를 생성할 대상 어셈블리에 있는 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-224">Specifies a type found in an assembly to generate a schema for.</span></span>|
|<span data-ttu-id="a0466-225">\<xml></span><span class="sxs-lookup"><span data-stu-id="a0466-225">\<xml></span></span>|<span data-ttu-id="a0466-226">스키마를 생성할 대상 XML 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-226">Specifies an XML file to generate a schema for.</span></span>|
|<span data-ttu-id="a0466-227">\<xdr></span><span class="sxs-lookup"><span data-stu-id="a0466-227">\<xdr></span></span>|<span data-ttu-id="a0466-228">스키마를 생성할 대상 XDR 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-228">Specifies an XDR file to generate a schema for.</span></span>|

<span data-ttu-id="a0466-229">코드 파일을 생성하려면 `<generateClasses>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-229">To generate a code file, use the `<generateClasses>` element.</span></span> <span data-ttu-id="a0466-230">다음 예제는 코드 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-230">The following example generates a code file.</span></span> <span data-ttu-id="a0466-231">또한 생성된 파일의 프로그래밍 언어 및 네임스페이스를 설정할 수 있는 두 개의 특성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-231">Note that two attributes are also shown that allow you to set the programming language and namespace of the generated file.</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 <span data-ttu-id="a0466-232">`<generateClasses>` 요소에 대해 설정할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-232">Options you can set for the `<generateClasses>` element include the following.</span></span>

|<span data-ttu-id="a0466-233">요소</span><span class="sxs-lookup"><span data-stu-id="a0466-233">Element</span></span>|<span data-ttu-id="a0466-234">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-234">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="a0466-235">\<element></span><span class="sxs-lookup"><span data-stu-id="a0466-235">\<element></span></span>|<span data-ttu-id="a0466-236">코드를 생성할 대상 .xsd 파일의 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-236">Specifies an element in the .xsd file to generate code for.</span></span>|
|<span data-ttu-id="a0466-237">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="a0466-237">\<schemaImporterExtensions></span></span>|<span data-ttu-id="a0466-238"><xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> 클래스에서 파생된 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-238">Specifies a type derived from the <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> class.</span></span>|
|<span data-ttu-id="a0466-239">\<schema></span><span class="sxs-lookup"><span data-stu-id="a0466-239">\<schema></span></span>|<span data-ttu-id="a0466-240">코드를 생성할 XML 스키마 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-240">Specifies a XML Schema file to generate code for.</span></span> <span data-ttu-id="a0466-241">여러 \<schema> 요소를 사용하여 XML 스키마 파일을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-241">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

<span data-ttu-id="a0466-242">다음 표에서는 `<generateClasses>` 요소에도 사용할 수 있는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-242">The following table shows the attributes that can also be used with the `<generateClasses>` element.</span></span>

|<span data-ttu-id="a0466-243">특성</span><span class="sxs-lookup"><span data-stu-id="a0466-243">Attribute</span></span>|<span data-ttu-id="a0466-244">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-244">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a0466-245">language</span><span class="sxs-lookup"><span data-stu-id="a0466-245">language</span></span>|<span data-ttu-id="a0466-246">사용할 프로그래밍 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-246">Specifies the programming language to use.</span></span> <span data-ttu-id="a0466-247">`CS`(C#, 기본값), `VB`(Visual Basic), `JS`(JScript) 또는 `VJS`(Visual J#) 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-247">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="a0466-248"><xref:System.CodeDom.Compiler.CodeDomProvider>를 구현하는 클래스의 정규화된 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-248">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="a0466-249">네임스페이스(namespace)</span><span class="sxs-lookup"><span data-stu-id="a0466-249">namespace</span></span>|<span data-ttu-id="a0466-250">생성된 코드에 대한 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-250">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="a0466-251">네임스페이스는 CLR 표준(예: 공백 없음 또는 백슬래시 문자)에 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-251">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|
|<span data-ttu-id="a0466-252">옵션</span><span class="sxs-lookup"><span data-stu-id="a0466-252">options</span></span>|<span data-ttu-id="a0466-253">`none`, `properties`(public 필드 대신 속성 생성), `order` 또는 `enableDataBinding`(위의 XSD 파일 옵션 섹션의 `/order` 및 `/enableDataBinding` 스위치 참조) 값 중 하나</span><span class="sxs-lookup"><span data-stu-id="a0466-253">One of the following values: `none`, `properties` (generates properties instead of public fields), `order`, or `enableDataBinding` (see the `/order` and `/enableDataBinding` switches in the preceding XSD File Options section.</span></span>|

 <span data-ttu-id="a0466-254">`DataSet` 요소를 사용하여 `<generateDataSet>` 코드를 생성하는 방식을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-254">You can also control how `DataSet` code is generated by using the `<generateDataSet>` element.</span></span> <span data-ttu-id="a0466-255">다음 XML은 생성 된 코드가 `DataSet` 구조체 (예: <xref:System.Data.DataTable> 클래스)를 사용 하 여 지정 된 요소에 대 한 Visual Basic 코드를 만들도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-255">The following XML specifies that the generated code uses `DataSet` structures (such as the <xref:System.Data.DataTable> class) to create Visual Basic code for a specified element.</span></span> <span data-ttu-id="a0466-256">생성된 DataSet 구조체는 LINQ 쿼리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-256">The generated DataSet structures will support LINQ queries.</span></span>

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

<span data-ttu-id="a0466-257">`<generateDataSet>` 요소에 대해 설정할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-257">Options you can set for the `<generateDataSet>` element include the following.</span></span>

|<span data-ttu-id="a0466-258">요소</span><span class="sxs-lookup"><span data-stu-id="a0466-258">Element</span></span>|<span data-ttu-id="a0466-259">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-259">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="a0466-260">\<schema></span><span class="sxs-lookup"><span data-stu-id="a0466-260">\<schema></span></span>|<span data-ttu-id="a0466-261">코드를 생성할 XML 스키마 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-261">Specifies an XML Schema file to generate code for.</span></span> <span data-ttu-id="a0466-262">여러 \<schema> 요소를 사용하여 XML 스키마 파일을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-262">Multiple XML Schema files can be specified using multiple \<schema> elements.</span></span>|

 <span data-ttu-id="a0466-263">다음 표에서는 `<generateDataSet>` 요소에 사용할 수 있는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-263">The following table shows the attributes that can be used with the `<generateDataSet>` element.</span></span>

|<span data-ttu-id="a0466-264">특성</span><span class="sxs-lookup"><span data-stu-id="a0466-264">Attribute</span></span>|<span data-ttu-id="a0466-265">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-265">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a0466-266">enableLinqDataSet</span><span class="sxs-lookup"><span data-stu-id="a0466-266">enableLinqDataSet</span></span>|<span data-ttu-id="a0466-267">생성된 DataSet을 LINQ to DataSet을 사용하여 쿼리할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-267">Specifies that the generated DataSet can be queried against using LINQ to DataSet.</span></span> <span data-ttu-id="a0466-268">기본값은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-268">The default value is false.</span></span>|
|<span data-ttu-id="a0466-269">language</span><span class="sxs-lookup"><span data-stu-id="a0466-269">language</span></span>|<span data-ttu-id="a0466-270">사용할 프로그래밍 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-270">Specifies the programming language to use.</span></span> <span data-ttu-id="a0466-271">`CS`(C#, 기본값), `VB`(Visual Basic), `JS`(JScript) 또는 `VJS`(Visual J#) 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-271">Choose from `CS` (C#, the default), `VB` (Visual Basic), `JS` (JScript), or `VJS` (Visual J#).</span></span> <span data-ttu-id="a0466-272"><xref:System.CodeDom.Compiler.CodeDomProvider>를 구현하는 클래스의 정규화된 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-272">You can also specify a fully qualified name for a class that implements <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>|
|<span data-ttu-id="a0466-273">네임스페이스(namespace)</span><span class="sxs-lookup"><span data-stu-id="a0466-273">namespace</span></span>|<span data-ttu-id="a0466-274">생성된 코드에 대한 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-274">Specifies the namespace for the generated code.</span></span> <span data-ttu-id="a0466-275">네임스페이스는 CLR 표준(예: 공백 없음 또는 백슬래시 문자)에 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-275">The namespace must conform to CLR standards (for example, no spaces or backslash characters).</span></span>|

 <span data-ttu-id="a0466-276">이러한 특성은 최상위 수준의 `<xsd>` 요소에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-276">There are attributes that you can set on the top level `<xsd>` element.</span></span> <span data-ttu-id="a0466-277">이러한 옵션은 자식 요소(`<generateSchemas>`, `<generateClasses>` 또는 `<generateDataSet>`)에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-277">These options can be used with any of the child elements (`<generateSchemas>`, `<generateClasses>` or `<generateDataSet>`).</span></span> <span data-ttu-id="a0466-278">다음 XML 코드는 "MyOutputDirectory"라는 출력 디렉터리에 "IDItems" 요소에 대한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-278">The following XML code generates code for an element named "IDItems" in the output directory named "MyOutputDirectory".</span></span>

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

<span data-ttu-id="a0466-279">다음 표에서는 `<xsd>` 요소에도 사용할 수 있는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-279">The following table shows the attributes that can also be used with the `<xsd>` element.</span></span>

|<span data-ttu-id="a0466-280">특성</span><span class="sxs-lookup"><span data-stu-id="a0466-280">Attribute</span></span>|<span data-ttu-id="a0466-281">설명</span><span class="sxs-lookup"><span data-stu-id="a0466-281">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a0466-282">출력</span><span class="sxs-lookup"><span data-stu-id="a0466-282">output</span></span>|<span data-ttu-id="a0466-283">생성된 스키마 또는 코드 파일을 지정할 디렉터리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-283">The name of a directory where the generated schema or code file will be placed.</span></span>|
|<span data-ttu-id="a0466-284">nologo</span><span class="sxs-lookup"><span data-stu-id="a0466-284">nologo</span></span>|<span data-ttu-id="a0466-285">배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-285">Suppresses the banner.</span></span> <span data-ttu-id="a0466-286">`true` 또는 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-286">Set to `true` or `false`.</span></span>|
|<span data-ttu-id="a0466-287">도움말</span><span class="sxs-lookup"><span data-stu-id="a0466-287">help</span></span>|<span data-ttu-id="a0466-288">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-288">Displays command syntax and options for the tool.</span></span> <span data-ttu-id="a0466-289">`true` 또는 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-289">Set to `true` or `false`.</span></span>|

## <a name="examples"></a><span data-ttu-id="a0466-290">예제</span><span class="sxs-lookup"><span data-stu-id="a0466-290">Examples</span></span>
 <span data-ttu-id="a0466-291">다음 명령을 사용하여 `myFile.xdr` 에서 XML 스키마를 생성한 다음 현재 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-291">The following command generates an XML schema from `myFile.xdr` and saves it to the current directory.</span></span>

```console
xsd myFile.xdr
```

<span data-ttu-id="a0466-292">다음 명령을 사용하여 `myFile.xml` 스키마를 생성한 다음 지정된 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-292">The following command generates an XML schema from `myFile.xml` and saves it to the specified directory.</span></span>

```console
xsd myFile.xml /outputdir:myOutputDir
```

<span data-ttu-id="a0466-293">다음 명령은 C# 언어로 된 지정된 스키마와 일치하는 데이터 집합을 생성한 다음 현재 디렉터리에 `XSDSchemaFile.cs`로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-293">The following command generates a data set that corresponds to the specified schema in the C# language and saves it as `XSDSchemaFile.cs` in the current directory.</span></span>

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

<span data-ttu-id="a0466-294">다음 명령을 사용하여 어셈블리 `myAssembly.dll`에 있는 모든 형식에 대해 XML 스키마를 생성한 다음 현재 디렉터리에 `schema0.xsd`로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a0466-294">The following command generates XML schemas for all types in the assembly `myAssembly.dll` and saves them as `schema0.xsd` in the current directory.</span></span>

```console
xsd myAssembly.dll
```

## <a name="see-also"></a><span data-ttu-id="a0466-295">참조</span><span class="sxs-lookup"><span data-stu-id="a0466-295">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [<span data-ttu-id="a0466-296">도구</span><span class="sxs-lookup"><span data-stu-id="a0466-296">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="a0466-297">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="a0466-297">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
- [<span data-ttu-id="a0466-298">LINQ to DataSet 개요</span><span class="sxs-lookup"><span data-stu-id="a0466-298">LINQ to DataSet Overview</span></span>](../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="a0466-299">형식화된 데이터 세트 쿼리</span><span class="sxs-lookup"><span data-stu-id="a0466-299">Querying Typed DataSets</span></span>](../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [<span data-ttu-id="a0466-300">LINQ (통합 언어 쿼리) (C#)</span><span class="sxs-lookup"><span data-stu-id="a0466-300">LINQ (Language-Integrated Query) (C#)</span></span>](../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="a0466-301">LINQ (통합 언어 쿼리) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0466-301">LINQ (Language-Integrated Query) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)
