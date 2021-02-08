---
description: "BC30007: ' <assemblyname> ' 기본 클래스를 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 합니다.<classname>"
title: 기본 클래스 '<assemblyname>'을(를) 포함하는 '<classname>' 어셈블리에 대한 참조가 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f01795d3e8147015f9f46697b047a8c63099ff32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792052"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="fa725-103">BC30007: ' ' \<assemblyname> 기본 클래스를 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 합니다. \<classname></span><span class="sxs-lookup"><span data-stu-id="fa725-103">BC30007: Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>

<span data-ttu-id="fa725-104">기본 클래스 ' '을 (를) 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 \<assemblyname> \<classname> 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa725-104">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="fa725-105">하나를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa725-105">Add one to your project.</span></span>

 <span data-ttu-id="fa725-106">클래스는 프로젝트에서 직접 참조하지 않는 어셈블리 또는 DLL(동적 연결 라이브러리)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa725-106">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="fa725-107">클래스가 둘 이상의 DLL 또는 어셈블리에서 정의 된 경우에는 모호성을 방지 하기 위해 Visual Basic 컴파일러에 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa725-107">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>

 <span data-ttu-id="fa725-108">**오류 ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="fa725-108">**Error ID:** BC30007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="fa725-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="fa725-109">To correct this error</span></span>

- <span data-ttu-id="fa725-110">참조되지 않은 DLL 또는 어셈블리 이름을 프로젝트 참조에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa725-110">Include the name of the unreferenced DLL or assembly in your project references.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa725-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa725-111">See also</span></span>

- [<span data-ttu-id="fa725-112">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="fa725-112">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="fa725-113">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="fa725-113">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
