---
title: XML 파일 처리(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: a10255be140c7c86a435cca98cec5df7df82ffee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955495"
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="abdd5-102">XML 파일 처리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abdd5-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="abdd5-103">컴파일러는 문서 생성을 위해 태그가 지정되는 코드의 각 구문에 대해 ID 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="abdd5-104">(코드에 태그를 하는 방법에 대 한 자세한 내용은 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md).) ID 문자열은 구문을 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="abdd5-105">XML 파일을 처리 하는 프로그램은 해당 하는 데 ID 문자열을 사용할 수 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 메타 데이터/리플렉션 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="abdd5-106">XML 파일에 코드의 계층적 표현이 아닙니다. 각 요소에 대해 생성 된 ID 사용 하 여 플랫 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="abdd5-107">컴파일러는 ID 문자열을 생성할 때 다음 규칙을 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
- <span data-ttu-id="abdd5-108">문자열에 공백이 배치되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-108">No white space is placed in the string.</span></span>  
  
- <span data-ttu-id="abdd5-109">ID 문자열의 첫 부분이 뒤에 콜론이 붙은 한 글자로 식별 대상 멤버를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="abdd5-110">멤버 유형은 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="abdd5-111">문자</span><span class="sxs-lookup"><span data-stu-id="abdd5-111">Character</span></span>|<span data-ttu-id="abdd5-112">설명</span><span class="sxs-lookup"><span data-stu-id="abdd5-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="abdd5-113">N</span><span class="sxs-lookup"><span data-stu-id="abdd5-113">N</span></span>|<span data-ttu-id="abdd5-114">namespace</span><span class="sxs-lookup"><span data-stu-id="abdd5-114">namespace</span></span><br /><br /> <span data-ttu-id="abdd5-115">네임 스페이스에 문서 주석을 추가할 수는 없지만,에 대 한 CREF 참조를 만들 수 있습니다 지원 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="abdd5-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="abdd5-116">T</span><span class="sxs-lookup"><span data-stu-id="abdd5-116">T</span></span>|<span data-ttu-id="abdd5-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span><span class="sxs-lookup"><span data-stu-id="abdd5-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="abdd5-118">F</span><span class="sxs-lookup"><span data-stu-id="abdd5-118">F</span></span>|<span data-ttu-id="abdd5-119">field: `Dim`</span><span class="sxs-lookup"><span data-stu-id="abdd5-119">field: `Dim`</span></span>|  
|<span data-ttu-id="abdd5-120">P</span><span class="sxs-lookup"><span data-stu-id="abdd5-120">P</span></span>|<span data-ttu-id="abdd5-121">속성: `Property` (기본 속성 포함)</span><span class="sxs-lookup"><span data-stu-id="abdd5-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="abdd5-122">M</span><span class="sxs-lookup"><span data-stu-id="abdd5-122">M</span></span>|<span data-ttu-id="abdd5-123">method: `Sub`, `Function`, `Declare`, `Operator`</span><span class="sxs-lookup"><span data-stu-id="abdd5-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="abdd5-124">E</span><span class="sxs-lookup"><span data-stu-id="abdd5-124">E</span></span>|<span data-ttu-id="abdd5-125">event: `Event`</span><span class="sxs-lookup"><span data-stu-id="abdd5-125">event: `Event`</span></span>|  
|<span data-ttu-id="abdd5-126">!</span><span class="sxs-lookup"><span data-stu-id="abdd5-126">!</span></span>|<span data-ttu-id="abdd5-127">오류 문자열</span><span class="sxs-lookup"><span data-stu-id="abdd5-127">error string</span></span><br /><br /> <span data-ttu-id="abdd5-128">문자열의 나머지 부분은 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="abdd5-129">Visual Basic 컴파일러는 확인할 수 없는 링크에 대 한 오류 정보를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span></span>|  
  
- <span data-ttu-id="abdd5-130">두 번째 부분을 `String` 네임 스페이스의 루트에서 시작 하는 항목의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="abdd5-131">이름 항목, 해당 바깥쪽 형식 및 네임 스페이스는 마침표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="abdd5-132">마침표를 포함 하는 항목 자체의 이름, 숫자 기호에서 대체 됩니다 (#).</span><span class="sxs-lookup"><span data-stu-id="abdd5-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="abdd5-133">항목이 직접 해당 이름에에서 숫자 기호 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="abdd5-134">정규화 된 이름에 예를 들어 합니다 `String` 생성자 것 `System.String.#ctor`입니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
- <span data-ttu-id="abdd5-135">속성 및 메서드의 경우 메서드에 대한 인수가 있으면 괄호로 묶인 인수 목록이 문자열 뒤에 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="abdd5-136">인수가 없으면 괄호도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="abdd5-137">인수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-137">The arguments are separated by commas.</span></span> <span data-ttu-id="abdd5-138">각 인수의 인코딩은 그대로 따릅니다에서 인코딩하는 방법을 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abdd5-139">예제</span><span class="sxs-lookup"><span data-stu-id="abdd5-139">Example</span></span>  
 <span data-ttu-id="abdd5-140">다음 코드는 클래스에 대 한 ID 문자열 하는 방법을 보여 줍니다. 하 고 해당 멤버 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdd5-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="abdd5-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="abdd5-141">See also</span></span>

- [<span data-ttu-id="abdd5-142">/doc</span><span class="sxs-lookup"><span data-stu-id="abdd5-142">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="abdd5-143">방법: XML 문서 만들기</span><span class="sxs-lookup"><span data-stu-id="abdd5-143">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
