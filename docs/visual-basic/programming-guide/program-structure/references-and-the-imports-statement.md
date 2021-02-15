---
description: 참조 및 Imports 문 (Visual Basic)에 대해 자세히 알아보세요.
title: 참조 및 Imports 문
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 3ca685d33f69224a6eea324d7357be4b5203eb45
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468241"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="265b5-103">참조 및 Imports 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="265b5-103">References and the Imports Statement (Visual Basic)</span></span>

<span data-ttu-id="265b5-104">**프로젝트** 메뉴에서 **참조 추가** 명령을 선택 하 여 프로젝트에서 외부 개체를 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-104">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="265b5-105">Visual Basic의 참조는 형식 라이브러리와 같지만 추가 정보를 포함 하는 어셈블리를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-105">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="265b5-106">Imports 문</span><span class="sxs-lookup"><span data-stu-id="265b5-106">The Imports Statement</span></span>  

 <span data-ttu-id="265b5-107">어셈블리는 하나 이상의 네임 스페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-107">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="265b5-108">어셈블리에 대 한 참조를 추가 하는 경우 `Imports` 모듈 내에서 해당 어셈블리의 네임 스페이스에 대 한 표시 여부를 제어 하는 문을 모듈에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-108">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="265b5-109">`Imports`문은 고유한 참조를 제공 하는 데 필요한 네임 스페이스의 일부만 사용할 수 있도록 하는 범위 지정 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-109">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="265b5-110">`Imports`문에는 다음 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-110">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="265b5-111">`Aliasname` 코드 내에서 가져온 네임 스페이스를 참조 하는 데 사용할 수 있는 짧은 이름을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="265b5-112">`Namespace` 는 프로젝트 참조, 프로젝트 내의 정의 또는 이전 문을 통해 사용할 수 있는 네임 스페이스입니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="265b5-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="265b5-113">모듈은 개수에 관계 없이 문을 포함할 수 있습니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="265b5-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="265b5-114">이러한 `Option` 문은 문 (있는 경우)이 아니라 다른 코드 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="265b5-115">프로젝트 참조를 문이나 문과 혼동 하지 마십시오 `Imports` `Declare` .</span><span class="sxs-lookup"><span data-stu-id="265b5-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="265b5-116">프로젝트 참조는 어셈블리의 개체와 같은 외부 개체를 Visual Basic 프로젝트에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="265b5-117">`Imports`문은 프로젝트 참조에 대 한 액세스를 간소화 하는 데 사용 되지만 이러한 개체에 대 한 액세스는 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="265b5-118">`Declare`문은 DLL (동적 연결 라이브러리)에서 외부 프로시저에 대 한 참조를 선언 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="265b5-119">Imports 문과 함께 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="265b5-119">Using Aliases with the Imports Statement</span></span>  

 <span data-ttu-id="265b5-120">`Imports`문을 사용 하면 참조의 정규화 된 이름을 명시적으로 입력할 필요가 없으므로 클래스의 메서드에 더 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="265b5-121">별칭을 사용 하면 네임 스페이스의 한 부분에만 친숙 한 이름을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="265b5-122">예를 들어 단일 텍스트를 여러 줄에 표시 하는 캐리지 리턴/줄 바꿈 시퀀스는 <xref:Microsoft.VisualBasic.ControlChars> 네임 스페이스에 있는 모듈의 일부입니다 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="265b5-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="265b5-123">별칭 없이 프로그램에서이 상수를 사용 하려면 다음 코드를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="265b5-124">`Imports` 문은 항상 모듈의 문 바로 다음에 오는 첫 번째 줄 이어야 합니다 `Option` .</span><span class="sxs-lookup"><span data-stu-id="265b5-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="265b5-125">다음 코드 조각에서는 모듈에 별칭을 가져오고 할당 하는 방법을 보여 줍니다 <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="265b5-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="265b5-126">이 네임 스페이스에 대 한 이후 참조는 훨씬 더 짧을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="265b5-127">`Imports`문에 별칭 이름이 포함 되지 않은 경우에는 가져온 네임 스페이스 내에 정의 된 요소를 한정자 없이 모듈에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="265b5-128">별칭 이름을 지정 하는 경우 해당 네임 스페이스 내에 포함 된 이름에 대 한 한정자로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="265b5-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265b5-129">추가 정보</span><span class="sxs-lookup"><span data-stu-id="265b5-129">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="265b5-130">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="265b5-130">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="265b5-131">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="265b5-131">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="265b5-132">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="265b5-132">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
