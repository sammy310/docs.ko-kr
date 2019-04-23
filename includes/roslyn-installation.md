---
ms.openlocfilehash: 72acd0029d0189de1c724856572957f111b9d18f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675898"
---
## <a name="installation-instructions"></a><span data-ttu-id="f59ac-101">설치 지침</span><span class="sxs-lookup"><span data-stu-id="f59ac-101">Installation instructions</span></span> 

<span data-ttu-id="f59ac-102">**Visual Studio 설치 관리자**에서 **.NET Compiler Platform SDK**를 찾는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-workloads-view"></a><span data-ttu-id="f59ac-103">워크로드 보기를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="f59ac-103">Install using the Workloads view</span></span>

<span data-ttu-id="f59ac-104">.NET Compiler Platform SDK는 Visual Studio 확장 개발 워크로드의 일부로 자동으로 선택되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="f59ac-105">선택적 구성 요소로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="f59ac-106">**Visual Studio 설치 관리자**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="f59ac-107">**수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-107">Select **Modify**</span></span> 
1. <span data-ttu-id="f59ac-108">**Visual Studio 확장 개발** 워크로드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="f59ac-109">요약 트리에서 **Visual Studio 확장 개발** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="f59ac-110">**.NET Compiler Platform SDK**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="f59ac-111">선택적 구성 요소 아래에서 마지막에 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="f59ac-112">필요에 따라, 시각화 도우미에서 **DGML 편집기**에 그래프도 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="f59ac-113">요약 트리에서 **개별 구성 요소** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="f59ac-114">**DGML 편집기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-individual-components-tab"></a><span data-ttu-id="f59ac-115">개별 구성 요소 탭을 사용하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-115">Install using the Individual components tab</span></span>

1. <span data-ttu-id="f59ac-116">**Visual Studio 설치 관리자**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="f59ac-117">**수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-117">Select **Modify**</span></span> 
1. <span data-ttu-id="f59ac-118">**개별 구성 요소** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="f59ac-119">**.NET Compiler Platform SDK**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="f59ac-120">**컴파일러, 빌드 도구 및 런타임** 섹션의 위쪽에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="f59ac-121">필요에 따라, 시각화 도우미에서 **DGML 편집기**에 그래프도 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="f59ac-122">**DGML 편집기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="f59ac-123">**코드 도구** 섹션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59ac-123">You'll find it under the **Code tools** section.</span></span>
