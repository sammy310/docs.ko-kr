---
title: Model Builder에서 GPU 지원을 설치하는 방법
description: Model Builder에서 GPU 지원을 설치하는 방법을 알아봅니다.
ms.date: 08/18/2020
author: luisquintanilla
ms.author: luquinta
ms.topic: how-to
ms.openlocfilehash: ce629efa4c12a69f87196de35ebfe4331dc0800f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608555"
---
# <a name="how-to-install-gpu-support-in-model-builder"></a><span data-ttu-id="b5e10-103">Model Builder에서 GPU 지원을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="b5e10-103">How to install GPU support in Model Builder</span></span>

<span data-ttu-id="b5e10-104">Model Builder에서 GPU를 사용하기 위해 GPU 드라이버를 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-104">Learn how to install the GPU drivers to use your GPU with Model Builder.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5e10-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5e10-105">Prerequisites</span></span>

- <span data-ttu-id="b5e10-106">Model Builder Visual Studio 확장.</span><span class="sxs-lookup"><span data-stu-id="b5e10-106">Model Builder Visual Studio extension.</span></span> <span data-ttu-id="b5e10-107">이 확장은 버전 16.6.1부터 Visual Studio에 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-107">The extension is built into Visual Studio as of version 16.6.1.</span></span>
- <span data-ttu-id="b5e10-108">[Model Builder Visual Studio GPU 지원 확장](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).</span><span class="sxs-lookup"><span data-stu-id="b5e10-108">[Model Builder Visual Studio GPU support extension](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).</span></span>
- <span data-ttu-id="b5e10-109">하나 이상의 CUDA 호환 GPU.</span><span class="sxs-lookup"><span data-stu-id="b5e10-109">At least one CUDA compatible GPU.</span></span> <span data-ttu-id="b5e10-110">호환되는 GPU 목록은 [NVIDIA 가이드](https://developer.nvidia.com/cuda-gpus)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5e10-110">For a list of compatible GPUs, see [NVIDIA's guide](https://developer.nvidia.com/cuda-gpus).</span></span>
- <span data-ttu-id="b5e10-111">NVIDIA 개발자 계정.</span><span class="sxs-lookup"><span data-stu-id="b5e10-111">NVIDIA developer account.</span></span> <span data-ttu-id="b5e10-112">아직 없는 경우 [체험 계정](https://developer.nvidia.com/developer-program)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-112">If you don't have one, [create a free account](https://developer.nvidia.com/developer-program).</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="b5e10-113">종속성 설치</span><span class="sxs-lookup"><span data-stu-id="b5e10-113">Install dependencies</span></span>

1. <span data-ttu-id="b5e10-114">[CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-114">Install [CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive).</span></span> <span data-ttu-id="b5e10-115">다른 최신 버전이 아닌 CUDA v10.0을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-115">Make sure you install CUDA v10.0, not any other newer version.</span></span> <span data-ttu-id="b5e10-116">CUDA 버전을 여러 개 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-116">You cannot have multiple versions of CUDA installed.</span></span>
1. <span data-ttu-id="b5e10-117">[cuDNN v7.6.4 for CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-117">Install [cuDNN v7.6.4 for CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download).</span></span> <span data-ttu-id="b5e10-118">cuDNN 버전을 여러 개 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-118">You cannot have multiple versions of cuDNN installed.</span></span> <span data-ttu-id="b5e10-119">cuDNN v7.6.4 zip 파일을 다운로드하고 압축을 푼 후 `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll`을 `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-119">After downloading cuDNN v7.6.4 zip file and unpacking it, copy `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` to `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b5e10-120">문제 해결</span><span class="sxs-lookup"><span data-stu-id="b5e10-120">Troubleshooting</span></span>

<span data-ttu-id="b5e10-121">**어떤 GPU가 있는지 확인하려면 어떻게 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="b5e10-121">**How do I know what GPU I have?**</span></span>

<span data-ttu-id="b5e10-122">제공된 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-122">Follow instructions provided:</span></span>

1. <span data-ttu-id="b5e10-123">바탕 화면을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-123">Right-click on desktop</span></span>
1. <span data-ttu-id="b5e10-124">팝업 창에 “NVIDIA 제어판” 또는 “NVIDIA 디스플레이”가 표시되면 NVIDIA GPU가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-124">If you see "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window, you have an NVIDIA GPU</span></span>
1. <span data-ttu-id="b5e10-125">팝업 창에서 “NVIDIA 제어판” 또는 “NVIDIA 디스플레이”를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-125">Click on "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window</span></span>
1. <span data-ttu-id="b5e10-126">“그래픽 카드 정보”를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-126">Look at "Graphics Card Information"</span></span>
1. <span data-ttu-id="b5e10-127">NVIDIA GPU 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-127">You will see the name of your NVIDIA GPU</span></span>

<span data-ttu-id="b5e10-128">**NVIDIA 제어판은 표시되지 않지만(또는 열지 못함) NVIDIA GPU가 있는 것을 알고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b5e10-128">**I don't see NVIDIA Control Panel (or it fails to open) but I know I have an NVIDIA GPU.**</span></span>

1. <span data-ttu-id="b5e10-129">디바이스 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-129">Open Device Manager</span></span>
1. <span data-ttu-id="b5e10-130">디스플레이 어댑터를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-130">Look at Display adapters</span></span>
1. <span data-ttu-id="b5e10-131">GPU에 적합한 [드라이버](https://www.nvidia.com/drivers)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e10-131">Install appropriate [driver](https://www.nvidia.com/drivers) for your GPU.</span></span>
