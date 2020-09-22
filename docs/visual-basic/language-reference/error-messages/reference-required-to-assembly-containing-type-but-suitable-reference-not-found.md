---
title: "'<assemblyidentity>' 형식을 포함하는 '<typename>' 어셈블리에 대한 참조가 필요하지만 '<projectname1>' 프로젝트와 '<projectname2>' 프로젝트 사이의 모호성 때문에 적합한 참조를 찾을 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: ffc6b3c180c86abe272d56d0ecf3042d8181da59
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870902"
---
# <a name="reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a><span data-ttu-id="abb4d-102">'\<assemblyidentity>' 형식을 포함하는 '\<typename>' 어셈블리에 대한 참조가 필요하지만 '\<projectname1>' 프로젝트와 '\<projectname2>' 프로젝트 사이의 모호성 때문에 적합한 참조를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-102">Reference required to assembly '\<assemblyidentity>' containing type '\<typename>', but a suitable reference could not be found due to ambiguity between projects '\<projectname1>' and '\<projectname2>'</span></span>

<span data-ttu-id="abb4d-103">식은 프로젝트 외부에 정의된 클래스, 구조체, 인터페이스, 열거형 또는 대리자와 같은 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="abb4d-104">그러나 해당 형식을 정의하는 둘 이상의 어셈블리에 대한 프로젝트 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="abb4d-105">인용된 프로젝트는 이름이 동일한 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="abb4d-106">따라서 컴파일러에서 사용자가 액세스하려는 형식에 사용할 어셈블리를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="abb4d-107">다른 어셈블리에 정의 된 형식에 액세스 하려면 Visual Basic 컴파일러에 해당 어셈블리에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="abb4d-108">이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="abb4d-109">**오류 ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="abb4d-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="abb4d-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="abb4d-110">To correct this error</span></span>  
  
1. <span data-ttu-id="abb4d-111">참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="abb4d-112">이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="abb4d-113">프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 파일에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb4d-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb4d-114">참조</span><span class="sxs-lookup"><span data-stu-id="abb4d-114">See also</span></span>

- [<span data-ttu-id="abb4d-115">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="abb4d-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="abb4d-116">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="abb4d-116">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="abb4d-117">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="abb4d-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="abb4d-118">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="abb4d-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
