---
title: 코드를 XML로 문서화
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347450"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="be952-102">코드를 XML로 문서화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be952-102">Documenting Your Code with XML (Visual Basic)</span></span>

<span data-ttu-id="be952-103">Visual Basic에서 XML을 사용 하 여 코드를 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-103">In Visual Basic, you can document your code using XML</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="be952-104">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="be952-104">XML Documentation Comments</span></span>

<span data-ttu-id="be952-105">Visual Basic는 프로젝트에 대 한 XML 문서를 자동으로 만드는 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be952-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="be952-106">형식 및 멤버에 대해 XML 기본 구조를 자동으로 생성 한 다음 요약, 각 매개 변수에 대 한 설명 설명서 및 기타 설명을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="be952-107">적절 한 설정을 사용 하 여 XML 문서는 프로젝트와 이름이 같은 XML 파일 및 .xml 확장명으로 자동으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="be952-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="be952-108">자세한 내용은 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be952-108">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="be952-109">XML 파일을 사용 하거나 XML로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="be952-110">이 파일은 프로젝트의 출력 .exe 또는 .dll 파일과 같은 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="be952-111">XML 설명서는 `'''`로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="be952-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="be952-112">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="be952-113">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be952-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="be952-114">XML의 형식이 잘못 된 경우 경고가 생성 되 고 설명서 파일에 오류가 발생 했다는 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="be952-115">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="be952-116">권장 태그 집합이 있습니다 (이 항목의 "관련 섹션" 참조).</span><span class="sxs-lookup"><span data-stu-id="be952-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="be952-117">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="be952-118">\<param> 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be952-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="be952-119">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be952-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="be952-120">확인이 실패 하면 컴파일러에서 경고를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="be952-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="be952-121">`cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be952-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="be952-122">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be952-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="be952-123">확인이 실패 하면 컴파일러에서 경고를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="be952-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="be952-124">또한 컴파일러는 `cref` 특성에 설명 된 형식을 찾을 때 `Imports` 문을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="be952-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="be952-125">\<summary > 태그는 Visual Studio의 IntelliSense에서 형식 또는 멤버에 대 한 추가 정보를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be952-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="be952-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="be952-126">Related Sections</span></span>

<span data-ttu-id="be952-127">문서 주석을 사용 하 여 XML 파일을 만드는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be952-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="be952-128">-doc</span><span class="sxs-lookup"><span data-stu-id="be952-128">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)

- [<span data-ttu-id="be952-129">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="be952-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

- [<span data-ttu-id="be952-130">XML 파일 처리</span><span class="sxs-lookup"><span data-stu-id="be952-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [<span data-ttu-id="be952-131">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="be952-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [<span data-ttu-id="be952-132">Visual Studio의 XML 도구</span><span class="sxs-lookup"><span data-stu-id="be952-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="be952-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="be952-133">See also</span></span>

- [<span data-ttu-id="be952-134">Visual Basic을 사용한 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="be952-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
- [<span data-ttu-id="be952-135">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="be952-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
