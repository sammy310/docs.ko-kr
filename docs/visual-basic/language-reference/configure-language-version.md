---
title: Visual Basic 언어 버전 선택
description: 컴파일러가 특정 컴파일러 버전을 사용 하 여 구문 유효성 검사를 수행 하도록 구성 합니다.
ms.date: 05/24/2018
ms.openlocfilehash: 3b6d8055dbf64f2a5c38f46b6d66794fc48a1cea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797035"
---
# <a name="select-the-visual-basic-language-version"></a><span data-ttu-id="769fb-103">Visual Basic 언어 버전 선택</span><span class="sxs-lookup"><span data-stu-id="769fb-103">Select the Visual Basic language version</span></span>

<span data-ttu-id="769fb-104">Visual Basic 컴파일러 기본값은 해제 된 언어의 최신 주 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-104">The Visual Basic compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="769fb-105">언어의 새 포인트 릴리스를 사용하여 모든 프로젝트를 컴파일하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="769fb-106">최신 버전의 언어를 선택하면 프로젝트에서 최신 언어 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="769fb-107">다른 시나리오에서는 이전 버전의 언어를 사용할 때 프로젝트가 깨끗하게 컴파일되는지 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="769fb-108">이 기능은 개발 환경에서 SDK 및 도구의 새 버전을 설치하는 결정과 프로젝트의 새 언어 기능을 통합하는 결정을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="769fb-109">빌드 컴퓨터에 최신 SDK 및 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="769fb-110">각 프로젝트는 해당 빌드에 대해 특정 버전의 언어를 사용하도록 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="769fb-111">언어 버전을 설정 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-111">There are three ways to set the language version:</span></span>

- <span data-ttu-id="769fb-112">수동으로 편집 하 여 [ **.vbproj** 파일](#edit-the-vbproj-file)</span><span class="sxs-lookup"><span data-stu-id="769fb-112">Manually edit your [**.vbproj** file](#edit-the-vbproj-file)</span></span>
- <span data-ttu-id="769fb-113">언어 버전을 설정 [하위 디렉터리에 여러 프로젝트에 대 한](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="769fb-113">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects)</span></span>
- <span data-ttu-id="769fb-114">구성 된 [ `-langversion` 컴파일러 옵션](#set-the-langversion-compiler-option)</span><span class="sxs-lookup"><span data-stu-id="769fb-114">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option)</span></span>

## <a name="edit-the-vbproj-file"></a><span data-ttu-id="769fb-115">Vbproj 파일 편집</span><span class="sxs-lookup"><span data-stu-id="769fb-115">Edit the vbproj file</span></span>

<span data-ttu-id="769fb-116">언어 버전을 설정할 수 있습니다 하 **.vbproj** 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-116">You can set the language version in your **.vbproj** file.</span></span> <span data-ttu-id="769fb-117">다음 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-117">Add the following element:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="769fb-118">값 `latest` Visual Basic 언어의 최신 부 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-118">The value `latest` uses the latest minor version of the Visual Basic language.</span></span> <span data-ttu-id="769fb-119">올바른 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-119">Valid values are:</span></span>

|<span data-ttu-id="769fb-120">값</span><span class="sxs-lookup"><span data-stu-id="769fb-120">Value</span></span>|<span data-ttu-id="769fb-121">의미</span><span class="sxs-lookup"><span data-stu-id="769fb-121">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="769fb-122">default</span><span class="sxs-lookup"><span data-stu-id="769fb-122">default</span></span>|<span data-ttu-id="769fb-123">컴파일러는 지원할 수 있는 최신 주 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-123">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="769fb-124">10</span><span class="sxs-lookup"><span data-stu-id="769fb-124">9</span></span>|<span data-ttu-id="769fb-125">컴파일러 또는 Visual Basic 9.0에 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-125">The compiler accepts only syntax that is included in Visual Basic 9.0 or lower.</span></span>|
|<span data-ttu-id="769fb-126">10</span><span class="sxs-lookup"><span data-stu-id="769fb-126">10</span></span>|<span data-ttu-id="769fb-127">컴파일러 또는 Visual Basic 10.0의 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-127">The compiler accepts only syntax that is included in Visual Basic 10.0 or lower.</span></span>|
|<span data-ttu-id="769fb-128">11</span><span class="sxs-lookup"><span data-stu-id="769fb-128">11</span></span>|<span data-ttu-id="769fb-129">컴파일러 또는 Visual Basic 11.0에 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-129">The compiler accepts only syntax that is included in Visual Basic 11.0 or lower.</span></span>|
|<span data-ttu-id="769fb-130">12</span><span class="sxs-lookup"><span data-stu-id="769fb-130">12</span></span>|<span data-ttu-id="769fb-131">컴파일러 또는 Visual Basic 12.0에 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-131">The compiler accepts only syntax that is included in Visual Basic 12.0 or lower.</span></span>|
|<span data-ttu-id="769fb-132">14</span><span class="sxs-lookup"><span data-stu-id="769fb-132">14</span></span>|<span data-ttu-id="769fb-133">컴파일러 또는 Visual Basic 14.0에 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-133">The compiler accepts only syntax that is included in Visual Basic 14.0 or lower.</span></span>|
|<span data-ttu-id="769fb-134">15</span><span class="sxs-lookup"><span data-stu-id="769fb-134">15</span></span>|<span data-ttu-id="769fb-135">컴파일러 또는 Visual Basic 15.0에 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-135">The compiler accepts only syntax that is included in Visual Basic 15.0 or lower.</span></span>|
|<span data-ttu-id="769fb-136">15.3</span><span class="sxs-lookup"><span data-stu-id="769fb-136">15.3</span></span>|<span data-ttu-id="769fb-137">컴파일러 또는 Visual Basic 15.3에 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-137">The compiler accepts only syntax that is included in Visual Basic 15.3 or lower.</span></span>|
|<span data-ttu-id="769fb-138">15.5</span><span class="sxs-lookup"><span data-stu-id="769fb-138">15.5</span></span>|<span data-ttu-id="769fb-139">컴파일러 또는 Visual Basic 15.5에 포함 된 구문만을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-139">The compiler accepts only syntax that is included in Visual Basic 15.5 or lower.</span></span>|
|<span data-ttu-id="769fb-140">latest</span><span class="sxs-lookup"><span data-stu-id="769fb-140">latest</span></span>|<span data-ttu-id="769fb-141">컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-141">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="769fb-142">특수한 문자열 `default` 및 `latest`는 각각 빌드 컴퓨터에 설치된 최신 주 및 부 언어 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-142">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="769fb-143">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="769fb-143">Configure multiple projects</span></span>

<span data-ttu-id="769fb-144">`<LangVersion>` 요소를 포함하는 **Directory.build.props** 파일을 생성하여 여러 디렉터리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-144">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="769fb-145">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-145">You typically do that in your solution directory.</span></span> <span data-ttu-id="769fb-146">솔루션 디렉터리의 **Directory.build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-146">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="769fb-147">이제 해당 파일을 포함 하는 디렉터리의 모든 하위 디렉터리에 빌드는 Visual Basic 버전 15.5 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-147">Now, builds in every subdirectory of the directory containing that file will use Visual Basic version 15.5 syntax.</span></span> <span data-ttu-id="769fb-148">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="769fb-148">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="769fb-149">langversion 컴파일러 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="769fb-149">Set the langversion compiler option</span></span>

<span data-ttu-id="769fb-150">`-langversion` 명령줄 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-150">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="769fb-151">자세한 내용은 [-langversion](../reference/command-line-compiler/langversion.md) 컴파일러 옵션에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="769fb-151">For more information, see the article on the [-langversion](../reference/command-line-compiler/langversion.md) compiler option.</span></span> <span data-ttu-id="769fb-152">유효한 값 목록을 입력 하 여 보이는 `vbc -langversion:?` 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fb-152">You can see a list of the valid values by typing  `vbc -langversion:?` .</span></span>
