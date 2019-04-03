---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 13005eb55b430f6ff9b3a6408582a02e53838742
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824587"
---
# <a name="-doc"></a><span data-ttu-id="ff767-102">-doc</span><span class="sxs-lookup"><span data-stu-id="ff767-102">-doc</span></span>
<span data-ttu-id="ff767-103">XML 파일에 대해 문서 주석을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff767-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff767-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff767-105">인수</span><span class="sxs-lookup"><span data-stu-id="ff767-105">Arguments</span></span>  
  
|<span data-ttu-id="ff767-106">용어</span><span class="sxs-lookup"><span data-stu-id="ff767-106">Term</span></span>|<span data-ttu-id="ff767-107">정의</span><span class="sxs-lookup"><span data-stu-id="ff767-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="ff767-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ff767-108">`+` &#124; `-`</span></span>|<span data-ttu-id="ff767-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-109">Optional.</span></span> <span data-ttu-id="ff767-110">+ 또는 `-doc`만 지정하면 컴파일러가 문서 정보를 생성하여 XML 파일에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="ff767-111">`-`를 지정하면 `-doc`를 지정하지 않는 것과 같으며, 문서 정보를 생성하지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="ff767-112">`-doc:`를 사용하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="ff767-113">출력 XML 파일을 지정하며, 이 파일은 컴파일의 소스 코드 파일에 있는 주석으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="ff767-114">파일 이름에 공백이 있으면 이름을 따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff767-115">설명</span><span class="sxs-lookup"><span data-stu-id="ff767-115">Remarks</span></span>  
 <span data-ttu-id="ff767-116">`-doc` 옵션은 컴파일러가 문서 주석을 포함하는 XML 파일을 생성하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="ff767-117">`-doc:file` 구문을 사용하는 경우 `file` 매개 변수에서 XML 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="ff767-118">`-doc` 또는 `-doc+`를 사용하는 경우 컴파일러는 컴파일러가 생성하는 실행 파일 또는 라이브러리에서 XML 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="ff767-119">`-doc-`를 사용하거나 `-doc` 옵션을 지정하지 않는 경우 컴파일러는 XML 파일을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="ff767-120">소스 코드 파일에서 문서 주석은 다음 정의보다 앞에 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="ff767-121">[class](../../../visual-basic/language-reference/statements/class-statement.md) 또는 [interface](../../../visual-basic/language-reference/statements/interface-statement.md) 같은 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="ff767-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="ff767-122">field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md) 또는 [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md) 같은 멤버</span><span class="sxs-lookup"><span data-stu-id="ff767-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="ff767-123">Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) 기능에서 생성된 XML 파일을 사용하려면 XML 파일의 파일 이름을 지원하려는 어셈블리와 동일하게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-123">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="ff767-124">어셈블리가 Visual Studio 프로젝트에서 참조되면 .xml 파일도 검색되도록 XML 파일이 어셈블리와 동일한 디렉터리에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="ff767-125">IntelliSense에서 프로젝트 내의 코드나 프로젝트에서 참조하는 프로젝트 내의 코드를 작업하는 데는 XML 문서 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="ff767-126">`/target:module`로 컴파일하는 경우 외에는 XML 파일에 `<assembly></assembly>` 태그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="ff767-127">이러한 태그는 컴파일 출력 파일의 어셈블리 매니페스트를 포함하는 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="ff767-128">코드의 주석에서 문서를 생성하는 방법은 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)(XML 주석 태그)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff767-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="ff767-129">Visual Studio 통합 개발 환경에서 -doc를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="ff767-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ff767-130">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ff767-131">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ff767-132">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ff767-133">3.  **XML 문서 파일 생성** 상자에 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff767-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff767-134">예제</span><span class="sxs-lookup"><span data-stu-id="ff767-134">Example</span></span>  
 <span data-ttu-id="ff767-135">샘플은 [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)(XML과 함께 코드 문서화)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff767-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff767-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff767-136">See also</span></span>

- [<span data-ttu-id="ff767-137">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="ff767-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ff767-138">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="ff767-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
