---
title: 모델 작성기 Azure 학습 리소스
description: Azure Machine Learning에 대한 리소스 가이드
ms.topic: reference
ms.date: 06/01/2020
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: d9eb5560ef33f8f80dbe53e17087c606a8697378
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289475"
---
# <a name="model-builder-azure-training-resources"></a><span data-ttu-id="bcc18-103">모델 작성기 Azure 학습 리소스</span><span class="sxs-lookup"><span data-stu-id="bcc18-103">Model Builder Azure Training Resources</span></span>

<span data-ttu-id="bcc18-104">다음은 모델 작성기를 사용하여 Azure에서 모델을 학습시키는 데 사용되는 리소스에 대해 자세히 알아보는 데 유용한 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-104">The following is a guide to help you learn more about resources used to train models in Azure with Model Builder.</span></span>

## <a name="what-is-an-azure-machine-learning-experiment"></a><span data-ttu-id="bcc18-105">Azure Machine Learning 실험이란?</span><span class="sxs-lookup"><span data-stu-id="bcc18-105">What is an Azure Machine Learning experiment?</span></span>

<span data-ttu-id="bcc18-106">Azure Machine Learning 실험은 Azure에서 모델 작성기 학습을 실행하기 전에 만들어야 하는 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-106">An Azure Machine Learning experiment is a resource that needs to be created before running Model Builder training on Azure.</span></span>

<span data-ttu-id="bcc18-107">실험은 하나 이상의 기계 학습 실행에 대한 구성 및 결과를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-107">The experiment encapsulates the configuration and results for one or more machine learning training runs.</span></span> <span data-ttu-id="bcc18-108">실험은 특정 작업 영역에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-108">Experiments belong to a specific workspace.</span></span> <span data-ttu-id="bcc18-109">처음 실험을 만들면 해당 이름이 작업 영역에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-109">The first time an experiment is created, its name is registered in the workspace.</span></span> <span data-ttu-id="bcc18-110">모든 후속 실행(같은 실험 이름이 사용되는 경우)은 같은 실험의 일부로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-110">Any subsequent runs - if the same experiment name is used - are logged as part of the same experiment.</span></span> <span data-ttu-id="bcc18-111">같은 실험 이름이 사용되지 않으면 새 실험이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-111">Otherwise, a new experiment is created.</span></span>

## <a name="what-is-an-azure-machine-learning-workspace"></a><span data-ttu-id="bcc18-112">Azure Machine Learning 작업 영역이란?</span><span class="sxs-lookup"><span data-stu-id="bcc18-112">What is an Azure Machine Learning workspace?</span></span>

<span data-ttu-id="bcc18-113">작업 영역은 학습 실행의 일부로 생성된 모든 Azure Machine Learning 리소스 및 아티팩트에 대한 중앙 환경을 제공하는 Azure Machine Learning 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-113">A workspace is an Azure Machine Learning resource that provides a central place for all Azure Machine Learning resources and artifacts created as part of training run.</span></span>

<span data-ttu-id="bcc18-114">Azure Machine Learning 작업 영역을 만들려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-114">To create an Azure Machine Learning workspace, the following are required:</span></span>

- <span data-ttu-id="bcc18-115">이름: 3~33자 길이의 작업 영역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-115">Name: A name for your workspace between 3-33 characters.</span></span> <span data-ttu-id="bcc18-116">이름은 영숫자 문자와 하이픈만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-116">Names may only contain alphanumeric characters and hyphens.</span></span>
- <span data-ttu-id="bcc18-117">지역: 작업 영역 및 리소스가 배포되는 데이터 센터의 지리적 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-117">Region: The geographic location of the data center where your workspace and resources are deployed to.</span></span> <span data-ttu-id="bcc18-118">귀하 또는 귀하의 고객이 있는 위치와 가까운 위치를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-118">It is recommended that you choose a location close to where you or your customers are.</span></span>
- <span data-ttu-id="bcc18-119">리소스 그룹: Azure 솔루션의 모든 관련 리소스를 포함하는 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-119">Resource group: A container that contains all related resources for an Azure solution.</span></span>

## <a name="what-is-an-azure-machine-learning-compute"></a><span data-ttu-id="bcc18-120">Azure Machine Learning 컴퓨팅이란?</span><span class="sxs-lookup"><span data-stu-id="bcc18-120">What is an Azure Machine Learning compute?</span></span>

<span data-ttu-id="bcc18-121">Azure Machine Learning 컴퓨팅은 학습에 사용되는 클라우드 기반 Linux VM입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-121">An Azure Machine Learning compute is a cloud-based Linux VM used for training.</span></span>

<span data-ttu-id="bcc18-122">Azure Machine Learning 작업 영역을 만들려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-122">To create an Azure Machine Learning workspace, the following are required:</span></span>

- <span data-ttu-id="bcc18-123">이름: 2~16자 길이의 작업 영역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-123">Name: A name for your workspace between 2-16 characters.</span></span> <span data-ttu-id="bcc18-124">이름은 영숫자 문자와 하이픈만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-124">Names may only contain alphanumeric characters and hyphens.</span></span>
- <span data-ttu-id="bcc18-125">컴퓨팅 크기</span><span class="sxs-lookup"><span data-stu-id="bcc18-125">Compute size</span></span>

    <span data-ttu-id="bcc18-126">모델 작성기는 다음과 같은 GPU 최적화 컴퓨팅 형식 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-126">Model Builder can use one of the following GPU-optimized compute types:</span></span>

    | <span data-ttu-id="bcc18-127">Size</span><span class="sxs-lookup"><span data-stu-id="bcc18-127">Size</span></span> | <span data-ttu-id="bcc18-128">vCPU</span><span class="sxs-lookup"><span data-stu-id="bcc18-128">vCPU</span></span> | <span data-ttu-id="bcc18-129">메모리: GiB</span><span class="sxs-lookup"><span data-stu-id="bcc18-129">Memory: GiB</span></span> | <span data-ttu-id="bcc18-130">임시 스토리지(SSD) GiB</span><span class="sxs-lookup"><span data-stu-id="bcc18-130">Temp storage (SSD) GiB</span></span> | <span data-ttu-id="bcc18-131">GPU</span><span class="sxs-lookup"><span data-stu-id="bcc18-131">GPU</span></span> | <span data-ttu-id="bcc18-132">GPU 메모리: GiB</span><span class="sxs-lookup"><span data-stu-id="bcc18-132">GPU memory: GiB</span></span> | <span data-ttu-id="bcc18-133">최대 데이터 디스크 수</span><span class="sxs-lookup"><span data-stu-id="bcc18-133">Max data disks</span></span> | <span data-ttu-id="bcc18-134">최대 NIC 수</span><span class="sxs-lookup"><span data-stu-id="bcc18-134">Max NICs</span></span> |
    |---|---|---|---|---|---|---|---|
    | <span data-ttu-id="bcc18-135">Standard_NC12</span><span class="sxs-lookup"><span data-stu-id="bcc18-135">Standard_NC12</span></span>   | <span data-ttu-id="bcc18-136">12</span><span class="sxs-lookup"><span data-stu-id="bcc18-136">12</span></span> | <span data-ttu-id="bcc18-137">112</span><span class="sxs-lookup"><span data-stu-id="bcc18-137">112</span></span> | <span data-ttu-id="bcc18-138">680</span><span class="sxs-lookup"><span data-stu-id="bcc18-138">680</span></span>  | <span data-ttu-id="bcc18-139">2</span><span class="sxs-lookup"><span data-stu-id="bcc18-139">2</span></span> | <span data-ttu-id="bcc18-140">24</span><span class="sxs-lookup"><span data-stu-id="bcc18-140">24</span></span> | <span data-ttu-id="bcc18-141">48</span><span class="sxs-lookup"><span data-stu-id="bcc18-141">48</span></span> | <span data-ttu-id="bcc18-142">2</span><span class="sxs-lookup"><span data-stu-id="bcc18-142">2</span></span> |
    | <span data-ttu-id="bcc18-143">Standard_NC24</span><span class="sxs-lookup"><span data-stu-id="bcc18-143">Standard_NC24</span></span>   | <span data-ttu-id="bcc18-144">24</span><span class="sxs-lookup"><span data-stu-id="bcc18-144">24</span></span> | <span data-ttu-id="bcc18-145">224</span><span class="sxs-lookup"><span data-stu-id="bcc18-145">224</span></span> | <span data-ttu-id="bcc18-146">1440</span><span class="sxs-lookup"><span data-stu-id="bcc18-146">1440</span></span> | <span data-ttu-id="bcc18-147">4</span><span class="sxs-lookup"><span data-stu-id="bcc18-147">4</span></span> | <span data-ttu-id="bcc18-148">48</span><span class="sxs-lookup"><span data-stu-id="bcc18-148">48</span></span> | <span data-ttu-id="bcc18-149">64</span><span class="sxs-lookup"><span data-stu-id="bcc18-149">64</span></span> | <span data-ttu-id="bcc18-150">4</span><span class="sxs-lookup"><span data-stu-id="bcc18-150">4</span></span> |

    <span data-ttu-id="bcc18-151">GPU 최적화 컴퓨팅 형식에 대한 자세한 내용은 [NC 시리즈 Linux VM 설명서](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcc18-151">Visit the [NC-series Linux VM documentation](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json) for more details on GPU optimized compute types.</span></span>
- <span data-ttu-id="bcc18-152">컴퓨팅 우선 순위</span><span class="sxs-lookup"><span data-stu-id="bcc18-152">Compute priority</span></span>

  - <span data-ttu-id="bcc18-153">낮은 우선 순위: 실행 시간이 짧은 작업에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-153">Low-priority: Suited for tasks with shorter execution times.</span></span> <span data-ttu-id="bcc18-154">중단 및 가용성 부족의 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-154">May be impacted by interruptions and lack of availability.</span></span> <span data-ttu-id="bcc18-155">Azure에서 여분의 용량을 활용하므로 일반적으로 비용이 절감됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-155">Usually costs less because it takes advantage of surplus capacity in Azure.</span></span>
  - <span data-ttu-id="bcc18-156">전용: 모든 기간의 작업에 적합하지만 장기 실행 작업에 특히 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-156">Dedicated: Suited for tasks of any duration, but especially long-running jobs.</span></span> <span data-ttu-id="bcc18-157">중단 또는 가용성 부족의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-157">Not impacted by interruptions or lack of availability.</span></span> <span data-ttu-id="bcc18-158">작업에 대해 Azure의 전용 컴퓨팅 리소스 세트를 예약하므로 일반적으로 비용이 더 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-158">Usually costs more because it reserves a dedicated set of compute resources in Azure for your tasks.</span></span>

## <a name="training"></a><span data-ttu-id="bcc18-159">교육</span><span class="sxs-lookup"><span data-stu-id="bcc18-159">Training</span></span>

<span data-ttu-id="bcc18-160">Azure에 대한 학습은 모델 작성기 이미지 분류 시나리오에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-160">Training on Azure is only available for the Model Builder image classification scenario.</span></span> <span data-ttu-id="bcc18-161">이 모델을 학습시키는 데 사용되는 알고리즘은 ResNet50 아키텍처를 기반으로 한 심층 신경망입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-161">The algorithm used to train these models is a Deep Neural Network based on the ResNet50 architecture.</span></span> <span data-ttu-id="bcc18-162">학습 프로세스에는 어느 정도 시간이 걸리며, 선택한 컴퓨팅 크기 및 데이터의 양에 따라 걸리는 시간이 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-162">The training process takes some time and the amount of time may vary depending on the size of compute selected as well as amount of data.</span></span> <span data-ttu-id="bcc18-163">처음 모델을 학습시킬 때는 리소스를 프로비저닝해야 하므로 학습 시간이 약간 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-163">The first time a model is trained, you can expect a slightly longer training time because resources have to be provisioned.</span></span> <span data-ttu-id="bcc18-164">Visual Studio에서 “Monitor current run in Azure portal”(Azure Portal에서 현재 실행 모니터링) 링크를 선택하여 실행의 진행률을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-164">You can track the progress of your runs by selecting the "Monitor current run in Azure portal" link in Visual Studio.</span></span>

## <a name="results"></a><span data-ttu-id="bcc18-165">결과</span><span class="sxs-lookup"><span data-stu-id="bcc18-165">Results</span></span>

<span data-ttu-id="bcc18-166">학습이 완료되면 다음 접미사가 사용된 두 개의 프로젝트가 솔루션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-166">Once training is complete, two projects are added to your solution with the following suffixes:</span></span>

- <span data-ttu-id="bcc18-167">*ConsoleApp*: 예측 파이프라인을 빌드하고 예측을 수행하기 위한 시작 코드를 제공하는 C# .NET Core 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-167">*ConsoleApp*: A C# .NET Core console application that provides starter code to build the prediction pipeline and make predictions.</span></span>
- <span data-ttu-id="bcc18-168">*모델*: 입력 및 출력 모델 데이터의 스키마와 다음 자산을 정의하는 데이터 모델이 포함된 C# .NET Standard 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-168">*Model*: A C# .NET Standard application that contains the data models that define the schema of input and output model data as well as the following assets:</span></span>

  - <span data-ttu-id="bcc18-169">bestModel.onnx: ONNX(Open Neural Network Exchange) 형식으로 된 모델의 직렬화된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-169">bestModel.onnx: A serialized version of the model in Open Neural Network Exchange (ONNX) format.</span></span> <span data-ttu-id="bcc18-170">ONNX는 ML.NET, PyTorch, TensorFlow 등의 프레임워크 간 상호 운용성을 지원하는 AI 모델의 오픈 소스 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-170">ONNX is an open source format for AI models that supports interoperability between frameworks like ML.NET, PyTorch and TensorFlow.</span></span>
  - <span data-ttu-id="bcc18-171">bestModelMap.json: 예측을 만들어 모델 출력을 텍스트 범주에 매핑할 때 사용되는 범주 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-171">bestModelMap.json: A list of categories used when making predictions to map the model output to a text category.</span></span>
  - <span data-ttu-id="bcc18-172">MLModel.zip: *bestModel.onnx* 모델의 직렬화된 버전을 사용하여 예측하고 `bestModelMap.json` 파일을 사용하여 출력을 매핑하는 ML.NET 예측 파이프라인의 직렬화된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-172">MLModel.zip: A serialized version of the ML.NET prediction pipeline that uses the serialized version of the model *bestModel.onnx* to make predictions and maps outputs using the `bestModelMap.json` file.</span></span>

## <a name="use-the-machine-learning-model"></a><span data-ttu-id="bcc18-173">기계 학습 모델 사용</span><span class="sxs-lookup"><span data-stu-id="bcc18-173">Use the machine learning model</span></span>

<span data-ttu-id="bcc18-174">*Model* 프로젝트의 `ModelInput` 및 `ModelOutput` 클래스는 각각 모델의 필요한 입력 및 출력 스키마를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-174">The `ModelInput` and `ModelOutput` classes in the *Model* project define the schema of the model's expected input and output respectively.</span></span>

<span data-ttu-id="bcc18-175">이미지 분류 시나리오에서 `ModelInput`은 다음과 같은 두 개의 열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-175">In an image classification scenario, the `ModelInput` contains two columns:</span></span>

- <span data-ttu-id="bcc18-176">`ImageSource`: 이미지 위치의 문자열 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-176">`ImageSource`: The string path of the image location.</span></span>
- <span data-ttu-id="bcc18-177">`Label`: 이미지가 속하는 실제 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-177">`Label`: The actual category the image belongs to.</span></span> <span data-ttu-id="bcc18-178">`Label`은 학습 시 입력으로만 사용되며 예측할 때 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-178">`Label` is only used as an input when training and does not need to be provided when making predictions.</span></span>

<span data-ttu-id="bcc18-179">`ModelOutput`은 다음과 같은 두 개의 열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-179">The `ModelOutput` contains two columns:</span></span>

- <span data-ttu-id="bcc18-180">`Prediction`: 이미지의 예측 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-180">`Prediction`: The image's predicted category.</span></span>
- <span data-ttu-id="bcc18-181">`Score`: 모든 범주에 대한 확률 목록입니다(가장 높은 확률이 `Prediction`에 속함).</span><span class="sxs-lookup"><span data-stu-id="bcc18-181">`Score`: The list of probabilities for all categories (the highest belongs to the `Prediction`).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bcc18-182">문제 해결</span><span class="sxs-lookup"><span data-stu-id="bcc18-182">Troubleshooting</span></span>

### <a name="cannot-create-compute"></a><span data-ttu-id="bcc18-183">컴퓨팅을 만들 수 없음</span><span class="sxs-lookup"><span data-stu-id="bcc18-183">Cannot create compute</span></span>

<span data-ttu-id="bcc18-184">Azure Machine Learning 컴퓨팅을 생성하는 동안 오류가 발생하는 경우, 그런데도 컴퓨팅 리소스가 존재할 수는 있습니다(단, 오류 상태).</span><span class="sxs-lookup"><span data-stu-id="bcc18-184">If an error occurs during Azure Machine Learning compute creation, the compute resource may still exist, in an errored state.</span></span> <span data-ttu-id="bcc18-185">같은 이름으로 컴퓨팅 리소스를 다시 만들려고 하면 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-185">If you try to re-create the compute resource with the same name, the operation fails.</span></span> <span data-ttu-id="bcc18-186">이 오류를 해결하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc18-186">To fix this error, either:</span></span>

- <span data-ttu-id="bcc18-187">다른 이름으로 새 컴퓨팅 만들기</span><span class="sxs-lookup"><span data-stu-id="bcc18-187">Create the new compute with a different name</span></span>
- <span data-ttu-id="bcc18-188">Azure Portal로 이동하여 원래 컴퓨팅 리소스 제거</span><span class="sxs-lookup"><span data-stu-id="bcc18-188">Go to the Azure portal, and remove the original compute resource</span></span>
