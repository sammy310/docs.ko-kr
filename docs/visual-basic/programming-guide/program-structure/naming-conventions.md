---
title: 명명 규칙
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 98fdda2934c9df1b33f41b6e0442a39246efe168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347313"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="737df-102">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="737df-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="737df-103">Visual Basic 응용 프로그램에서 요소의 이름을 지정할 때 해당 이름의 첫 문자는 영문자 또는 밑줄 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="737df-104">그러나 밑줄로 시작 하는 이름은 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="737df-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="737df-105">다음 제안 사항이 이름 지정에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="737df-105">The following suggestions apply to naming.</span></span>  
  
- <span data-ttu-id="737df-106">`FindLastRecord` 및 `RedrawMyForm`와 같이 이름에 있는 각 단어를 대문자로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
- <span data-ttu-id="737df-107">`InitNameArray` 또는 `CloseDialog`와 같이 동사를 사용 하 여 함수 및 메서드 이름을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
- <span data-ttu-id="737df-108">`EmployeeName` 또는 `CarAccessory`와 같이 명사를 사용 하 여 클래스, 구조체, 모듈 및 속성 이름을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
- <span data-ttu-id="737df-109">접두사 "I"를 사용 하 여 인터페이스 이름을 시작 하 고, `IComponent`같은 명사 또는 명사구를 사용 하거나, `IPersistable`와 같이 인터페이스 동작을 설명 하는 형용사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="737df-110">약어는 혼동을 일으킬 수 있으므로 밑줄을 사용 하지 말고 약어를 사용 하는 경우에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
- <span data-ttu-id="737df-111">"`MouseEventHandler`"와 같이 이벤트 유형과 "`EventHandler`" 접미사를 설명 하는 명사를 사용 하 여 이벤트 처리기 이름을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
- <span data-ttu-id="737df-112">이벤트 인수 클래스 이름에 "`EventArgs`" 접미사를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
- <span data-ttu-id="737df-113">이벤트의 개념이 "before" 또는 "after" 인 경우 "`ControlAdd`" 또는 "`ControlAdded`"와 같이 현재 또는 과거 시제에 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
- <span data-ttu-id="737df-114">길고 자주 사용 되는 용어의 경우 약어를 사용 하 여 이름 길이를 적절 하 게 유지 합니다 (예: "HTML(Hypertext Markup Language)" 대신 "HTML").</span><span class="sxs-lookup"><span data-stu-id="737df-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="737df-115">일반적으로 32 자를 초과 하는 변수 이름은 낮은 해상도로 설정 된 모니터에서 읽기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="737df-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="737df-116">또한 약어가 전체 응용 프로그램 전체에서 일관 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="737df-117">"HTML"과 "HTML(Hypertext Markup Language)" 간에 프로젝트를 임의로 전환 하면 혼동을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="737df-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
- <span data-ttu-id="737df-118">외부 범위의 이름과 동일한 내부 범위에서 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="737df-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="737df-119">잘못 된 변수에 액세스 하면 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="737df-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="737df-120">변수와 이름이 같은 키워드 사이에 충돌이 발생 하는 경우 적절 한 형식 라이브러리를 사용 하 여 키워드 앞에 키워드를 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737df-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="737df-121">예를 들어 `Date`라는 변수가 있는 경우 <xref:System.DateTime.Date%2A?displayProperty=nameWithType>를 호출 해야만 내장 `Date` 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="737df-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="737df-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="737df-122">See also</span></span>

- [<span data-ttu-id="737df-123">코드에서 요소 이름으로 사용되는 키워드</span><span class="sxs-lookup"><span data-stu-id="737df-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [<span data-ttu-id="737df-124">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="737df-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="737df-125">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="737df-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="737df-126">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="737df-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="737df-127">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="737df-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
