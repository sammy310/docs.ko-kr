---
description: '자세한 정보: BC40039: <namespacename> 루트 네임 스페이스의 이름이 <fullnamespacename> CLS 규격이 아님'
title: 루트 네임스페이스 <namespacename>의 이름 <fullnamespacename>이(가) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 2560c5c056c70909a08a48a0ff8b2859b178cc8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795731"
---
# <a name="bc40039-name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="338af-103">BC40039: \<namespacename> 루트 네임 스페이스의 이름이 \<fullnamespacename> CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="338af-103">BC40039: Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>

<span data-ttu-id="338af-104">어셈블리가로 표시 `<CLSCompliant(True)>` 되지만 루트 네임 스페이스 이름의 요소는 밑줄 ()로 시작 `_` 합니다.</span><span class="sxs-lookup"><span data-stu-id="338af-104">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>

 <span data-ttu-id="338af-105">프로그래밍 요소는 하나 이상의 밑줄을 포함할 수 있지만 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)를 준수 하려면 밑줄로 시작 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="338af-105">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="338af-106">[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="338af-106">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="338af-107"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="338af-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="338af-108">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="338af-108">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="338af-109">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="338af-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="338af-110">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="338af-110">By default, this message is a warning.</span></span> <span data-ttu-id="338af-111">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="338af-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="338af-112">**오류 ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="338af-112">**Error ID:** BC40039</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="338af-113">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="338af-113">To correct this error</span></span>

- <span data-ttu-id="338af-114">CLS 규격이 필요한 경우 해당 요소가 밑줄로 시작 하지 않도록 루트 네임 스페이스 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="338af-114">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>

- <span data-ttu-id="338af-115">네임 스페이스 이름이 변경 되지 않은 상태로 유지 되어야 하는 경우 <xref:System.CLSCompliantAttribute> 어셈블리에서를 제거 하거나로 표시 합니다 `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="338af-115">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="338af-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="338af-116">See also</span></span>

- [<span data-ttu-id="338af-117">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="338af-117">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="338af-118">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="338af-118">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="338af-119">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="338af-119">-rootnamespace</span></span>](../../reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="338af-120">프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="338af-120">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="338af-121">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="338af-121">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="338af-122">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="338af-122">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
