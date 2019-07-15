---
ms.openlocfilehash: dab6b435a885d862d08f94dd31de79625f19bcc0
ms.sourcegitcommit: 6472349821dbe202d01182bc2cfe9d7176eaaa6c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67870502"
---
## <a name="installation-instructions---visual-studio-installer"></a><span data-ttu-id="55d50-101">설치 지침 - Visual Studio 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="55d50-101">Installation instructions - Visual Studio Installer</span></span>

<span data-ttu-id="55d50-102">**Visual Studio 설치 관리자**에서 **.NET Compiler Platform SDK**를 찾는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-visual-studio-installer---workloads-view"></a><span data-ttu-id="55d50-103">Visual Studio 설치 관리자를 사용한 설치 - 워크로드 보기</span><span class="sxs-lookup"><span data-stu-id="55d50-103">Install using the Visual Studio Installer - Workloads view</span></span>

<span data-ttu-id="55d50-104">.NET Compiler Platform SDK는 Visual Studio 확장 개발 워크로드의 일부로 자동으로 선택되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="55d50-105">선택적 구성 요소로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="55d50-106">**Visual Studio 설치 관리자**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="55d50-107">**수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-107">Select **Modify**</span></span> 
1. <span data-ttu-id="55d50-108">**Visual Studio 확장 개발** 워크로드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="55d50-109">요약 트리에서 **Visual Studio 확장 개발** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="55d50-110">**.NET Compiler Platform SDK**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="55d50-111">선택적 구성 요소 아래에서 마지막에 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="55d50-112">필요에 따라, 시각화 도우미에서 **DGML 편집기**에 그래프도 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="55d50-113">요약 트리에서 **개별 구성 요소** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="55d50-114">**DGML 편집기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a><span data-ttu-id="55d50-115">Visual Studio 설치 관리자를 사용한 설치 - 개별 구성 요소 탭</span><span class="sxs-lookup"><span data-stu-id="55d50-115">Install using the Visual Studio Installer - Individual components tab</span></span>

1. <span data-ttu-id="55d50-116">**Visual Studio 설치 관리자**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="55d50-117">**수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-117">Select **Modify**</span></span> 
1. <span data-ttu-id="55d50-118">**개별 구성 요소** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="55d50-119">**.NET Compiler Platform SDK**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="55d50-120">**컴파일러, 빌드 도구 및 런타임** 섹션의 위쪽에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="55d50-121">필요에 따라, 시각화 도우미에서 **DGML 편집기**에 그래프도 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="55d50-122">**DGML 편집기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="55d50-123">**코드 도구** 섹션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d50-123">You'll find it under the **Code tools** section.</span></span>
