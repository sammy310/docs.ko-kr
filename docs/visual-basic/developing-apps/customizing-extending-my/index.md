---
title: 프로젝트 사용자 지정 및 My 확장
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: e6ed43aeff90295f71590bcee180ca1e0f88e5ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330335"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="3a71f-102">Visual Basic에서 프로젝트 사용자 지정 및 My 확장</span><span class="sxs-lookup"><span data-stu-id="3a71f-102">Customizing Projects and Extending My with Visual Basic</span></span>

<span data-ttu-id="3a71f-103">프로젝트 템플릿을 사용자 지정하여 추가 `My` 개체를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="3a71f-104">이렇게 하면 다른 개발자가 쉽게 개체를 찾고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-104">This makes it easy for other developers to find and use your objects.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3a71f-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="3a71f-105">In this section</span></span>

- [<span data-ttu-id="3a71f-106">Visual Basic의 내 네임스페이스 확장</span><span class="sxs-lookup"><span data-stu-id="3a71f-106">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)  
 <span data-ttu-id="3a71f-107">Visual Basic에서 `My` 네임스페이스에 사용자 지정 멤버 및 값을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>
- [<span data-ttu-id="3a71f-108">사용자 지정 My 확장명 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="3a71f-108">Packaging and Deploying Custom My Extensions</span></span>](packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="3a71f-109">Visual Studio 템플릿을 사용하여 사용자 지정 `My` 네임스페이스 확장을 게시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>
- [<span data-ttu-id="3a71f-110">Visual Basic 애플리케이션 모델 확장</span><span class="sxs-lookup"><span data-stu-id="3a71f-110">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="3a71f-111"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스의 멤버를 재정의하여 애플리케이션 모델에 대한 고유한 확장을 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>
- [<span data-ttu-id="3a71f-112">My에 사용할 수 있는 개체 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3a71f-112">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="3a71f-113">이 프로젝트의 \_MYTYPE 조건부 컴파일 상수를 설정하여 사용 가능한 `My` 개체를 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-113">Describes how to control which `My` objects are enabled by setting your project's \_MYTYPE conditional-compilation constant.</span></span>

## <a name="related-sections"></a><span data-ttu-id="3a71f-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="3a71f-114">Related sections</span></span>

- [<span data-ttu-id="3a71f-115">My를 사용한 개발</span><span class="sxs-lookup"><span data-stu-id="3a71f-115">Development with My</span></span>](../development-with-my/index.md)  
 <span data-ttu-id="3a71f-116">기본적으로 다양한 프로젝트 형식에서 사용할 수 있는 `My` 개체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-116">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="3a71f-117">Visual Basic 애플리케이션 모델 개요</span><span class="sxs-lookup"><span data-stu-id="3a71f-117">Overview of the Visual Basic Application Model</span></span>](../development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="3a71f-118">Windows Forms 애플리케이션의 동작을 제어하기 위한 Visual Basic 모델을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>
- [<span data-ttu-id="3a71f-119">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="3a71f-119">How My Depends on Project Type</span></span>](../development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="3a71f-120">기본적으로 다양한 프로젝트 형식에서 사용할 수 있는 `My` 개체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-120">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="3a71f-121">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="3a71f-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="3a71f-122">컴파일러가 조건부 컴파일을 사용하여 다른 섹션을 컴파일 및 제외하는 코드의 특정 섹션을 선택하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="3a71f-123">현재 애플리케이션과 관련된 속성, 메서드 및 이벤트를 제공하는 `My` 개체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a71f-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a71f-124">참조</span><span class="sxs-lookup"><span data-stu-id="3a71f-124">See also</span></span>

- [<span data-ttu-id="3a71f-125">Visual Basic을 사용한 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="3a71f-125">Developing Applications with Visual Basic</span></span>](../index.md)
