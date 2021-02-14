---
description: '자세히 알아보기: XML을 사용 하 여 코드 문서화 (Visual Basic)'
title: XML로 코드 문서화
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: b554007bdd5183d0d92dc7ff62d08885f4b7f486
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476009"
---
# <a name="document-your-code-with-xml-visual-basic"></a><span data-ttu-id="0c0ee-103">코드를 XML로 문서화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c0ee-103">Document your code with XML (Visual Basic)</span></span>

<span data-ttu-id="0c0ee-104">Visual Basic에서 XML을 사용 하 여 코드를 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-104">In Visual Basic, you can document your code using XML.</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="0c0ee-105">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="0c0ee-105">XML documentation comments</span></span>

<span data-ttu-id="0c0ee-106">Visual Basic는 프로젝트에 대 한 XML 문서를 자동으로 만드는 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-106">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="0c0ee-107">형식 및 멤버에 대해 XML 기본 구조를 자동으로 생성 한 다음 요약, 각 매개 변수에 대 한 설명 설명서 및 기타 설명을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-107">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="0c0ee-108">적절 한 설정을 사용 하 여 XML 문서를 프로젝트와 동일한 루트 파일 이름으로 XML 파일에 자동으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-108">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same root file name as your project.</span></span> <span data-ttu-id="0c0ee-109">자세한 내용은 [-doc](../../reference/command-line-compiler/doc.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-109">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="0c0ee-110">XML 파일을 사용 하거나 XML로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-110">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="0c0ee-111">이 파일은 프로젝트의 출력 .exe 또는 .dll 파일과 같은 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-111">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="0c0ee-112">XML 문서는 `'''`로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-112">XML documentation starts with `'''`.</span></span> <span data-ttu-id="0c0ee-113">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-113">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="0c0ee-114">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-114">The documentation must be well-formed XML.</span></span> <span data-ttu-id="0c0ee-115">XML의 형식이 잘못 된 경우 경고가 생성 되 고 설명서 파일에 오류가 발생 했다는 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-115">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="0c0ee-116">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-116">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="0c0ee-117">권장 태그 집합이 있습니다 ( [XML 주석 태그](../../language-reference/xmldoc/index.md)참조).</span><span class="sxs-lookup"><span data-stu-id="0c0ee-117">There is a recommended set of tags (see [XML Comment Tags](../../language-reference/xmldoc/index.md)).</span></span> <span data-ttu-id="0c0ee-118">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-118">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="0c0ee-119">\<param> 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-119">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="0c0ee-120">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-120">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="0c0ee-121">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-121">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="0c0ee-122">`cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-122">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="0c0ee-123">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-123">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="0c0ee-124">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-124">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="0c0ee-125">또한 컴파일러는 `Imports` 특성에 설명 된 형식을 찾을 때 문을 고려 합니다 `cref` .</span><span class="sxs-lookup"><span data-stu-id="0c0ee-125">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="0c0ee-126">\<summary>태그는 Visual Studio의 IntelliSense에서 형식 또는 멤버에 대 한 추가 정보를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-126">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="0c0ee-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0c0ee-127">Related sections</span></span>

<span data-ttu-id="0c0ee-128">문서 주석을 사용 하 여 XML 파일을 만드는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c0ee-128">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="0c0ee-129">-doc</span><span class="sxs-lookup"><span data-stu-id="0c0ee-129">-doc</span></span>](../../reference/command-line-compiler/doc.md)

- [<span data-ttu-id="0c0ee-130">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="0c0ee-130">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)

- [<span data-ttu-id="0c0ee-131">XML 파일 처리</span><span class="sxs-lookup"><span data-stu-id="0c0ee-131">Processing the XML File</span></span>](processing-the-xml-file.md)

- [<span data-ttu-id="0c0ee-132">방법: XML 설명서 만들기</span><span class="sxs-lookup"><span data-stu-id="0c0ee-132">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)

- [<span data-ttu-id="0c0ee-133">Visual Studio의 XML 도구</span><span class="sxs-lookup"><span data-stu-id="0c0ee-133">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="0c0ee-134">참조</span><span class="sxs-lookup"><span data-stu-id="0c0ee-134">See also</span></span>

- [<span data-ttu-id="0c0ee-135">Visual Basic을 사용한 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="0c0ee-135">Developing Applications with Visual Basic</span></span>](../../developing-apps/index.md)
- [<span data-ttu-id="0c0ee-136">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0c0ee-136">Visual Basic Programming Guide</span></span>](../index.md)
