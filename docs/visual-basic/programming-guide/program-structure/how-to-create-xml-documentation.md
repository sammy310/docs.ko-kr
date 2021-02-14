---
description: '자세한 정보: 방법: Visual Basic에서 XML 문서 만들기'
title: '방법: XML 설명서 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: d54c79d820a170b246e5c85d7562487fbe66f39c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475957"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="5343c-103">방법: Visual Basic에서 XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="5343c-103">How to: Create XML Documentation in Visual Basic</span></span>

<span data-ttu-id="5343c-104">이 예제에서는 코드에 XML 문서 주석을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-104">This example shows how to add XML documentation comments to your code.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="5343c-105">형식 또는 멤버에 대 한 XML 문서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5343c-105">To create XML documentation for a type or member</span></span>

1. <span data-ttu-id="5343c-106">**코드 편집기** 에서 문서를 만들 형식 또는 멤버 위의 줄에 커서를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-106">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>

2. <span data-ttu-id="5343c-107">`'''`(세 개의 작은 따옴표)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-107">Type `'''` (three single-quotation marks).</span></span>

    <span data-ttu-id="5343c-108">형식 또는 멤버에 대 한 XML 뼈대가 **코드 편집기** 에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-108">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>

3. <span data-ttu-id="5343c-109">적절 한 태그 사이에 설명 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-109">Add descriptive information between the appropriate tags.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5343c-110">XML 문서 블록 내에 줄을 추가 하는 경우 각 줄은로 시작 해야 합니다 `'''` .</span><span class="sxs-lookup"><span data-stu-id="5343c-110">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>

4. <span data-ttu-id="5343c-111">형식 또는 멤버를 사용 하는 코드를 새 XML 문서 주석과 함께 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-111">Add additional code that uses the type or member with the new XML documentation comments.</span></span>

    <span data-ttu-id="5343c-112">IntelliSense는 \<summary> 형식 또는 멤버에 대 한 태그의 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-112">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>

5. <span data-ttu-id="5343c-113">코드를 컴파일하여 문서 주석을 포함 하는 XML 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5343c-113">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="5343c-114">자세한 내용은 [-doc](../../reference/command-line-compiler/doc.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5343c-114">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5343c-115">참조</span><span class="sxs-lookup"><span data-stu-id="5343c-115">See also</span></span>

- [<span data-ttu-id="5343c-116">코드를 XML로 문서화</span><span class="sxs-lookup"><span data-stu-id="5343c-116">Documenting Your Code with XML</span></span>](documenting-your-code-with-xml.md)
- [<span data-ttu-id="5343c-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="5343c-117">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)
- [<span data-ttu-id="5343c-118">-doc</span><span class="sxs-lookup"><span data-stu-id="5343c-118">-doc</span></span>](../../reference/command-line-compiler/doc.md)
