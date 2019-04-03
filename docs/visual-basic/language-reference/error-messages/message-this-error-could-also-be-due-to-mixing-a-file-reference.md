---
title: <message> 이 오류는 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 수도 있습니다 '<assemblyname>'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 0f2e7040de5ea74f3793129d23d4ae8c80b71f25
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841552"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="d83e8-102">\<메시지 > 참조 어셈블리에 대 한 프로젝트 참조를 사용 하 여 파일 참조가 섞여 있기 때문에이 오류도 수 '\<assemblyname >'</span><span class="sxs-lookup"><span data-stu-id="d83e8-102">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>
<span data-ttu-id="d83e8-103">\<메시지 > 참조 어셈블리에 대 한 프로젝트 참조를 사용 하 여 파일 참조가 섞여 있기 때문에이 오류도 수 '\<assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="d83e8-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="d83e8-104">이 경우에 대 한 파일 참조를 교체를 시도 '\<assemblyfilename >' 프로젝트에서 '\<projectname1 >'에 대 한 프로젝트 참조를 사용 하 여 '\<projectname2 >'입니다.</span><span class="sxs-lookup"><span data-stu-id="d83e8-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="d83e8-105">코드 프로젝트에서 다른 프로젝트의 멤버에 액세스할 수 있지만 솔루션의 구성 참조를 해결 하려면 Visual Basic 컴파일러를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d83e8-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="d83e8-106">다른 어셈블리에 정의 된 형식에 액세스 하려면 해당 어셈블리에 대 한 참조를 Visual Basic 컴파일러에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83e8-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="d83e8-107">이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83e8-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="d83e8-108">**오류 ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="d83e8-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d83e8-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d83e8-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="d83e8-110">참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d83e8-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="d83e8-111">이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83e8-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="d83e8-112">프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 프로젝트에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d83e8-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83e8-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d83e8-113">See also</span></span>

- [<span data-ttu-id="d83e8-114">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="d83e8-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="d83e8-115">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="d83e8-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="d83e8-116">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="d83e8-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="d83e8-117">끊어진 참조 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d83e8-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
