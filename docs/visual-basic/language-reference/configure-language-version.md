---
title: Visual Basic 언어 버전을 선택 합니다.
description: 특정 컴파일러 버전을 사용 하 여 구문 유효성 검사를 수행 하도록 컴파일러를 구성 합니다.
ms.date: 05/24/2018
ms.openlocfilehash: 09503db726f9d993bc986860c57aa98652b696d1
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585457"
---
# <a name="select-the-visual-basic-language-version"></a><span data-ttu-id="34bea-103">Visual Basic 언어 버전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-103">Select the Visual Basic language version</span></span>

<span data-ttu-id="34bea-104">Visual Basic 컴파일러의 기본값은 릴리스된 언어의 최신 주 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-104">The Visual Basic compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="34bea-105">언어의 새 포인트 릴리스를 사용하여 모든 프로젝트를 컴파일하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="34bea-106">최신 버전의 언어를 선택하면 프로젝트에서 최신 언어 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="34bea-107">다른 시나리오에서는 이전 버전의 언어를 사용할 때 프로젝트가 깨끗하게 컴파일되는지 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="34bea-108">이 기능은 개발 환경에서 SDK 및 도구의 새 버전을 설치하는 결정과 프로젝트의 새 언어 기능을 통합하는 결정을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="34bea-109">빌드 컴퓨터에 최신 SDK 및 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="34bea-110">각 프로젝트는 해당 빌드에 대해 특정 버전의 언어를 사용하도록 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="34bea-111">언어 버전을 설정 하는 방법에는 다음 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-111">There are three ways to set the language version:</span></span>

- <span data-ttu-id="34bea-112">[ **.Vbproj** 파일을 수동으로 편집](#edit-the-vbproj-file)</span><span class="sxs-lookup"><span data-stu-id="34bea-112">Manually edit your [**.vbproj** file](#edit-the-vbproj-file)</span></span>
- <span data-ttu-id="34bea-113">[하위 디렉터리의 여러 프로젝트에 대 한](#configure-multiple-projects) 언어 버전 설정</span><span class="sxs-lookup"><span data-stu-id="34bea-113">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects)</span></span>
- <span data-ttu-id="34bea-114">[ `-langversion` 컴파일러 옵션](#set-the-langversion-compiler-option) 구성</span><span class="sxs-lookup"><span data-stu-id="34bea-114">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option)</span></span>

## <a name="edit-the-vbproj-file"></a><span data-ttu-id="34bea-115">.Vbproj 파일 편집</span><span class="sxs-lookup"><span data-stu-id="34bea-115">Edit the vbproj file</span></span>

<span data-ttu-id="34bea-116">**.Vbproj** 파일의 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-116">You can set the language version in your **.vbproj** file.</span></span> <span data-ttu-id="34bea-117">다음 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-117">Add the following element:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="34bea-118">이 값은 `latest` Visual Basic 언어의 최신 부 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-118">The value `latest` uses the latest minor version of the Visual Basic language.</span></span> <span data-ttu-id="34bea-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-119">Valid values are:</span></span>

|<span data-ttu-id="34bea-120">값</span><span class="sxs-lookup"><span data-stu-id="34bea-120">Value</span></span>|<span data-ttu-id="34bea-121">의미</span><span class="sxs-lookup"><span data-stu-id="34bea-121">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="34bea-122">기본값</span><span class="sxs-lookup"><span data-stu-id="34bea-122">default</span></span>|<span data-ttu-id="34bea-123">컴파일러는 지원할 수 있는 최신 주 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-123">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="34bea-124">9</span><span class="sxs-lookup"><span data-stu-id="34bea-124">9</span></span>|<span data-ttu-id="34bea-125">컴파일러는 Visual Basic 9.0에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-125">The compiler accepts only syntax that is included in Visual Basic 9.0 or lower.</span></span>|
|<span data-ttu-id="34bea-126">10</span><span class="sxs-lookup"><span data-stu-id="34bea-126">10</span></span>|<span data-ttu-id="34bea-127">컴파일러는 Visual Basic 10.0에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-127">The compiler accepts only syntax that is included in Visual Basic 10.0 or lower.</span></span>|
|<span data-ttu-id="34bea-128">11</span><span class="sxs-lookup"><span data-stu-id="34bea-128">11</span></span>|<span data-ttu-id="34bea-129">컴파일러는 Visual Basic 11.0에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-129">The compiler accepts only syntax that is included in Visual Basic 11.0 or lower.</span></span>|
|<span data-ttu-id="34bea-130">12</span><span class="sxs-lookup"><span data-stu-id="34bea-130">12</span></span>|<span data-ttu-id="34bea-131">컴파일러는 Visual Basic 12.0에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-131">The compiler accepts only syntax that is included in Visual Basic 12.0 or lower.</span></span>|
|<span data-ttu-id="34bea-132">14</span><span class="sxs-lookup"><span data-stu-id="34bea-132">14</span></span>|<span data-ttu-id="34bea-133">컴파일러는 Visual Basic 14.0에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-133">The compiler accepts only syntax that is included in Visual Basic 14.0 or lower.</span></span>|
|<span data-ttu-id="34bea-134">15</span><span class="sxs-lookup"><span data-stu-id="34bea-134">15</span></span>|<span data-ttu-id="34bea-135">컴파일러는 Visual Basic 15.0에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-135">The compiler accepts only syntax that is included in Visual Basic 15.0 or lower.</span></span>|
|<span data-ttu-id="34bea-136">15.3</span><span class="sxs-lookup"><span data-stu-id="34bea-136">15.3</span></span>|<span data-ttu-id="34bea-137">컴파일러는 Visual Basic 15.3에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-137">The compiler accepts only syntax that is included in Visual Basic 15.3 or lower.</span></span>|
|<span data-ttu-id="34bea-138">15.5</span><span class="sxs-lookup"><span data-stu-id="34bea-138">15.5</span></span>|<span data-ttu-id="34bea-139">컴파일러는 Visual Basic 15.5에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-139">The compiler accepts only syntax that is included in Visual Basic 15.5 or lower.</span></span>|
|<span data-ttu-id="34bea-140">16</span><span class="sxs-lookup"><span data-stu-id="34bea-140">16</span></span>|<span data-ttu-id="34bea-141">컴파일러는 Visual Basic 16에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-141">The compiler accepts only syntax that is included in Visual Basic 16 or lower.</span></span>|
|<span data-ttu-id="34bea-142">16.9</span><span class="sxs-lookup"><span data-stu-id="34bea-142">16.9</span></span>|<span data-ttu-id="34bea-143">컴파일러는 Visual Basic 16.9에 포함 된 구문만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-143">The compiler accepts only syntax that is included in Visual Basic 16.9 or lower.</span></span>|
|<span data-ttu-id="34bea-144">최신</span><span class="sxs-lookup"><span data-stu-id="34bea-144">latest</span></span>|<span data-ttu-id="34bea-145">컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-145">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="34bea-146">특수한 문자열 `default` 및 `latest`는 각각 빌드 컴퓨터에 설치된 최신 주 및 부 언어 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-146">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="34bea-147">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="34bea-147">Configure multiple projects</span></span>

<span data-ttu-id="34bea-148">`<LangVersion>` 요소를 포함하는 **Directory.build.props** 파일을 생성하여 여러 디렉터리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-148">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="34bea-149">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-149">You typically do that in your solution directory.</span></span> <span data-ttu-id="34bea-150">다음을 솔루션 디렉터리의 **디렉터리. build. props** 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-150">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="34bea-151">이제 해당 파일을 포함 하는 디렉터리의 모든 하위 디렉터리에 있는 빌드에서 Visual Basic 버전 15.5 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-151">Now, builds in every subdirectory of the directory containing that file will use Visual Basic version 15.5 syntax.</span></span> <span data-ttu-id="34bea-152">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34bea-152">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="34bea-153">langversion 컴파일러 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="34bea-153">Set the langversion compiler option</span></span>

<span data-ttu-id="34bea-154">`-langversion` 명령줄 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bea-154">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="34bea-155">자세한 내용은 [-langversion](../reference/command-line-compiler/langversion.md) 컴파일러 옵션에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34bea-155">For more information, see the article on the [-langversion](../reference/command-line-compiler/langversion.md) compiler option.</span></span> <span data-ttu-id="34bea-156">을 입력 하 여 유효한 값의 목록을 볼 수 있습니다  `vbc -langversion:?` .</span><span class="sxs-lookup"><span data-stu-id="34bea-156">You can see a list of the valid values by typing  `vbc -langversion:?` .</span></span>
