---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 8b80629ce9b2cd62f10d9a53279b83ba41bc4ece
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097711"
---
# <a name="-doc"></a><span data-ttu-id="8a848-102">-doc</span><span class="sxs-lookup"><span data-stu-id="8a848-102">-doc</span></span>

<span data-ttu-id="8a848-103">XML 파일에 대해 문서 주석을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a848-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a848-104">Syntax</span></span>  
  
```console  
-doc[+ | -]  
```

<span data-ttu-id="8a848-105">또는</span><span class="sxs-lookup"><span data-stu-id="8a848-105">or</span></span>  

```console
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a848-106">인수</span><span class="sxs-lookup"><span data-stu-id="8a848-106">Arguments</span></span>  
  
|<span data-ttu-id="8a848-107">용어</span><span class="sxs-lookup"><span data-stu-id="8a848-107">Term</span></span>|<span data-ttu-id="8a848-108">정의</span><span class="sxs-lookup"><span data-stu-id="8a848-108">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="8a848-109">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8a848-109">`+` &#124; `-`</span></span>|<span data-ttu-id="8a848-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-110">Optional.</span></span> <span data-ttu-id="8a848-111">\+ 또는 `-doc`만 지정하면 컴파일러가 문서 정보를 생성하여 XML 파일에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-111">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="8a848-112">`-`를 지정하면 `-doc`를 지정하지 않는 것과 같으며, 문서 정보를 생성하지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-112">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="8a848-113">`-doc:`를 사용하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-113">Required if `-doc:` is used.</span></span> <span data-ttu-id="8a848-114">출력 XML 파일을 지정하며, 이 파일은 컴파일의 소스 코드 파일에 있는 주석으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-114">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="8a848-115">파일 이름에 공백이 있으면 이름을 따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-115">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a848-116">설명</span><span class="sxs-lookup"><span data-stu-id="8a848-116">Remarks</span></span>  

 <span data-ttu-id="8a848-117">`-doc` 옵션은 컴파일러가 문서 주석을 포함하는 XML 파일을 생성하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-117">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="8a848-118">`-doc:file` 구문을 사용하는 경우 `file` 매개 변수에서 XML 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-118">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="8a848-119">`-doc` 또는 `-doc+`를 사용하는 경우 컴파일러는 컴파일러가 생성하는 실행 파일 또는 라이브러리에서 XML 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-119">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="8a848-120">`-doc-`를 사용하거나 `-doc` 옵션을 지정하지 않는 경우 컴파일러는 XML 파일을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-120">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="8a848-121">소스 코드 파일에서 문서 주석은 다음 정의보다 앞에 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-121">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
- <span data-ttu-id="8a848-122">[class](../../language-reference/statements/class-statement.md) 또는 [interface](../../language-reference/statements/interface-statement.md) 같은 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="8a848-122">User-defined types, such as a [class](../../language-reference/statements/class-statement.md) or [interface](../../language-reference/statements/interface-statement.md)</span></span>  
  
- <span data-ttu-id="8a848-123">field, [event](../../language-reference/statements/event-statement.md), [property](../../language-reference/statements/property-statement.md), [function](../../language-reference/statements/function-statement.md) 또는 [subroutine](../../language-reference/statements/sub-statement.md) 같은 멤버</span><span class="sxs-lookup"><span data-stu-id="8a848-123">Members, such as a field, [event](../../language-reference/statements/event-statement.md), [property](../../language-reference/statements/property-statement.md), [function](../../language-reference/statements/function-statement.md), or [subroutine](../../language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="8a848-124">Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) 기능에서 생성된 XML 파일을 사용하려면 XML 파일의 파일 이름을 지원하려는 어셈블리와 동일하게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-124">To use the generated XML file with the Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="8a848-125">어셈블리가 Visual Studio 프로젝트에서 참조되면 .xml 파일도 검색되도록 XML 파일이 어셈블리와 동일한 디렉터리에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-125">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="8a848-126">IntelliSense에서 프로젝트 내의 코드나 프로젝트에서 참조하는 프로젝트 내의 코드를 작업하는 데는 XML 문서 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-126">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="8a848-127">`-target:module`로 컴파일하는 경우 외에는 XML 파일에 `<assembly></assembly>` 태그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-127">Unless you compile with `-target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="8a848-128">이러한 태그는 컴파일 출력 파일의 어셈블리 매니페스트를 포함하는 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-128">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="8a848-129">코드의 주석에서 문서를 생성하는 방법은 [XML Comment Tags](../../language-reference/xmldoc/index.md)(XML 주석 태그)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a848-129">See [XML Comment Tags](../../language-reference/xmldoc/index.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="8a848-130">Visual Studio 통합 개발 환경에서 -doc를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="8a848-130">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8a848-131">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8a848-132">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-132">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="8a848-133">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="8a848-134">3.  **XML 문서 파일 생성** 상자에 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a848-134">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a848-135">예제</span><span class="sxs-lookup"><span data-stu-id="8a848-135">Example</span></span>  

 <span data-ttu-id="8a848-136">샘플은 [Documenting Your Code with XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md)(XML과 함께 코드 문서화)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a848-136">See [Documenting Your Code with XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a848-137">참조</span><span class="sxs-lookup"><span data-stu-id="8a848-137">See also</span></span>

- [<span data-ttu-id="8a848-138">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="8a848-138">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="8a848-139">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="8a848-139">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
