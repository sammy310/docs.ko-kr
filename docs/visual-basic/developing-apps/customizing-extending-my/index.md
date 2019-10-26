---
title: Visual Basic에서 프로젝트 사용자 지정 및 My 확장
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: 97933a9d014a54d5b6e333090cddccace99fcc3c
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960937"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="8ff5f-102">Visual Basic에서 프로젝트 사용자 지정 및 My 확장</span><span class="sxs-lookup"><span data-stu-id="8ff5f-102">Customizing Projects and Extending My with Visual Basic</span></span>

<span data-ttu-id="8ff5f-103">프로젝트 템플릿을 사용자 지정 하 여 추가 `My` 개체를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="8ff5f-104">이렇게 하면 다른 개발자가 쉽게 개체를 찾고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-104">This makes it easy for other developers to find and use your objects.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8ff5f-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8ff5f-105">In this section</span></span>

- [<span data-ttu-id="8ff5f-106">Visual Basic의 내 네임스페이스 확장</span><span class="sxs-lookup"><span data-stu-id="8ff5f-106">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)  
 <span data-ttu-id="8ff5f-107">Visual Basic에서 `My` 네임 스페이스에 사용자 지정 멤버 및 값을 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>
- [<span data-ttu-id="8ff5f-108">사용자 지정 My 확장명 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="8ff5f-108">Packaging and Deploying Custom My Extensions</span></span>](packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="8ff5f-109">Visual Studio 템플릿을 사용 하 여 사용자 지정 `My` 네임 스페이스 확장을 게시 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>
- [<span data-ttu-id="8ff5f-110">Visual Basic 애플리케이션 모델 확장</span><span class="sxs-lookup"><span data-stu-id="8ff5f-110">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="8ff5f-111"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스의 멤버를 재정의 하 여 응용 프로그램 모델에 대 한 고유한 확장을 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>
- [<span data-ttu-id="8ff5f-112">My에 사용할 수 있는 개체 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8ff5f-112">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="8ff5f-113">프로젝트의 \_MYTYPE 조건부 컴파일 상수를 설정 하 여 사용할 수 있는 `My` 개체를 제어 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-113">Describes how to control which `My` objects are enabled by setting your project's \_MYTYPE conditional-compilation constant.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8ff5f-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8ff5f-114">Related sections</span></span>

- [<span data-ttu-id="8ff5f-115">My를 사용한 개발</span><span class="sxs-lookup"><span data-stu-id="8ff5f-115">Development with My</span></span>](../development-with-my/index.md)  
 <span data-ttu-id="8ff5f-116">기본적으로 다른 프로젝트 형식에서 사용할 수 있는 `My` 개체에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-116">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="8ff5f-117">Visual Basic 애플리케이션 모델 개요</span><span class="sxs-lookup"><span data-stu-id="8ff5f-117">Overview of the Visual Basic Application Model</span></span>](../development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="8ff5f-118">Windows Forms 응용 프로그램의 동작을 제어 하기 위한 Visual Basic 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>
- [<span data-ttu-id="8ff5f-119">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="8ff5f-119">How My Depends on Project Type</span></span>](../development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="8ff5f-120">기본적으로 다른 프로젝트 형식에서 사용할 수 있는 `My` 개체에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-120">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="8ff5f-121">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="8ff5f-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="8ff5f-122">컴파일러가 조건부 컴파일을 사용 하 여 다른 섹션을 컴파일 및 제외 하는 코드의 특정 섹션을 선택 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="8ff5f-123">현재 응용 프로그램과 관련 된 속성, 메서드 및 이벤트를 제공 하는 `My` 개체에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff5f-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ff5f-124">참조</span><span class="sxs-lookup"><span data-stu-id="8ff5f-124">See also</span></span>

- [<span data-ttu-id="8ff5f-125">Visual Basic을 사용한 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="8ff5f-125">Developing Applications with Visual Basic</span></span>](../index.md)
