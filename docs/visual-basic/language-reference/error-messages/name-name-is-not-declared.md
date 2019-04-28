---
title: "'<name>' 이름이 선언되지 않았습니다."
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3aadc49f91021409123550ba2712f1acf5b99d83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651027"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="125ad-102">이름 '\<이름 >'가 선언 되지 않았습니다</span><span class="sxs-lookup"><span data-stu-id="125ad-102">Name '\<name>' is not declared</span></span>
<span data-ttu-id="125ad-103">문에서 프로그래밍 요소를 참조 하지만 컴파일러에서 정확한 해당 이름의 요소를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="125ad-104">**오류 ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="125ad-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="125ad-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="125ad-105">To correct this error</span></span>  
  
1. <span data-ttu-id="125ad-106">참조하는 문에서 이름의 철자를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="125ad-107">Visual Basic은 대/소문자를 구분 하지만 철자에서를 변형 완전히 다른 이름으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="125ad-108">밑줄(`_`)은 이름의 일부이므로 철자의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="125ad-109">멤버 액세스 연산자 있는지 확인 합니다 (`.`) 개체와 해당 멤버 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="125ad-110">예를 들어 <xref:System.Windows.Forms.TextBox> 이라는 `TextBox1`컨트롤이 있는 경우 해당 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 속성에 액세스하려면 `TextBox1.Text`를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="125ad-111">`TextBox1Text`를 대신 입력하면 다른 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="125ad-112">맞춤법 올바르고 개체 멤버 액세스의 구문이 올바른지, 경우에 요소가 선언 된를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="125ad-113">자세한 내용은 [Declared Elements](../../programming-guide/language-features/declared-elements/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="125ad-114">프로그래밍 요소를 선언한 경우 범위에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="125ad-115">참조 하는 문이 프로그래밍 요소를 선언 하는 지역 외부 인 경우 요소 이름을 정규화 하는 것이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="125ad-116">자세한 내용은 [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="125ad-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="125ad-117">정규화 된 형식 또는 형식 및 멤버 이름을 사용 하지 않는 경우 (코드를 속성으로 참조 하는 예를 들어 `MethodInfo.Name` of `System.Reflection.MethodInfo.Name`), 추가 [Imports 문](../statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="125ad-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="125ad-118">SDK 스타일 프로젝트를 컴파일할 수 하려는 경우 (사용 하 여 프로젝트를 \*줄을 시작 하는.vbproj 파일 `<Project Sdk="Microsoft.NET.Sdk">`), 오류 메시지 참조 형식 또는 Microsoft.VisualBasic.dll 어셈블리의 멤버, 응용 프로그램을 구성 하 고 Visual Basic 런타임 라이브러리에 대 한 참조를 사용 하 여 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="125ad-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="125ad-119">기본적으로 라이브러리의 하위 집합은 SDK 스타일 프로젝트에서 어셈블리에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="125ad-120">예를 들어, 다음 예제에서는 있으므로 컴파일되지 않습니다는 <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="125ad-121">응용 프로그램에 포함 된 Visual Basic 런타임 하위 집합에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   <span data-ttu-id="125ad-122">이 오류를 해결 하기 위해 추가 합니다 `<VBRuntime>Default</VBRuntime>` 요소는 프로젝트를 `<PropertyGroup>` 섹션에서는 Visual Basic 프로젝트 파일은 다음으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="125ad-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="125ad-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="125ad-123">See also</span></span>

- [<span data-ttu-id="125ad-124">선언 및 상수 요약</span><span class="sxs-lookup"><span data-stu-id="125ad-124">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="125ad-125">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="125ad-125">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="125ad-126">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="125ad-126">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="125ad-127">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="125ad-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
