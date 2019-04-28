---
title: 코드를 XML로 문서화(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 6b9fe9994b7bdf2259dcdb1ecef906e0f9955c8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785504"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="8760d-102">코드를 XML로 문서화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8760d-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="8760d-103">Visual basic에서 XML을 사용 하 여 코드를 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="8760d-104">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="8760d-104">XML Documentation Comments</span></span>

<span data-ttu-id="8760d-105">Visual Basic 프로젝트에 대 한 XML 문서를 자동으로 만들려면 쉬운을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="8760d-106">형식 및 멤버는 XML 구조를 자동으로 생성 하 고 각 매개 변수 및 기타 설명에 대 한 요약, 설명이 포함 된 설명서를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="8760d-107">적절 한 설정을 사용 하면 XML 문서는.xml 확장명 프로젝트와 동일한 이름 가진 XML 파일에 자동으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="8760d-108">자세한 내용은 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8760d-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="8760d-109">XML 파일을 사용 또는 XML로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="8760d-110">이 파일은 프로젝트의 출력.exe 또는.dll 파일과 동일한 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="8760d-111">XML 문서 시작 `'''`합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="8760d-112">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="8760d-113">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="8760d-114">XML이 제대로 구성 되지 경우 경고가 생성 되 고 문서 파일에 오류가 발생 했습니다 표시 하는 주석이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="8760d-115">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="8760d-116">권장된 태그 (이 항목의 "관련 섹션" 참조) 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="8760d-117">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="8760d-118">\<param> 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="8760d-119">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="8760d-120">확인에 실패 하는 경우 컴파일러는 경고를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="8760d-121">`cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="8760d-122">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="8760d-123">확인에 실패 하는 경우 컴파일러는 경고를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="8760d-124">하나는 컴파일러도 존중 `Imports` 에 설명 된 형식의 찾을 때 문은 `cref` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="8760d-125">\<요약 > 태그를 사용 하 여 Visual Studio의 IntelliSense 형식 또는 멤버에 대 한 추가 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8760d-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8760d-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8760d-126">Related Sections</span></span>

<span data-ttu-id="8760d-127">문서 주석이 포함 된 XML 파일을 만드는 방법에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8760d-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="8760d-128">/doc</span><span class="sxs-lookup"><span data-stu-id="8760d-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="8760d-129">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="8760d-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="8760d-130">XML 파일 처리</span><span class="sxs-lookup"><span data-stu-id="8760d-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="8760d-131">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="8760d-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="8760d-132">Visual Studio의 XML 도구</span><span class="sxs-lookup"><span data-stu-id="8760d-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="8760d-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="8760d-133">See also</span></span>

- [<span data-ttu-id="8760d-134">Visual Basic을 사용한 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="8760d-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="8760d-135">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8760d-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
