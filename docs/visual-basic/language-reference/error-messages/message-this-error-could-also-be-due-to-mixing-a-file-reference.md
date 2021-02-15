---
description: "자세한 정보: BC30971: <message> 이 오류는 ' ' 어셈블리에 대 한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다. <assemblyname>"
title: <message> 이 오류는 '<assemblyname>' 어셈블리에 대한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 73b0e3623bdb5fd7b8ab2110d85436b3f415b4f9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470943"
---
# <a name="bc30971-message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="730d7-103">BC30971: \<message> 이 오류는 ' ' 어셈블리에 대 한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다. \<assemblyname></span><span class="sxs-lookup"><span data-stu-id="730d7-103">BC30971: \<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>

<span data-ttu-id="730d7-104">\<message> 이 오류는 ' 어셈블리에 대 한 프로젝트 참조와 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다 \<assemblyname> . '</span><span class="sxs-lookup"><span data-stu-id="730d7-104">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="730d7-105">이 경우 ' ' 프로젝트의 ' '에 대 한 파일 참조를 \<assemblyfilename> \<projectname1> ' '에 대 한 프로젝트 참조로 바꿔 보세요 \<projectname2> .</span><span class="sxs-lookup"><span data-stu-id="730d7-105">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>

 <span data-ttu-id="730d7-106">프로젝트의 코드에서 다른 프로젝트의 멤버에 액세스 하지만 솔루션 구성에서는 Visual Basic 컴파일러가 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="730d7-106">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>

 <span data-ttu-id="730d7-107">다른 어셈블리에 정의 된 형식에 액세스 하려면 Visual Basic 컴파일러에 해당 어셈블리에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="730d7-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="730d7-108">이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="730d7-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>

 <span data-ttu-id="730d7-109">**오류 ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="730d7-109">**Error ID:** BC30971</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="730d7-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="730d7-110">To correct this error</span></span>

1. <span data-ttu-id="730d7-111">참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="730d7-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="730d7-112">이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730d7-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>

2. <span data-ttu-id="730d7-113">프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 프로젝트에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="730d7-113">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>

## <a name="see-also"></a><span data-ttu-id="730d7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="730d7-114">See also</span></span>

- [<span data-ttu-id="730d7-115">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="730d7-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="730d7-116">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="730d7-116">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="730d7-117">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="730d7-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="730d7-118">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="730d7-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
