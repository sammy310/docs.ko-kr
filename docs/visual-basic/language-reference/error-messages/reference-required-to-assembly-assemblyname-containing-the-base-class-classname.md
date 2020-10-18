---
title: 기본 클래스 '<assemblyname>'을(를) 포함하는 '<classname>' 어셈블리에 대한 참조가 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: d2fb3498219dfe3318ec418ede250de818874ba9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162338"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="41c3a-102">BC30007: ' ' \<assemblyname> 기본 클래스를 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 합니다. \<classname></span><span class="sxs-lookup"><span data-stu-id="41c3a-102">BC30007: Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>

<span data-ttu-id="41c3a-103">기본 클래스 ' '을 (를) 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 \<assemblyname> \<classname> 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c3a-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="41c3a-104">하나를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="41c3a-104">Add one to your project.</span></span>

 <span data-ttu-id="41c3a-105">클래스는 프로젝트에서 직접 참조하지 않는 어셈블리 또는 DLL(동적 연결 라이브러리)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="41c3a-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="41c3a-106">클래스가 둘 이상의 DLL 또는 어셈블리에서 정의 된 경우에는 모호성을 방지 하기 위해 Visual Basic 컴파일러에 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="41c3a-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>

 <span data-ttu-id="41c3a-107">**오류 ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="41c3a-107">**Error ID:** BC30007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="41c3a-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="41c3a-108">To correct this error</span></span>

- <span data-ttu-id="41c3a-109">참조되지 않은 DLL 또는 어셈블리 이름을 프로젝트 참조에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="41c3a-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>

## <a name="see-also"></a><span data-ttu-id="41c3a-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41c3a-110">See also</span></span>

- [<span data-ttu-id="41c3a-111">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="41c3a-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="41c3a-112">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="41c3a-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
