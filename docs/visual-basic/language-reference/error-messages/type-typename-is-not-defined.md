---
description: "자세한 정보: BC30002: 형식 ' <typename> '이 (가) 정의 되지 않았습니다."
title: "'<typename>' 형식이 정의되지 않았습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 48ee0c38492769aea8c1be2e9d54eaa537e35766
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641126"
---
# <a name="bc30002-type-typename-is-not-defined"></a><span data-ttu-id="baad7-103">BC30002: ' \<typename> ' 형식이 정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-103">BC30002: Type '\<typename>' is not defined</span></span>

<span data-ttu-id="baad7-104">문이 정의 되지 않은 형식에 대 한 참조를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-104">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="baad7-105">,, 또는와 같은 선언 문에서 형식을 정의할 수 있습니다 `Enum` `Structure` `Class` `Interface` .</span><span class="sxs-lookup"><span data-stu-id="baad7-105">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>

 <span data-ttu-id="baad7-106">**오류 ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="baad7-106">**Error ID:** BC30002</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="baad7-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="baad7-107">To correct this error</span></span>

- <span data-ttu-id="baad7-108">형식 정의와 해당 참조가 모두 동일한 철자를 사용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-108">Ensure that the type definition and its reference both use the same spelling.</span></span>

- <span data-ttu-id="baad7-109">참조에서 형식 정의에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-109">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="baad7-110">예를 들어 형식이 다른 모듈에 있고 선언 된 경우 `Private` 형식 정의를 참조 하는 모듈로 이동 하거나 선언 `Public` 합니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-110">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>

- <span data-ttu-id="baad7-111">형식의 네임 스페이스를 프로젝트 내에서 다시 정의 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-111">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="baad7-112">인 경우 키워드를 사용 `Global` 하 여 형식 이름을 정규화 합니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-112">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="baad7-113">예를 들어, 프로젝트에서 라는 네임 스페이스를 정의 하는 경우 `System` <xref:System.Object?displayProperty=nameWithType> 키워드를 사용 하 여 정규화 되지 않은 경우 형식에 액세스할 수 없습니다 `Global` `Global.System.Object` .</span><span class="sxs-lookup"><span data-stu-id="baad7-113">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>

- <span data-ttu-id="baad7-114">형식이 정의 되어 있지만 해당 형식이 정의 된 개체 라이브러리 또는 형식 라이브러리가 Visual Basic에 등록 되지 않은 경우 **프로젝트** 메뉴에서 **참조 추가** 를 클릭 한 다음 적절 한 개체 라이브러리 또는 형식 라이브러리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-114">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>

- <span data-ttu-id="baad7-115">형식이 대상 .NET Framework 프로필의 일부인 어셈블리에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="baad7-115">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="baad7-116">자세한 내용은 [.NET Framework 대상 지정 오류 문제 해결](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baad7-116">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>

## <a name="see-also"></a><span data-ttu-id="baad7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baad7-117">See also</span></span>

- [<span data-ttu-id="baad7-118">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="baad7-118">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="baad7-119">Enum 문</span><span class="sxs-lookup"><span data-stu-id="baad7-119">Enum Statement</span></span>](../statements/enum-statement.md)
- [<span data-ttu-id="baad7-120">Structure 문</span><span class="sxs-lookup"><span data-stu-id="baad7-120">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="baad7-121">Class 문</span><span class="sxs-lookup"><span data-stu-id="baad7-121">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="baad7-122">Interface 문</span><span class="sxs-lookup"><span data-stu-id="baad7-122">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="baad7-123">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="baad7-123">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
