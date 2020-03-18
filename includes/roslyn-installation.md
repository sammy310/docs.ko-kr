---
ms.openlocfilehash: 2872c5909b382e01fdd231019a12970caa3b77d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "72526762"
---
## <a name="installation-instructions---visual-studio-installer"></a><span data-ttu-id="67c45-101">설치 지침 - Visual Studio 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="67c45-101">Installation instructions - Visual Studio Installer</span></span>

<span data-ttu-id="67c45-102">**Visual Studio 설치 관리자**에서 **.NET Compiler Platform SDK**를 찾는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-visual-studio-installer---workloads-view"></a><span data-ttu-id="67c45-103">Visual Studio 설치 관리자를 사용한 설치 - 워크로드 보기</span><span class="sxs-lookup"><span data-stu-id="67c45-103">Install using the Visual Studio Installer - Workloads view</span></span>

<span data-ttu-id="67c45-104">.NET Compiler Platform SDK는 Visual Studio 확장 개발 워크로드의 일부로 자동으로 선택되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="67c45-105">선택적 구성 요소로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="67c45-106">**Visual Studio 설치 관리자**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-106">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="67c45-107">**수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-107">Select **Modify**</span></span>
1. <span data-ttu-id="67c45-108">**Visual Studio 확장 개발** 워크로드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="67c45-109">요약 트리에서 **Visual Studio 확장 개발** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="67c45-110">**.NET Compiler Platform SDK**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="67c45-111">선택적 구성 요소 아래에서 마지막에 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="67c45-112">필요에 따라, 시각화 도우미에서 **DGML 편집기**에 그래프도 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="67c45-113">요약 트리에서 **개별 구성 요소** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="67c45-114">**DGML 편집기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a><span data-ttu-id="67c45-115">Visual Studio 설치 관리자를 사용한 설치 - 개별 구성 요소 탭</span><span class="sxs-lookup"><span data-stu-id="67c45-115">Install using the Visual Studio Installer - Individual components tab</span></span>

1. <span data-ttu-id="67c45-116">**Visual Studio 설치 관리자**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-116">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="67c45-117">**수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-117">Select **Modify**</span></span>
1. <span data-ttu-id="67c45-118">**개별 구성 요소** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-118">Select the **Individual components** tab</span></span>
1. <span data-ttu-id="67c45-119">**.NET Compiler Platform SDK**에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="67c45-120">**컴파일러, 빌드 도구 및 런타임** 섹션의 위쪽에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="67c45-121">필요에 따라, 시각화 도우미에서 **DGML 편집기**에 그래프도 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="67c45-122">**DGML 편집기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="67c45-123">**코드 도구** 섹션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67c45-123">You'll find it under the **Code tools** section.</span></span>
