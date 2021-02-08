---
description: "' ' 형식을 포함 하는 ' ' 어셈블리에 대해 BC30969: Reference가 필요 <assemblyidentity> <typename> 하지만, ' <projectname1> ' 및 ' 프로젝트 간의 모호성 때문에 적합 한 참조를 찾을 수 없습니다.<projectname2>"
title: "'<assemblyidentity>' 형식을 포함하는 '<typename>' 어셈블리에 대한 참조가 필요하지만 '<projectname1>' 프로젝트와 '<projectname2>' 프로젝트 사이의 모호성 때문에 적합한 참조를 찾을 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 945a6558ff9eea20a28bc27da27e495d0eddfb15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792039"
---
# <a name="bc30969-reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a><span data-ttu-id="652ee-103">BC30969: ' ' 형식을 포함 하는 ' ' 어셈블리에 대 한 참조가 필요 \<assemblyidentity> \<typename> 하지만 ' \<projectname1> ' 프로젝트와 ' ' 프로젝트 사이의 모호성 때문에 적합 한 참조를 찾을 수 없습니다. \<projectname2></span><span class="sxs-lookup"><span data-stu-id="652ee-103">BC30969: Reference required to assembly '\<assemblyidentity>' containing type '\<typename>', but a suitable reference could not be found due to ambiguity between projects '\<projectname1>' and '\<projectname2>'</span></span>

<span data-ttu-id="652ee-104">식은 프로젝트 외부에 정의된 클래스, 구조체, 인터페이스, 열거형 또는 대리자와 같은 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-104">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="652ee-105">그러나 해당 형식을 정의하는 둘 이상의 어셈블리에 대한 프로젝트 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-105">However, you have project references to more than one assembly defining that type.</span></span>

 <span data-ttu-id="652ee-106">인용된 프로젝트는 이름이 동일한 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-106">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="652ee-107">따라서 컴파일러에서 사용자가 액세스하려는 형식에 사용할 어셈블리를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-107">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>

 <span data-ttu-id="652ee-108">다른 어셈블리에 정의 된 형식에 액세스 하려면 Visual Basic 컴파일러에 해당 어셈블리에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-108">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="652ee-109">이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-109">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>

 <span data-ttu-id="652ee-110">**오류 ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="652ee-110">**Error ID:** BC30969</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="652ee-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="652ee-111">To correct this error</span></span>

1. <span data-ttu-id="652ee-112">참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-112">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="652ee-113">이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-113">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>

2. <span data-ttu-id="652ee-114">프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 파일에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="652ee-114">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>

## <a name="see-also"></a><span data-ttu-id="652ee-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="652ee-115">See also</span></span>

- [<span data-ttu-id="652ee-116">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="652ee-116">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="652ee-117">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="652ee-117">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="652ee-118">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="652ee-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="652ee-119">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="652ee-119">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
