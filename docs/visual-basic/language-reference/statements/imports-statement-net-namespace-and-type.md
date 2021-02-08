---
description: '자세한 정보: Imports 문 (.NET 네임 스페이스 및 형식)'
title: Imports 문-.NET 네임 스페이스 및 형식
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
ms.openlocfilehash: 28b7608e250fdba9c39f0209154d5a3d8f725eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768976"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="b8cf6-103">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="b8cf6-103">Imports Statement (.NET Namespace and Type)</span></span>

<span data-ttu-id="b8cf6-104">네임 스페이스 한정자 없이 형식 이름을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-104">Enables type names to be referenced without namespace qualification.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8cf6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8cf6-105">Syntax</span></span>

```vb
Imports [ aliasname = ] namespace
' -or-
Imports [ aliasname = ] namespace.element
```

## <a name="parts"></a><span data-ttu-id="b8cf6-106">부분</span><span class="sxs-lookup"><span data-stu-id="b8cf6-106">Parts</span></span>

|<span data-ttu-id="b8cf6-107">용어</span><span class="sxs-lookup"><span data-stu-id="b8cf6-107">Term</span></span>|<span data-ttu-id="b8cf6-108">정의</span><span class="sxs-lookup"><span data-stu-id="b8cf6-108">Definition</span></span>|
|---|---|
|`aliasname`|<span data-ttu-id="b8cf6-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-109">Optional.</span></span> <span data-ttu-id="b8cf6-110">코드에서 전체 한정 문자열 대신 참조할 수 있는 *가져오기 별칭* 또는 이름입니다 `namespace` .</span><span class="sxs-lookup"><span data-stu-id="b8cf6-110">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="b8cf6-111">[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-111">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`namespace`|<span data-ttu-id="b8cf6-112">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-112">Required.</span></span> <span data-ttu-id="b8cf6-113">가져오는 네임 스페이스의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-113">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="b8cf6-114">는 임의의 수준에 중첩 된 네임 스페이스의 문자열일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-114">Can be a string of namespaces nested to any level.</span></span>|
|`element`|<span data-ttu-id="b8cf6-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-115">Optional.</span></span> <span data-ttu-id="b8cf6-116">네임 스페이스에 선언 된 프로그래밍 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-116">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="b8cf6-117">모든 컨테이너 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-117">Can be any container element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b8cf6-118">설명</span><span class="sxs-lookup"><span data-stu-id="b8cf6-118">Remarks</span></span>

<span data-ttu-id="b8cf6-119">`Imports`문을 사용 하면 지정 된 네임 스페이스에 포함 된 형식을 직접 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-119">The `Imports` statement enables types that are contained in a given namespace to be referenced directly.</span></span>

<span data-ttu-id="b8cf6-120">단일 네임 스페이스 이름 또는 중첩 된 네임 스페이스의 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-120">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="b8cf6-121">다음 예제와 같이 중첩 된 각 네임 스페이스는 다음 상위 수준 네임 스페이스와 마침표 ()로 구분 됩니다 `.` .</span><span class="sxs-lookup"><span data-stu-id="b8cf6-121">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates:</span></span>

```vb
Imports System.Collections.Generic
```

<span data-ttu-id="b8cf6-122">각 소스 파일에는 개수에 관계 없이 문을 포함할 수 있습니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="b8cf6-122">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="b8cf6-123">이는 문과 같은 모든 옵션 선언을 따라야 하며, `Option Strict` 또는 문과 같은 프로그래밍 요소 선언 앞에와 야 합니다 `Module` `Class` .</span><span class="sxs-lookup"><span data-stu-id="b8cf6-123">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>

<span data-ttu-id="b8cf6-124">는 `Imports` 파일 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-124">You can use `Imports` only at file level.</span></span> <span data-ttu-id="b8cf6-125">즉, 가져오기에 대 한 선언 컨텍스트는 소스 파일 이어야 하며 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-125">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>

<span data-ttu-id="b8cf6-126">`Imports`문은 다른 프로젝트 및 어셈블리의 요소를 프로젝트에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-126">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="b8cf6-127">가져오기는 참조 설정 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-127">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="b8cf6-128">프로젝트에 이미 사용할 수 있는 이름을 한정할 필요성이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-128">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="b8cf6-129">자세한 내용은 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조에서 "포함 하는 요소 가져오기"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-129">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b8cf6-130">`Imports` [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)를 사용 하 여 암시적 문을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-130">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="b8cf6-131">자세한 내용은 [방법: 가져온 네임 스페이스 추가 또는 제거 (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-131">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>

## <a name="import-aliases"></a><span data-ttu-id="b8cf6-132">Import 별칭</span><span class="sxs-lookup"><span data-stu-id="b8cf6-132">Import Aliases</span></span>

<span data-ttu-id="b8cf6-133">*가져오기 별칭* 은 네임 스페이스 또는 형식에 대 한 별칭을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-133">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="b8cf6-134">가져오기 별칭은 하나 이상의 네임 스페이스에 선언 된 것과 동일한 이름의 항목을 사용 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-134">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="b8cf6-135">자세한 내용 및 예제는 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조의 "요소 이름 한정"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-135">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="b8cf6-136">와 동일한 이름을 사용 하 여 모듈 수준에서 멤버를 선언 하면 안 됩니다 `aliasname` .</span><span class="sxs-lookup"><span data-stu-id="b8cf6-136">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="b8cf6-137">이 경우 Visual Basic 컴파일러는 `aliasname` 선언 된 멤버에만를 사용 하며 더 이상 가져오기 별칭으로 인식 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-137">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>

<span data-ttu-id="b8cf6-138">가져오기 별칭을 선언 하는 데 사용 되는 구문은 XML 네임 스페이스 접두사를 가져오는 데 사용 되는 구문과 유사 하지만 결과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-138">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="b8cf6-139">Xml 네임 스페이스 접두사는 xml 리터럴 또는 XML 축 속성 에서만 정규화 된 요소 또는 특성 이름에 대 한 접두사로 사용할 수 있는 반면, 코드에서는 가져오기 별칭을 식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-139">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>

### <a name="element-names"></a><span data-ttu-id="b8cf6-140">요소 이름</span><span class="sxs-lookup"><span data-stu-id="b8cf6-140">Element Names</span></span>

<span data-ttu-id="b8cf6-141">를 제공 하는 경우 `element` 다른 요소를 포함할 수 있는 프로그래밍 요소인 *컨테이너 요소* 를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-141">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="b8cf6-142">컨테이너 요소에는 클래스, 구조체, 모듈, 인터페이스 및 열거형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-142">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>

<span data-ttu-id="b8cf6-143">문에서 사용할 수 있는 요소의 범위는 `Imports` 지정 여부에 따라 달라 집니다 `element` .</span><span class="sxs-lookup"><span data-stu-id="b8cf6-143">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="b8cf6-144">만 지정 하는 경우 `namespace` 해당 네임 스페이스의 고유 하 게 명명 된 멤버와 해당 네임 스페이스 내에 있는 컨테이너 요소의 멤버를 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-144">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="b8cf6-145">및를 둘 다 지정 하는 경우 `namespace` `element` 해당 요소의 멤버만 한정 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-145">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>

## <a name="example"></a><span data-ttu-id="b8cf6-146">예제</span><span class="sxs-lookup"><span data-stu-id="b8cf6-146">Example</span></span>

<span data-ttu-id="b8cf6-147">다음 예제에서는 클래스를 사용 하 여 *C: \\* 디렉터리의 모든 폴더를 반환 합니다 <xref:System.IO.DirectoryInfo> .</span><span class="sxs-lookup"><span data-stu-id="b8cf6-147">The following example returns all the folders in the *C:\\* directory by using the <xref:System.IO.DirectoryInfo> class:</span></span>

<span data-ttu-id="b8cf6-148">코드에는 `Imports` 파일 맨 위에 문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-148">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="b8cf6-149">따라서, <xref:System.IO.DirectoryInfo> <xref:System.Text.StringBuilder> 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf> 참조는 모두 네임 스페이스를 사용 하 여 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-149">Therefore, the <xref:System.IO.DirectoryInfo>, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>

[!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]

## <a name="example"></a><span data-ttu-id="b8cf6-150">예제</span><span class="sxs-lookup"><span data-stu-id="b8cf6-150">Example</span></span>

<span data-ttu-id="b8cf6-151">다음 예제에서는 `Imports` 참조 된 네임 스페이스에 대 한 문을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-151">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="b8cf6-152">따라서 네임 스페이스를 사용 하 여 형식을 정규화 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-152">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>

[!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]

[!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]
  
## <a name="example"></a><span data-ttu-id="b8cf6-153">예제</span><span class="sxs-lookup"><span data-stu-id="b8cf6-153">Example</span></span>

<span data-ttu-id="b8cf6-154">다음 예제에는 `Imports` 참조 된 네임 스페이스에 대 한 별칭을 만드는 문이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-154">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="b8cf6-155">형식은 별칭으로 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-155">The types are qualified with the aliases.</span></span>

[!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]

[!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]

## <a name="example"></a><span data-ttu-id="b8cf6-156">예제</span><span class="sxs-lookup"><span data-stu-id="b8cf6-156">Example</span></span>

<span data-ttu-id="b8cf6-157">다음 예에는 `Imports` 참조 된 형식에 대 한 별칭을 만드는 문이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-157">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="b8cf6-158">별칭은 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cf6-158">Aliases are used to specify the types.</span></span>

[!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]

[!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]
  
## <a name="see-also"></a><span data-ttu-id="b8cf6-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8cf6-159">See also</span></span>

- [<span data-ttu-id="b8cf6-160">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="b8cf6-160">Namespace Statement</span></span>](namespace-statement.md)
- [<span data-ttu-id="b8cf6-161">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b8cf6-161">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="b8cf6-162">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="b8cf6-162">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="b8cf6-163">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="b8cf6-163">Imports Statement (XML Namespace)</span></span>](imports-statement-xml-namespace.md)
- [<span data-ttu-id="b8cf6-164">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="b8cf6-164">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
