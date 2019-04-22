---
title: Imports 문-.NET Namespace 및 형식 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: 4574bab62ca6d095ab66c17bf186da5f3d79bfb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826524"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="78803-102">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="78803-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="78803-103">사용 하도록 설정에는 네임 스페이스 한정자 없이 참조 되는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78803-104">구문</span><span class="sxs-lookup"><span data-stu-id="78803-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="78803-105">요소</span><span class="sxs-lookup"><span data-stu-id="78803-105">Parts</span></span>  
  
|<span data-ttu-id="78803-106">용어</span><span class="sxs-lookup"><span data-stu-id="78803-106">Term</span></span>|<span data-ttu-id="78803-107">정의</span><span class="sxs-lookup"><span data-stu-id="78803-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="78803-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-108">Optional.</span></span> <span data-ttu-id="78803-109">*가져오기 별칭* 코드를 참조할 수 있는 이름 또는 `namespace` 정규화 문자열 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="78803-110">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78803-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="78803-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="78803-111">Required.</span></span> <span data-ttu-id="78803-112">가져올 네임 스페이스의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="78803-113">중첩 될 수 있습니다 문자열 네임 스페이스의 모든 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="78803-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-114">Optional.</span></span> <span data-ttu-id="78803-115">네임 스페이스에 선언 된 프로그래밍 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="78803-116">모든 컨테이너 요소를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78803-117">설명</span><span class="sxs-lookup"><span data-stu-id="78803-117">Remarks</span></span>  
 <span data-ttu-id="78803-118">`Imports` 문을 직접 참조할 수 지정된 된 네임 스페이스에 포함 된 형식을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="78803-119">단일 네임 스페이스 이름 또는 중첩 된 네임 스페이스의 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="78803-120">각 중첩 된 네임 스페이스는 마침표로 다음 더 높은 수준의 네임 스페이스에서 (`.`) 다음 예제와 같이, 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="78803-121">각 소스 파일에는 개수에 관계 없이 포함 될 수 있습니다 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="78803-122">이러한 옵션 선언 같은 따라야 합니다 `Option Strict` 문 및 이러한 앞에 야 프로그래밍 요소 선언에 같은 `Module` 또는 `Class` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="78803-123">사용할 수 있습니다 `Imports` 파일 수준 에서만.</span><span class="sxs-lookup"><span data-stu-id="78803-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="78803-124">즉, 가져오기 선언 컨텍스트 소스 파일 이어야 하며 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="78803-125">`Imports` 문을 해도 다른 프로젝트와 어셈블리의 요소를 프로젝트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="78803-126">가져오기 대 한 참조를 설정 하는 위치를 차지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="78803-127">만 이미 프로젝트에 사용할 수 있는 이름을 한정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="78803-128">자세한 내용은 "를 포함 하는 요소 가져오기"를 참조 하세요 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78803-129">암시적 정의할 수 있습니다 `Imports` 문에서 사용 하 여 합니다 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="78803-130">자세한 내용은 [방법: 가져온된 네임 스페이스 (Visual Basic)를 제거 또는 추가](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="78803-131">Import 별칭</span><span class="sxs-lookup"><span data-stu-id="78803-131">Import Aliases</span></span>  
 <span data-ttu-id="78803-132">*가져오기 별칭* 네임 스페이스 또는 형식에 대 한 별칭을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="78803-133">Import 별칭은 하나 이상의 네임 스페이스에 선언 되어 있는 동일한 이름의 항목을 사용 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="78803-134">자세한 내용 및 예제에 나오는 "요소 이름 한정" [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="78803-135">동일한 이름의 모듈 수준에서 멤버를 선언 하지 해야 `aliasname`합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="78803-136">Visual Basic 컴파일러를 사용 하는 경우 `aliasname` 선언 된 멤버에 대해서만 하 고 더 이상 가져오기 별칭으로 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="78803-137">XML 네임 스페이스 접두사를 가져오기 위한 가져오기 별칭 선언에 대 한 구문과 같은, 있지만 결과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="78803-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="78803-138">가져오기 별칭은 XML 네임 스페이스 접두사를 사용할 수 XML 리터럴 또는 XML 축 속성에만 접두사로 정규화 된 요소 또는 특성 이름에 대 한 반면 코드 식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="78803-139">요소 이름</span><span class="sxs-lookup"><span data-stu-id="78803-139">Element Names</span></span>  
 <span data-ttu-id="78803-140">제공 하는 경우 `element`를 나타내야 합니다는 *컨테이너 요소*, 다른 요소를 포함할 수 있는 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="78803-141">클래스, 구조체, 모듈, 인터페이스 및 열거형을 포함 하는 컨테이너 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="78803-142">사용할 수 있는 요소의 범위를 `Imports` 를 지정 했는지 여부에 문이 종속 `element`합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="78803-143">만 지정한 경우 `namespace`해당 네임 스페이스의 멤버와 해당 네임 스페이스 내에서 컨테이너 요소의 멤버 이름이 고유 하 게 모든, 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="78803-144">둘 다 지정 하는 경우 `namespace` 고 `element`, 해당 요소의 멤버 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78803-145">예제</span><span class="sxs-lookup"><span data-stu-id="78803-145">Example</span></span>  
 <span data-ttu-id="78803-146">다음 예제에서는 C:\ 디렉터리에 있는 폴더를 모두 사용 하 여 반환 된 <xref:System.IO.DirectoryInfo> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="78803-147">코드에 없는 `Imports` 파일의 맨 위에 있는 문.</span><span class="sxs-lookup"><span data-stu-id="78803-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="78803-148">따라서 합니다 `DirectoryInfo`, <xref:System.Text.StringBuilder>, 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf> 참조는 네임 스페이스를 사용 하 여 정규화 합니다.</span><span class="sxs-lookup"><span data-stu-id="78803-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="78803-149">예제</span><span class="sxs-lookup"><span data-stu-id="78803-149">Example</span></span>  
 <span data-ttu-id="78803-150">다음 예제를 포함 `Imports` 참조 된 네임 스페이스에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="78803-151">따라서 형식 네임 스페이스를 사용 하 여 완벽 하 게 정규화 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78803-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="78803-152">예제</span><span class="sxs-lookup"><span data-stu-id="78803-152">Example</span></span>  
 <span data-ttu-id="78803-153">다음 예제를 포함 `Imports` 참조 된 네임 스페이스에 대 한 별칭을 사용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="78803-154">형식은 별칭으로 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78803-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="78803-155">예제</span><span class="sxs-lookup"><span data-stu-id="78803-155">Example</span></span>  
 <span data-ttu-id="78803-156">다음 예제를 포함 `Imports` 참조 된 형식에 대 한 별칭을 사용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="78803-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="78803-157">별칭은 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78803-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="78803-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="78803-158">See also</span></span>

- [<span data-ttu-id="78803-159">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="78803-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="78803-160">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="78803-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="78803-161">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="78803-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="78803-162">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="78803-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="78803-163">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="78803-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
