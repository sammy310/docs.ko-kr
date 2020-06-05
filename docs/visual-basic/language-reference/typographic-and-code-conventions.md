---
title: 글꼴 표시 및 코드 규칙
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: 0e36d9d61b0dd2701210ce614d15fd38f08f5401
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401357"
---
# <a name="typographic-and-code-conventions-visual-basic"></a><span data-ttu-id="65c34-102">글꼴 표시 및 코드 규칙(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65c34-102">Typographic and Code Conventions (Visual Basic)</span></span>

<span data-ttu-id="65c34-103">Visual Basic 설명서에서는 다음의 입력 및 코드 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-103">Visual Basic documentation uses the following typographic and code conventions.</span></span>  
  
## <a name="typographic-conventions"></a><span data-ttu-id="65c34-104">인쇄 규칙</span><span class="sxs-lookup"><span data-stu-id="65c34-104">Typographic Conventions</span></span>  
  
|<span data-ttu-id="65c34-105">예제</span><span class="sxs-lookup"><span data-stu-id="65c34-105">Example</span></span>|<span data-ttu-id="65c34-106">Description</span><span class="sxs-lookup"><span data-stu-id="65c34-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65c34-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span><span class="sxs-lookup"><span data-stu-id="65c34-107">`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`</span></span>|<span data-ttu-id="65c34-108">언어별 키워드 및 런타임 멤버는 초기 대문자를 가지 며이 예제에 나와 있는 것 처럼 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-108">Language-specific keywords and runtime members have initial uppercase letters and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="65c34-109">**SmallProject**, **buttoncollection**</span><span class="sxs-lookup"><span data-stu-id="65c34-109">**SmallProject**, **ButtonCollection**</span></span>|<span data-ttu-id="65c34-110">입력 하 라는 단어와 문구는이 예제에 표시 된 대로 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-110">Words and phrases you are instructed to type are formatted as shown in this example.</span></span>|  
|[<span data-ttu-id="65c34-111">Module 문</span><span class="sxs-lookup"><span data-stu-id="65c34-111">Module Statement</span></span>](statements/module-statement.md)|<span data-ttu-id="65c34-112">클릭 하 여 다른 도움말 페이지로 이동할 수 있는 링크는이 예제에 표시 된 것 처럼 서식 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-112">Links you can click to go to another Help page are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="65c34-113">*개체*, *variableName*,`argumentList`</span><span class="sxs-lookup"><span data-stu-id="65c34-113">*object*, *variableName*, `argumentList`</span></span>|<span data-ttu-id="65c34-114">사용자가 제공 하는 정보에 대 한 자리 표시자는이 예제에 표시 된 대로 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-114">Placeholders for information that you supply are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="65c34-115">[Shadows], [ *Expressionlist* ]</span><span class="sxs-lookup"><span data-stu-id="65c34-115">[ Shadows ], [ *expressionList* ]</span></span>|<span data-ttu-id="65c34-116">구문에서 선택적 항목은 대괄호로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-116">In syntax, optional items are enclosed in brackets.</span></span>|  
|<span data-ttu-id="65c34-117">{ `Public` &#124; `Friend` &#124; `Private` }</span><span class="sxs-lookup"><span data-stu-id="65c34-117">{ `Public` &#124; `Friend` &#124; `Private` }</span></span>|<span data-ttu-id="65c34-118">구문에서 둘 이상의 항목을 선택 해야 하는 경우 항목은 중괄호로 묶이고 세로 막대로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-118">In syntax, when you must make a choice between two or more items, the items are enclosed in braces and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="65c34-119">항목을 하나만 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-119">You must select one, and only one, of the items.</span></span>|  
|<span data-ttu-id="65c34-120">[ `Protected` &#124; `Friend` ]</span><span class="sxs-lookup"><span data-stu-id="65c34-120">[ `Protected` &#124; `Friend` ]</span></span>|<span data-ttu-id="65c34-121">구문에서 두 개 이상의 항목 중에서 선택할 수 있는 옵션이 있으면 항목은 대괄호로 묶여 있으며 세로 막대로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-121">In syntax, when you have the option of selecting between two or more items, the items are enclosed in square brackets and separated by vertical bars.</span></span><br /><br /> <span data-ttu-id="65c34-122">항목의 조합을 선택 하거나 항목을 선택 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-122">You can select any combination of the items, or no item.</span></span>|  
|<span data-ttu-id="65c34-123">[{ `ByVal` &#124; `ByRef` }]</span><span class="sxs-lookup"><span data-stu-id="65c34-123">[{ `ByVal` &#124; `ByRef` }]</span></span>|<span data-ttu-id="65c34-124">구문에서 둘 이상의 항목을 선택할 수 있지만 항목을 완전히 생략할 수 있는 경우 항목은 중괄호로 묶고 세로 막대로 구분 된 대괄호로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-124">In syntax, when you can select no more than one item, but you can also omit the items completely, the items are enclosed in square brackets surrounded by braces and separated by vertical bars.</span></span>|  
|<span data-ttu-id="65c34-125">*memberName*1, *MemberName*2, *memberName*3</span><span class="sxs-lookup"><span data-stu-id="65c34-125">*memberName*1, *memberName*2, *memberName*3</span></span>|<span data-ttu-id="65c34-126">예제에 표시 된 것 처럼 동일한 자리 표시자의 여러 인스턴스는 아래 첨자로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-126">Multiple instances of the same placeholder are differentiated by subscripts, as shown in the example.</span></span>|  
|<span data-ttu-id="65c34-127">*memberName1*</span><span class="sxs-lookup"><span data-stu-id="65c34-127">*memberName1*</span></span><br /><br /> <span data-ttu-id="65c34-128">...</span><span class="sxs-lookup"><span data-stu-id="65c34-128">...</span></span><br /><br /> <span data-ttu-id="65c34-129">*memberNameN*</span><span class="sxs-lookup"><span data-stu-id="65c34-129">*memberNameN*</span></span>|<span data-ttu-id="65c34-130">구문에서 줄임표 (...)를 사용 하 여 줄임표 바로 앞에 있는 종류의 항목을 무한 하 게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-130">In syntax, an ellipsis (...) is used to indicate an indefinite number of items of the kind immediately in front of the ellipsis.</span></span><br /><br /> <span data-ttu-id="65c34-131">코드에서 줄임표는 명확 하 게 하기 위해 코드를 생략 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-131">In code, ellipses signify code omitted for the sake of clarity.</span></span>|  
|<span data-ttu-id="65c34-132">ESC, ENTER</span><span class="sxs-lookup"><span data-stu-id="65c34-132">ESC, ENTER</span></span>|<span data-ttu-id="65c34-133">키보드의 키 이름과 키 시퀀스는 모두 대문자로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-133">Key names and key sequences on the keyboard appear in all uppercase letters.</span></span>|  
|<span data-ttu-id="65c34-134">Alt+F1</span><span class="sxs-lookup"><span data-stu-id="65c34-134">ALT+F1</span></span>|<span data-ttu-id="65c34-135">키 이름 사이에 더하기 기호 (+)가 표시 되 면 한 키를 누른 채 다른 키를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-135">When plus signs (+) appear between key names, you must hold down one key while pressing the other.</span></span> <span data-ttu-id="65c34-136">예를 들어, ALT + f 1은 ALT 키를 누른 채 F1 키를 누르는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-136">For example, ALT+F1 means hold down the ALT key while pressing the F1 key.</span></span>|  
  
## <a name="code-conventions"></a><span data-ttu-id="65c34-137">코드 규칙</span><span class="sxs-lookup"><span data-stu-id="65c34-137">Code Conventions</span></span>  
  
|<span data-ttu-id="65c34-138">예제</span><span class="sxs-lookup"><span data-stu-id="65c34-138">Example</span></span>|<span data-ttu-id="65c34-139">Description</span><span class="sxs-lookup"><span data-stu-id="65c34-139">Description</span></span>|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|<span data-ttu-id="65c34-140">코드 샘플은 고정 피치 글꼴로 표시 되 고 다음 예제와 같이 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-140">Code samples appear in a fixed-pitch font and are formatted as shown in this example.</span></span>|  
|<span data-ttu-id="65c34-141">이전 문은의 값을 `sampleString` "Hello, 세계!"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-141">The previous statement sets the value of `sampleString` to "Hello, world!"</span></span>|<span data-ttu-id="65c34-142">설명 텍스트의 코드 요소는 다음 예제와 같이 고정 피치 글꼴로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-142">Code elements in explanatory text appear in a fixed-pitch font, as shown in this example.</span></span>|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|<span data-ttu-id="65c34-143">코드 주석은 아포스트로피 (') 또는 REM 키워드에 의해 도입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-143">Code comments are introduced by an apostrophe (') or the REM keyword.</span></span>|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|<span data-ttu-id="65c34-144">줄 끝에서 밑줄 (_)이 뒤에 오는 공백은 다음 줄에서 문이 계속 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65c34-144">A space followed by an underscore ( _) at the end of a line indicates that the statement continues on the following line.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65c34-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65c34-145">See also</span></span>

- [<span data-ttu-id="65c34-146">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="65c34-146">Visual Basic Language Reference</span></span>](index.md)
- [<span data-ttu-id="65c34-147">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="65c34-147">Keywords</span></span>](keywords/index.md)
- [<span data-ttu-id="65c34-148">Visual Basic 런타임 라이브러리 멤버</span><span class="sxs-lookup"><span data-stu-id="65c34-148">Visual Basic Runtime Library Members</span></span>](runtime-library-members.md)
- [<span data-ttu-id="65c34-149">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="65c34-149">Visual Basic Naming Conventions</span></span>](../programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="65c34-150">방법: 코드에서 명령문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="65c34-150">How to: Break and Combine Statements in Code</span></span>](../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="65c34-151">코드 주석</span><span class="sxs-lookup"><span data-stu-id="65c34-151">Comments in Code</span></span>](../programming-guide/program-structure/comments-in-code.md)
