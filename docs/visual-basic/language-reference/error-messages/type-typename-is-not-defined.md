---
title: "'<typename>' 형식이 정의되지 않았습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: c2675d61307d92da1710368668f43af3559060a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032099"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="fd43d-102">형식 '\<typename >'가 정의 되지 않은</span><span class="sxs-lookup"><span data-stu-id="fd43d-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="fd43d-103">문에 정의 되지 않은 형식에 대 한 참조를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="fd43d-104">선언문의 형식 같은 정의 `Enum`, `Structure`를 `Class`, 또는 `Interface`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="fd43d-105">**오류 ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="fd43d-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd43d-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="fd43d-106">To correct this error</span></span>  
  
- <span data-ttu-id="fd43d-107">형식 정 및 참조 모두 사용 하는 동일한 철자를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="fd43d-108">형식 정의 참조에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="fd43d-109">예를 들어, 형식이 다른 모듈에서 선언 된 경우 `Private`를 참조 하는 모듈로 형식 정의 이동 하거나 선언 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="fd43d-110">형식의 네임 스페이스에 프로젝트 내에서 다시 정의 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="fd43d-111">인 경우 사용 된 `Global` 형식 이름을 정규화 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="fd43d-112">예를 들어 프로젝트 이름이 네임 스페이스를 정의 하는 경우 `System`는 <xref:System.Object?displayProperty=nameWithType> 사용 하 여 정규화 하지 않은 형식에 액세스할 수 없습니다는 `Global` 키워드: `Global.System.Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="fd43d-113">형식 정의 되었지만 Visual Basic을 사용 하면 클릭에 정의 된 형식 라이브러리를 개체 라이브러리를 등록 하지 않은 경우 **참조 추가** 에 **프로젝트** 메뉴를 선택한 후 적절 한 개체 라이브러리 또는 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="fd43d-114">대상된.NET 프레임 워크 프로필의 일부인 어셈블리의 형식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd43d-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="fd43d-115">자세한 내용은 [.NET Framework 대상 지정 오류 문제 해결](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd43d-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd43d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd43d-116">See also</span></span>

- [<span data-ttu-id="fd43d-117">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="fd43d-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="fd43d-118">Enum 문</span><span class="sxs-lookup"><span data-stu-id="fd43d-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="fd43d-119">Structure 문</span><span class="sxs-lookup"><span data-stu-id="fd43d-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="fd43d-120">Class 문</span><span class="sxs-lookup"><span data-stu-id="fd43d-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="fd43d-121">Interface 문</span><span class="sxs-lookup"><span data-stu-id="fd43d-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="fd43d-122">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="fd43d-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
