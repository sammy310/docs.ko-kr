---
title: '자습서: Model Builder를 사용하여 이미지에서 개체 검색'
description: 이 자습서에서는 ML.NET Model Builder 및 Azure ML을 사용하여 이미지에서 정지 표지판을 검색하는 개체 검색 모델을 빌드하는 방법을 보여 줍니다.
author: briacht
ms.author: brachtma
ms.date: 03/12/2021
ms.topic: tutorial
ms.custom: mlnet-tooling
ms.openlocfilehash: 21b672b84c7f55578a76459fa9f02aca3455d719
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104658385"
---
# <a name="tutorial-detect-stop-signs-in-images-with-model-builder"></a><span data-ttu-id="9a26c-103">자습서: Model Builder를 사용하여 이미지에서 정지 표지판 검색</span><span class="sxs-lookup"><span data-stu-id="9a26c-103">Tutorial: Detect stop signs in images with Model Builder</span></span>

<span data-ttu-id="9a26c-104">ML.NET Model Builder 및 Azure ML을 사용하여 이미지에서 정지 표지판을 찾는 개체 검색 모델을 빌드하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-104">Learn how to build an object detection model using ML.NET Model Builder and Azure ML to detect and locate stop signs in images.</span></span>

<span data-ttu-id="9a26c-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="9a26c-106">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="9a26c-106">Prepare and understand the data</span></span>
> - <span data-ttu-id="9a26c-107">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="9a26c-107">Choose the scenario</span></span>
> - <span data-ttu-id="9a26c-108">학습 환경 선택</span><span class="sxs-lookup"><span data-stu-id="9a26c-108">Choose the training environment</span></span>
> - <span data-ttu-id="9a26c-109">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="9a26c-109">Load the data</span></span>
> - <span data-ttu-id="9a26c-110">모델 학습</span><span class="sxs-lookup"><span data-stu-id="9a26c-110">Train the model</span></span>
> - <span data-ttu-id="9a26c-111">모델 평가</span><span class="sxs-lookup"><span data-stu-id="9a26c-111">Evaluate the model</span></span>
> - <span data-ttu-id="9a26c-112">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="9a26c-112">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="9a26c-113">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-113">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9a26c-114">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a26c-114">Prerequisites</span></span>

<span data-ttu-id="9a26c-115">필수 구성 요소 및 설치 지침 목록을 보려면 [모델 작성기 설치 가이드](../how-to-guides/install-model-builder.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="9a26c-115">For a list of prerequisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="model-builder-object-detection-overview"></a><span data-ttu-id="9a26c-116">Model Builder 개체 검색 개요</span><span class="sxs-lookup"><span data-stu-id="9a26c-116">Model Builder object detection overview</span></span>

<span data-ttu-id="9a26c-117">개체 검색은 컴퓨터 비전 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-117">Object detection is a computer vision problem.</span></span> <span data-ttu-id="9a26c-118">개체 검색은 이미지 분류와 밀접하게 관련된 반면, 보다 세부적인 규모에서 이미지 분류를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-118">While closely related to image classification, object detection performs image classification at a more granular scale.</span></span> <span data-ttu-id="9a26c-119">개체 검색에서는 이미지에서 엔터티 찾기 _및_ 분류를 둘 다 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-119">Object detection both locates _and_ categorizes entities within images.</span></span> <span data-ttu-id="9a26c-120">이미지에 서로 다른 유형의 개체가 여러 개 포함되어 있는 경우 개체 검색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-120">Use object detection when images contain multiple objects of different types.</span></span>

![이미지 분류 및 개체 분류를 보여 주는 스크린샷](./media/object-detection-onnx/img-classification-obj-detection.PNG)

<span data-ttu-id="9a26c-122">개체 검색의 몇 가지 사용 사례는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-122">Some use cases for object detection include:</span></span>

- <span data-ttu-id="9a26c-123">자동 주행 자동차</span><span class="sxs-lookup"><span data-stu-id="9a26c-123">Self-Driving Cars</span></span>
- <span data-ttu-id="9a26c-124">Robotics</span><span class="sxs-lookup"><span data-stu-id="9a26c-124">Robotics</span></span>
- <span data-ttu-id="9a26c-125">얼굴 감지</span><span class="sxs-lookup"><span data-stu-id="9a26c-125">Face Detection</span></span>
- <span data-ttu-id="9a26c-126">작업 영역 안전성</span><span class="sxs-lookup"><span data-stu-id="9a26c-126">Workplace Safety</span></span>
- <span data-ttu-id="9a26c-127">개체 수 계산</span><span class="sxs-lookup"><span data-stu-id="9a26c-127">Object Counting</span></span>
- <span data-ttu-id="9a26c-128">활동 인식</span><span class="sxs-lookup"><span data-stu-id="9a26c-128">Activity Recognition</span></span>

<span data-ttu-id="9a26c-129">이 샘플은 Model Builder로 빌드된 기계 학습 모델을 사용하여 이미지에서 정지 표지판을 검색하는 C# .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-129">This sample creates a C# .NET Core console application that detects stop signs in images using a machine learning model built with Model Builder.</span></span> <span data-ttu-id="9a26c-130">[dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/ObjectDetection_StopSigns) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-130">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/ObjectDetection_StopSigns) GitHub repository.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="9a26c-131">데이터 준비 및 이해</span><span class="sxs-lookup"><span data-stu-id="9a26c-131">Prepare and understand the data</span></span>

<span data-ttu-id="9a26c-132">정지 표지판 데이터 세트는 [Unsplash](https://unsplash.com/)에서 다운로드한 50개 이미지로 구성되며 각 이미지에는 하나 이상의 정지 표지판이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-132">The Stop Sign dataset consists of 50 images downloaded from [Unsplash](https://unsplash.com/), each of which contain at least one stop sign.</span></span>

<span data-ttu-id="9a26c-133">가장 먼저 할 일은 이미지에 주석을 추가하거나 각 이미지에서 정지 표지판 주위에 경계 상자를 그리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-133">The first thing you need to do is annotate your images, or draw bounding boxes around the stop signs in each image.</span></span> <span data-ttu-id="9a26c-134">이 자습서에서는 [VoTT](https://github.com/microsoft/VoTT)라는 도구를 사용하여 이미지에 주석을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-134">In this tutorial, you will annotate your images with a tool called [VoTT](https://github.com/microsoft/VoTT).</span></span>

> <span data-ttu-id="9a26c-135">아래의 데이터 레이블 지정 단계를 건너뛰려면 [이 버전의 데이터 세트를 다운로드](https://aka.ms/mlnet-object-detection-tutorial-assets)하여 [콘솔 애플리케이션 만들기](object-detection-model-builder.md#create-a-console-application)로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-135">If you want to skip the data labeling steps below, you can [download this version of the dataset](https://aka.ms/mlnet-object-detection-tutorial-assets) and skip to [Create a console application](object-detection-model-builder.md#create-a-console-application).</span></span>

### <a name="create-a-new-vott-project"></a><span data-ttu-id="9a26c-136">새 VoTT 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9a26c-136">Create a new VoTT project</span></span>

1. <span data-ttu-id="9a26c-137">50개 정지 표지판 이미지의 [데이터 세트를 다운로드](https://aka.ms/mlnet-object-detection-tutorial-dataset)하고 압축을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-137">[Download the dataset](https://aka.ms/mlnet-object-detection-tutorial-dataset) of 50 stop sign images and unzip.</span></span>
1. <span data-ttu-id="9a26c-138">[VoTT](https://github.com/Microsoft/VoTT/releases)(시각적 개체 태그 지정 도구)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-138">[Download VoTT](https://github.com/Microsoft/VoTT/releases) (Visual Object Tagging Tool).</span></span>
1. <span data-ttu-id="9a26c-139">VoTT를 열고 **새 프로젝트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-139">Open VoTT and select **New Project**.</span></span>

    ![VoTT 홈 화면](./media/object-detection-model-builder/vott.png)

1. <span data-ttu-id="9a26c-141">**프로젝트 설정** 에서 **표시 이름** 을 ‘StopSignObjDetection’으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-141">In **Project Settings**, change the **Display Name** to "StopSignObjDetection".</span></span>
1. <span data-ttu-id="9a26c-142">**보안 토큰** 을 새 보안 토큰 생성으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-142">Change the **Security Token** to *Generate New Security Token*.</span></span>
1. <span data-ttu-id="9a26c-143">**원본 연결** 옆에서 **연결 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-143">Next to **Source Connection**, select **Add Connection**.</span></span>
1. <span data-ttu-id="9a26c-144">**연결 설정** 에서 원본 연결의 **표시 이름** 을 ‘StopSignImages’로 변경하고 로컬 파일 시스템을 **공급자** 로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-144">In **Connection Settings**, change the **Display Name** for the source connection to "StopSignImages", and select *Local File System* as the **Provider**.</span></span> <span data-ttu-id="9a26c-145">**폴더 경로** 에서 50개 학습 이미지가 들어 있는 *Stop-Signs* 폴더를 선택한 다음 **연결 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-145">For the **Folder Path**, select the *Stop-Signs* folder which contains the 50 training images, and then select **Save Connection**.</span></span>

    ![VoTT 새 연결 대화 상자](./media/object-detection-model-builder/vott-new-connection.png)

1. <span data-ttu-id="9a26c-147">**프로젝트 설정** 에서 **원본 연결** 을 *StopSignImages*(방금 만든 연결)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-147">In **Project Settings**, change the **Source Connection** to *StopSignImages* (the connection you just created).</span></span>
1. <span data-ttu-id="9a26c-148">**대상 연결** 도 *StopSignImages* 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-148">Change the **Target Connection** to *StopSignImages* as well.</span></span> <span data-ttu-id="9a26c-149">이제 **프로젝트 설정** 은 다음과 유사하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-149">Your **Project Settings** should now look similar to this screenshot:</span></span>

    ![VoTT 프로젝트 설정 대화 상자](./media/object-detection-model-builder/vott-new-project.png)

1. <span data-ttu-id="9a26c-151">**프로젝트 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-151">Select **Save Project**.</span></span>

### <a name="add-tag-and-label-images"></a><span data-ttu-id="9a26c-152">태그 추가 및 이미지 레이블링</span><span class="sxs-lookup"><span data-stu-id="9a26c-152">Add tag and label images</span></span>

<span data-ttu-id="9a26c-153">이제 왼쪽에 모든 학습 이미지의 미리 보기 이미지가 표시되고, 가운데에 선택한 이미지의 미리 보기가 표시되고, 오른쪽에 **태그** 열이 표시된 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-153">You should now see a window with preview images of all the training images on the left, a preview of the selected image in the middle, and a **Tags** column on the right.</span></span> <span data-ttu-id="9a26c-154">이 화면은 **태그 편집기** 입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-154">This screen is the **Tags editor**.</span></span>

1. <span data-ttu-id="9a26c-155">**태그** 도구 모음에서 첫 번째(더하기 모양) 아이콘을 선택하여 새 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-155">Select the first (plus-shaped) icon in the **Tags** toolbar to add a new tag.</span></span>

    ![VoTT 새 태그 아이콘](./media/object-detection-model-builder/vott-new-tag-icon.png)

1. <span data-ttu-id="9a26c-157">태그 이름을 ‘Stop-Sign’으로 지정하고 키보드에서 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-157">Name the tag "Stop-Sign" and hit <kbd>Enter</kbd> on your keyboard.</span></span>

    ![VoTT 새 태그](./media/object-detection-model-builder/vott-new-tag.png)

1. <span data-ttu-id="9a26c-159">클릭하고 끌어 이미지의 각 정지 표지판 주위에 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-159">Click and drag to draw a rectangle around each stop sign in the image.</span></span> <span data-ttu-id="9a26c-160">커서를 사용하여 사각형을 그릴 수 없는 경우 위쪽의 도구 모음에서 **사각형 그리기** 도구를 선택하거나 바로 가기 키 <kbd>R</kbd>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-160">If the cursor does not let you draw a rectangle, try selecting the **Draw Rectangle** tool from the toolbar on the top, or use the keyboard shortcut <kbd>R</kbd>.</span></span>
1. <span data-ttu-id="9a26c-161">사각형을 그린 후 이전 단계에서 만든 **Stop-Sign** 태그를 선택하여 경계 상자에 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-161">After drawing your rectangle, select the **Stop-Sign** tag that you created in the previous steps to add the tag to the bounding box.</span></span>
1. <span data-ttu-id="9a26c-162">데이터 세트의 다음 이미지에 대한 미리 보기 이미지를 클릭하고 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-162">Click on the preview image for the next image in the dataset and repeat this process.</span></span>
1. <span data-ttu-id="9a26c-163">모든 이미지의 모든 정지 표지판에 대해 3~4단계를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-163">Continue steps 3-4 for every stop sign in every image.</span></span>

    ![VoTT 이미지 주석 달기](./media/object-detection-model-builder/vott-annotating.gif)

### <a name="export-your-vott-json"></a><span data-ttu-id="9a26c-165">VoTT JSON 내보내기</span><span class="sxs-lookup"><span data-stu-id="9a26c-165">Export your VoTT JSON</span></span>

<span data-ttu-id="9a26c-166">모든 학습 이미지에 레이블을 지정한 후에는 Model Builder에서 학습에 사용할 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-166">Once you have labeled all of your training images, you can export the file that will be used by Model Builder for training.</span></span>

1. <span data-ttu-id="9a26c-167">왼쪽 도구 모음의 네 번째 아이콘(상자 안에 대각선 화살표가 있는 모양)을 선택하여 **내보내기 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-167">Select the fourth icon in the left toolbar (the one with the diagonal arrow in a box) to go to the **Export Settings**.</span></span>
1. <span data-ttu-id="9a26c-168">**공급자** 를 *VoTT JSON* 으로 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-168">Leave the **Provider** as *VoTT JSON*.</span></span>
1. <span data-ttu-id="9a26c-169">**자산 상태** 를 태그가 지정된 자산만으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-169">Change the **Asset State** to *Only tagged Assets*.</span></span>
1. <span data-ttu-id="9a26c-170">**이미지 포함** 을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-170">Uncheck **Include Images**.</span></span> <span data-ttu-id="9a26c-171">이미지를 포함시킬 경우 학습 이미지가 생성되는 내보내기 폴더로 복사됩니다. 이는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-171">If you include the images, then the training images will be copied to the export folder that is generated, which is not necessary.</span></span>
1. <span data-ttu-id="9a26c-172">**내보내기 설정 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-172">Select **Save Export Settings**.</span></span>

    ![VoTT 내보내기 설정](./media/object-detection-model-builder/vott-export.png)

1. <span data-ttu-id="9a26c-174">**태그 편집기** 로 돌아갑니다(왼쪽 도구 모음에서 리본 모양의 두 번째 아이콘).</span><span class="sxs-lookup"><span data-stu-id="9a26c-174">Go back to the **Tags editor** (the second icon in the left toolbar shaped like a ribbon).</span></span> <span data-ttu-id="9a26c-175">상단 도구 모음에서 **프로젝트 내보내기** 아이콘(상자 안에 화살표가 있는 모양의 마지막 아이콘)을 선택하거나 바로 가기 키 <kbd>Ctrl</kbd>+<kbd>E</kbd>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-175">In the top toolbar, select the **Export Project** icon (the last icon shaped like an arrow in a box), or use the keyboard shortcut <kbd>Ctrl</kbd>+<kbd>E</kbd>.</span></span>

    ![VoTT 내보내기 단추](./media/object-detection-model-builder/vott-export-button.png)

<span data-ttu-id="9a26c-177">이 내보내기는 *Stop-Sign-Images* 폴더에 *vott-json-export* 라는 새 폴더를 만들고 그 안에 *StopSignObjDetection-export* 라는 JSON 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-177">This export will create a new folder called *vott-json-export* in your *Stop-Sign-Images* folder and will generate a JSON file named *StopSignObjDetection-export* in that new folder.</span></span> <span data-ttu-id="9a26c-178">Model Builder에서 개체 검색 모델을 학습시키는 다음 단계에서 이 JSON 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-178">You will use this JSON file in the next steps for training an object detection model in Model Builder.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="9a26c-179">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="9a26c-179">Create a console application</span></span>

1. <span data-ttu-id="9a26c-180">Visual Studio에서 *StopSignDetection* 이라는 **C# .NET Core 콘솔 애플리케이션** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-180">In Visual Studio, create a **C# .NET Core console application** called *StopSignDetection*.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="9a26c-181">시나리오 선택</span><span class="sxs-lookup"><span data-stu-id="9a26c-181">Choose a scenario</span></span>

1. <span data-ttu-id="9a26c-182">**솔루션 탐색기** 에서 *StopSignDetection* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **기계 학습** 을 선택하여 Model Builder UI를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-182">In **Solution Explorer**, right-click the *StopSignDetection* project, and select **Add** > **Machine Learning** to open the Model Builder UI.</span></span>
1. <span data-ttu-id="9a26c-183">이 샘플에서는 시나리오가 개체 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-183">For this sample, the scenario is object detection.</span></span> <span data-ttu-id="9a26c-184">Model Builder의 **시나리오** 단계에서 **개체 검색** 시나리오를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-184">In the **Scenario** step of Model Builder, select the **Object Detection** scenario.</span></span>

![Visual Studio의 모델 작성기 마법사](./media/object-detection-model-builder/obj-det-scenario.png)

> <span data-ttu-id="9a26c-186">시나리오 목록에 개체 감지가 표시되지 않는 경우 [Model Builder의 버전을 업데이트](https://marketplace.visualstudio.com/items?itemName=MLNET.07)해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-186">If you don't see *Object Detection* in the list of scenarios, you may need to [update your version of Model Builder](https://marketplace.visualstudio.com/items?itemName=MLNET.07).</span></span>

## <a name="choose-the-training-environment"></a><span data-ttu-id="9a26c-187">학습 환경 선택</span><span class="sxs-lookup"><span data-stu-id="9a26c-187">Choose the training environment</span></span>

<span data-ttu-id="9a26c-188">현재 Model Builder는 Azure Machine Learning을 사용하는 개체 검색 모델 학습만 지원하므로 Azure 학습 환경이 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-188">Currently, Model Builder supports training object detection models with Azure Machine Learning only, so the Azure training environment is selected by default.</span></span>

![Azure 학습 환경 선택](./media/object-detection-model-builder/obj-det-environment.png)

<span data-ttu-id="9a26c-190">Azure ML을 사용하여 모델을 학습시키려면 Model Builder에서 Azure ML 실험을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-190">To train a model using Azure ML, you must create an Azure ML experiment from Model Builder.</span></span>

<span data-ttu-id="9a26c-191">**Azure ML 실험** 은 하나 이상의 기계 학습 학습 실행에 대한 구성 및 결과를 캡슐화하는 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-191">An **Azure ML experiment** is a resource that encapsulates the configuration and results for one or more machine learning training runs.</span></span>

<span data-ttu-id="9a26c-192">Azure ML 실험을 만들려면 먼저 Azure에서 환경을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-192">To create an Azure ML experiment, you first need to configure your environment in Azure.</span></span> <span data-ttu-id="9a26c-193">실험을 실행하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-193">An experiment needs the following to run:</span></span>

- <span data-ttu-id="9a26c-194">Azure 구독</span><span class="sxs-lookup"><span data-stu-id="9a26c-194">An Azure subscription</span></span>
- <span data-ttu-id="9a26c-195">**작업 영역**: 학습 실행의 일부로 생성된 모든 Azure ML 리소스 및 아티팩트에 대한 중앙 위치를 제공하는 Azure ML 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-195">A **workspace**: an Azure ML resource that provides a central place for all Azure ML resources and artifacts created as part of a training run.</span></span>
- <span data-ttu-id="9a26c-196">**컴퓨팅**: Azure Machine Learning 컴퓨팅은 학습에 사용되는 클라우드 기반 Linux VM입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-196">A **compute**: an Azure Machine Learning compute is a cloud-based Linux VM used for training.</span></span> <span data-ttu-id="9a26c-197">[Model Builder에서 지원하는 컴퓨팅 형식](../resources/azure-training-concepts-model-builder.md#what-is-an-azure-machine-learning-compute)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9a26c-197">Learn more about [compute types supported by Model Builder](../resources/azure-training-concepts-model-builder.md#what-is-an-azure-machine-learning-compute).</span></span>

### <a name="set-up-an-azure-ml-workspace"></a><span data-ttu-id="9a26c-198">Azure ML 작업 영역 설정</span><span class="sxs-lookup"><span data-stu-id="9a26c-198">Set up an Azure ML workspace</span></span>

<span data-ttu-id="9a26c-199">환경을 구성하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-199">To configure your environment:</span></span>

1. <span data-ttu-id="9a26c-200">**작업 영역 설정** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-200">Select the **Set up workspace** button.</span></span>
1. <span data-ttu-id="9a26c-201">**새 실험 만들기** 대화 상자에서 Azure 구독을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-201">In the **Create new experiment** dialog, select your Azure subscription.</span></span>
1. <span data-ttu-id="9a26c-202">기존 작업 영역을 선택하거나 새 Azure ML 작업 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-202">Select an existing workspace or create a new Azure ML workspace.</span></span>

    <span data-ttu-id="9a26c-203">새 작업 영역을 만들면 다음 리소스가 프로비저닝됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-203">When you create a new workspace, the following resources are provisioned:</span></span>

    - <span data-ttu-id="9a26c-204">Azure Machine Learning 작업 영역</span><span class="sxs-lookup"><span data-stu-id="9a26c-204">Azure Machine Learning workspace</span></span>
    - <span data-ttu-id="9a26c-205">Azure Storage</span><span class="sxs-lookup"><span data-stu-id="9a26c-205">Azure Storage</span></span>
    - <span data-ttu-id="9a26c-206">Azure Application Insights</span><span class="sxs-lookup"><span data-stu-id="9a26c-206">Azure Application Insights</span></span>
    - <span data-ttu-id="9a26c-207">Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="9a26c-207">Azure Container Registry</span></span>
    - <span data-ttu-id="9a26c-208">Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9a26c-208">Azure Key Vault</span></span>

    <span data-ttu-id="9a26c-209">그러므로 이 프로세스에 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-209">As a result, this process may take a few minutes.</span></span>

1. <span data-ttu-id="9a26c-210">기존 컴퓨팅을 선택하거나 새 Azure ML 컴퓨팅을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-210">Select an existing compute or create a new Azure ML compute.</span></span> <span data-ttu-id="9a26c-211">이 프로세스에 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-211">This process may take a few minutes.</span></span>
1. <span data-ttu-id="9a26c-212">기본 실험 이름은 그대로 두고 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-212">Leave the default experiment name and select **Create**.</span></span>

    ![Azure 작업 영역 설정 대화 상자](./media/object-detection-model-builder/azure-dialog.png)

<span data-ttu-id="9a26c-214">처음 실험이 만들어지고 작업 영역에 실험 이름이 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-214">The first experiment is created, and the experiment name is registered in the workspace.</span></span> <span data-ttu-id="9a26c-215">모든 후속 실행(같은 실험 이름을 사용하는 경우)은 같은 실험의 일부로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-215">Any subsequent runs (if the same experiment name is used ) are logged as part of the same experiment.</span></span> <span data-ttu-id="9a26c-216">같은 실험 이름이 사용되지 않으면 새 실험이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-216">Otherwise, a new experiment is created.</span></span>

<span data-ttu-id="9a26c-217">구성에 만족하는 경우 Model Builder에서 **다음 단계** 단추를 선택하여 **데이터** 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-217">If you’re satisfied with your configuration, select the **Next step** button in Model Builder to move to the **Data** step.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="9a26c-218">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="9a26c-218">Load the data</span></span>

<span data-ttu-id="9a26c-219">Model Builder의 **데이터** 단계에서는 학습 데이터 세트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-219">In the **Data** step of Model Builder, you will select your training dataset.</span></span>

><span data-ttu-id="9a26c-220">Model Builder는 현재 VoTT에서 생성된 JSON 형식만 허용하지만 향후 더 많은 형식에 대한 지원을 추가할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-220">Model Builder currently only accepts the format of JSON generated by VoTT, but the team plans to add support for more formats in the future.</span></span> <span data-ttu-id="9a26c-221">Model Builder가 지원하기를 희망하는 개체 검색용 데이터 세트 형식이 있는 경우 [GitHub](https://github.com/dotnet/machinelearning-modelbuilder/issues/new?assignees=&labels=&template=data_suggestion.md&title=)에 피드백을 남겨주세요.</span><span class="sxs-lookup"><span data-stu-id="9a26c-221">If there is a dataset format for object detection that you’d like to see supported in Model Builder, leave your feedback on [GitHub](https://github.com/dotnet/machinelearning-modelbuilder/issues/new?assignees=&labels=&template=data_suggestion.md&title=).</span></span>

1. <span data-ttu-id="9a26c-222">**폴더 선택** 텍스트 상자 옆에 있는 단추를 선택하고 파일 탐색기를 사용하여 *Stop-Signs/vott-json-export* 디렉터리에 있는 `StopSignObjDetection-export.json`을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-222">Select the button next to the **Select a folder** text box and use the File Explorer to find the `StopSignObjDetection-export.json` which should be located in the *Stop-Signs/vott-json-export* directory.</span></span>

    ![Model Builder 데이터 단계](./media/object-detection-model-builder/obj-det-data.png)

1. <span data-ttu-id="9a26c-224">**데이터 미리 보기** 에서 데이터가 올바르게 표시되면 **다음 단계** 를 선택하여 **학습** 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-224">If your data looks correct in the **Data Preview**, select **Next step** to move on to the **Train** step.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="9a26c-225">모델 학습</span><span class="sxs-lookup"><span data-stu-id="9a26c-225">Train the model</span></span>

<span data-ttu-id="9a26c-226">다음 단계는 모델 학습입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-226">The next step is to train your model.</span></span>

<span data-ttu-id="9a26c-227">Model Builder **학습** 화면에서 **학습 시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-227">In the Model Builder **Train** screen, select the **Start training** button.</span></span>

<span data-ttu-id="9a26c-228">이제 데이터가 Azure Storage에 업로드되고 Azure ML에서 학습 프로세스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-228">At this point, your data is uploaded to Azure Storage and the training process begins in Azure ML.</span></span>

><span data-ttu-id="9a26c-229">학습 프로세스에는 어느 정도 시간이 걸리며, 선택한 컴퓨팅 크기 및 데이터의 양에 따라 걸리는 시간이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-229">The training process takes some time, and the amount of time may vary depending on the size of compute selected as well as the amount of data.</span></span> <span data-ttu-id="9a26c-230">Azure에서 처음 모델을 학습시킬 때는 리소스를 프로비저닝해야 하므로 학습 시간이 약간 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-230">The first time a model is trained in Azure, you can expect a slightly longer training time because resources have to be provisioned.</span></span> <span data-ttu-id="9a26c-231">이 50개 이미지 샘플의 경우 학습에 16분 정도 걸렸습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-231">For this sample of 50 images, training took about 16 minutes.</span></span>

<span data-ttu-id="9a26c-232">Visual Studio에서 **Azure Portal에서 현재 실행 모니터링** 링크를 선택하여 Azure Machine Learning 포털에서 실행의 진행률을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-232">You can track the progress of your runs in the Azure Machine Learning portal by selecting the **Monitor current run in Azure portal** link in Visual Studio.</span></span>

<span data-ttu-id="9a26c-233">학습이 완료되면 **다음 단계** 단추를 선택하여 **평가** 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-233">Once training is complete, select the **Next step** button to move on to the **Evaluate** step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="9a26c-234">모델 평가</span><span class="sxs-lookup"><span data-stu-id="9a26c-234">Evaluate the model</span></span>

<span data-ttu-id="9a26c-235">평가 화면에서 모델 정확도를 포함하여 학습 프로세스의 결과에 대한 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-235">In the Evaluate screen, you get an overview of the results from the training process, including the model accuracy.</span></span>

![Model Builder 평가 단계](./media/object-detection-model-builder/obj-det-evaluate.png)

<span data-ttu-id="9a26c-237">이 경우 정확도가 100%로 표시됩니다. 즉, 데이터 세트에 이미지가 너무 적어서 모델이 과잉 맞춤된 것으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-237">In this case, the accuracy says 100%, which means that the model is more than likely *overfit* due to too few images in the dataset.</span></span>

<span data-ttu-id="9a26c-238">**모델 사용해 보기** 환경을 사용하여 모델이 예상대로 작동하는지 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-238">You can use the **Try your model** experience to quickly check whether your model is performing as expected.</span></span>

<span data-ttu-id="9a26c-239">**이미지 찾아보기** 를 선택하고 테스트 이미지를 제공합니다. 이러한 이미지는 모델이 학습에 사용하지 않은 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-239">Select **Browse an image** and provide a test image, preferably one that the model did not use as part of training.</span></span>

![Model Builder 모델 사용해 보기](./media/object-detection-model-builder/obj-det-try-model.png)

<span data-ttu-id="9a26c-241">검색된 각 경계 상자에 표시되는 점수는 검색된 개체의 **신뢰도** 를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-241">The score shown on each detected bounding box indicates the **confidence** of the detected object.</span></span> <span data-ttu-id="9a26c-242">예를 들어 위의 스크린샷에서 정지 표지판 주위의 경계 상자 점수는 모델이 검색된 개체가 정지 표지판임을 99% 확신하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-242">For instance, in the screenshot above, the score on the bounding box around the stop sign indicates that the model is 99% sure that the detected object is a stop sign.</span></span>

<span data-ttu-id="9a26c-243">임계값 슬라이더를 사용하여 높이거나 낮출 수 있는 **점수 임계값** 은 해당 점수에 따라 검색된 개체를 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-243">The **Score threshold**, which can be increased or decreased with the threshold slider, will add and remove detected objects based on their scores.</span></span> <span data-ttu-id="9a26c-244">예를 들어 임계값이 .51인 경우 모델은 신뢰도 점수가 .51 이상인 개체만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-244">For instance, if the threshold is .51, then the model will only show objects that have a confidence score of .51 or above.</span></span> <span data-ttu-id="9a26c-245">임계값을 높이면 검색된 개체가 줄어듭니다. 임계값을 낮추면 검색된 개체가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-245">As you increase the threshold, you will see less detected objects, and as you decrease the threshold, you will see more detected objects.</span></span>

<span data-ttu-id="9a26c-246">정확도 메트릭이 만족스럽지 않을 경우 모델 정확도를 개선하기 위한 간단한 방법 하나는 더 많은 데이터를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-246">If you're not satisfied with your accuracy metrics, one easy way to try to improve model accuracy is to use more data.</span></span> <span data-ttu-id="9a26c-247">그렇지 않으면 **다음 단계** 링크를 선택하여 Model Builder의 **코드** 단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-247">Otherwise, select the **Next step** link to move on to the **Code** step in Model Builder.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="9a26c-248">코드를 추가하여 예측하기</span><span class="sxs-lookup"><span data-stu-id="9a26c-248">Add the code to make predictions</span></span>

<span data-ttu-id="9a26c-249">학습 프로세스의 결과로 두 개의 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-249">Two projects are created as a result of the training process.</span></span>

- <span data-ttu-id="9a26c-250">*StopSignDetectionML.ConsoleApp*: 모델 학습 코드 및 샘플 소비 코드가 포함된 C# .NET Core 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-250">*StopSignDetectionML.ConsoleApp*: A C# .NET Core Console application that contains the model training code and sample consumption code.</span></span>
- <span data-ttu-id="9a26c-251">*StopSignDetectionML.Model*: 입력 및 출력 모델 데이터의 스키마를 정의하는 데이터 모델, 학습 중 가장 성능이 뛰어난 모델의 저장된 버전, 예측을 위한 `ConsumeModel`이라는 도우미 클래스를 포함하는 .NET Standard 클래스 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-251">*StopSignDetectionML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data, the saved version of the best performing model during training, and a helper class called `ConsumeModel` to make predictions.</span></span>

1. <span data-ttu-id="9a26c-252">Model Builder의 코드 단계에서 **프로젝트 추가** 를 선택하여 자동 생성된 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-252">In the code step of Model Builder, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="9a26c-253">*StopSignDetection* 프로젝트에서 *Program.cs* 파일을 열고 다음 using 문을 파일 맨 위에 추가하여 *StopSignDetectionML.Model* 프로젝트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-253">Open the *Program.cs* file in the *StopSignDetection* project, and add the following using statement at the top of the file to reference the *StopSignDetectionML.Model* project:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L2)]

1. <span data-ttu-id="9a26c-254">다음 [테스트 이미지](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/test-image1.jpeg)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-254">Download the following [test image](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/test-image1.jpeg).</span></span>
1. <span data-ttu-id="9a26c-255">애플리케이션의 `Main` 메서드 내에서 `ImageSource` 속성을 테스트 이미지의 filepath로 설정하여 `ModelInput` 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-255">Create a new instance of the `ModelInput` class with the `ImageSource` property set to the filepath of your test image inside the `Main` method of your application.</span></span> <span data-ttu-id="9a26c-256">‘Hello World’ 문을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-256">Replace the "Hello World" statement with the following code:</span></span>

    [!code-csharp [InputData](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L10-L15)]

1. <span data-ttu-id="9a26c-257">`ConsumeModel` 클래스의 `Predict` 메서드를 사용하여 학습된 모델을 로드하고, 모델에 대한 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만들고, 새 데이터에 대한 예측을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-257">Use the `Predict` method from the `ConsumeModel` class to load the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model, and make predictions on new data.</span></span> <span data-ttu-id="9a26c-258">`ModelInput` 문에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-258">Add the following code below the `ModelInput` statement:</span></span>

    [!code-csharp [Prediction](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L15)]

1. <span data-ttu-id="9a26c-259">다음 코드를 추가하여 레이블, 좌표, 점수를 포함한 예측의 출력을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-259">Print out the Prediction's output, including the label, coordinates, and score by adding the following code:</span></span>

    [!code-csharp [PrintResults](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L17-L18)]

1. <span data-ttu-id="9a26c-260">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-260">Run the application.</span></span>

    <span data-ttu-id="9a26c-261">프로그램에서 생성된 출력은 아래 코드 조각과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-261">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Boxes:
    
    Top: 89.453415, Left: 481.95343, Right: 724.8073, Bottom: 388.32385, Label: Stop-Sign, Score: 0.99539465
    ```

<span data-ttu-id="9a26c-262">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="9a26c-262">Congratulations!</span></span> <span data-ttu-id="9a26c-263">Model Builder를 사용하여 이미지에서 정지 표지판을 검색하는 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-263">You've successfully built a machine learning model to detect stop signs in images using Model Builder.</span></span> <span data-ttu-id="9a26c-264">[dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/ObjectDetection_StopSigns) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a26c-264">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/ObjectDetection_StopSigns) GitHub repository.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a26c-265">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9a26c-265">Additional resources</span></span>

<span data-ttu-id="9a26c-266">이 자습서에서 언급한 항목에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a26c-266">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="9a26c-267">모델 작성기 시나리오</span><span class="sxs-lookup"><span data-stu-id="9a26c-267">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenario)
- [<span data-ttu-id="9a26c-268">ML.NET에서 ONNX를 사용하여 개체 검색</span><span class="sxs-lookup"><span data-stu-id="9a26c-268">Object Detection using ONNX in ML.NET</span></span>](object-detection-onnx.md)
