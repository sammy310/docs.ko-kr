---
description: '자세한 정보: -subsystemversion(Visual Basic)'
title: -subsystemversion
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: 2aecf08b95249b6c4285ca7fe71f4e488f8db3c8
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480828"
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="db052-103">-subsystemversion(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db052-103">-subsystemversion (Visual Basic)</span></span>

<span data-ttu-id="db052-104">생성된 실행 파일을 실행할 수 있는 하위 시스템의 최소 버전을 지정하여 실행 파일을 실행할 수 있는 Windows 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="db052-104">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="db052-105">가장 일반적으로, 이 옵션은 실행 파일이 이전 버전의 Windows에서 사용할 수 없는 특정 보안 기능을 활용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="db052-105">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="db052-106">하위 시스템 자체를 지정하려면 [-target](target.md) 컴파일러 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="db052-106">To specify the subsystem itself, use the [-target](target.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="db052-107">구문</span><span class="sxs-lookup"><span data-stu-id="db052-107">Syntax</span></span>

```vb
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="db052-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db052-108">Parameters</span></span>

`major.minor`

<span data-ttu-id="db052-109">주 버전과 부 버전의 점 표기법으로 표현된 필수 최소 버전의 하위 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="db052-109">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="db052-110">예를 들어 이 항목의 뒷부분에 나오는 표의 설명에 따라 이 옵션의 값을 6.01로 설정하는 경우 Windows 7 이전 운영 체제에서는 애플리케이션을 실행할 수 없도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db052-110">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="db052-111">`major` 및 `minor`의 값을 정수로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db052-111">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="db052-112">`minor` 버전에서 선행 0은 버전을 변경하지 않지만 후행 0은 버전을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="db052-112">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="db052-113">예를 들어 6.1과 6.01은 동일한 버전을 가리키지만 6.10은 다른 버전을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="db052-113">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="db052-114">혼동을 피하기 위해 부 버전을 두 자리로 표현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db052-114">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="db052-115">설명</span><span class="sxs-lookup"><span data-stu-id="db052-115">Remarks</span></span>

<span data-ttu-id="db052-116">다음 표에는 Windows의 일반적인 하위 시스템 버전이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db052-116">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="db052-117">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="db052-117">Windows version</span></span>|<span data-ttu-id="db052-118">하위 시스템 버전</span><span class="sxs-lookup"><span data-stu-id="db052-118">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="db052-119">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="db052-119">Windows 2000</span></span>|<span data-ttu-id="db052-120">5.00</span><span class="sxs-lookup"><span data-stu-id="db052-120">5.00</span></span>|
|<span data-ttu-id="db052-121">Windows XP</span><span class="sxs-lookup"><span data-stu-id="db052-121">Windows XP</span></span>|<span data-ttu-id="db052-122">5.01</span><span class="sxs-lookup"><span data-stu-id="db052-122">5.01</span></span>|
|<span data-ttu-id="db052-123">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="db052-123">Windows Server 2003</span></span>|<span data-ttu-id="db052-124">5.02</span><span class="sxs-lookup"><span data-stu-id="db052-124">5.02</span></span>|
|<span data-ttu-id="db052-125">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="db052-125">Windows Vista</span></span>|<span data-ttu-id="db052-126">6.00</span><span class="sxs-lookup"><span data-stu-id="db052-126">6.00</span></span>|
|<span data-ttu-id="db052-127">Windows 7</span><span class="sxs-lookup"><span data-stu-id="db052-127">Windows 7</span></span>|<span data-ttu-id="db052-128">6.01</span><span class="sxs-lookup"><span data-stu-id="db052-128">6.01</span></span>|
|<span data-ttu-id="db052-129">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="db052-129">Windows Server 2008</span></span>|<span data-ttu-id="db052-130">6.01</span><span class="sxs-lookup"><span data-stu-id="db052-130">6.01</span></span>|
|<span data-ttu-id="db052-131">Windows 8</span><span class="sxs-lookup"><span data-stu-id="db052-131">Windows 8</span></span>|<span data-ttu-id="db052-132">6.02</span><span class="sxs-lookup"><span data-stu-id="db052-132">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="db052-133">기본값</span><span class="sxs-lookup"><span data-stu-id="db052-133">Default values</span></span>

<span data-ttu-id="db052-134">**-subsystemversion** 컴파일러 옵션의 기본값은 다음 목록의 조건에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="db052-134">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="db052-135">다음 목록의 컴파일러 옵션이 설정된 경우 기본값은 6.02입니다.</span><span class="sxs-lookup"><span data-stu-id="db052-135">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="db052-136">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="db052-136">-target:appcontainerexe</span></span>](target.md)

  - [<span data-ttu-id="db052-137">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="db052-137">-target:winmdobj</span></span>](target.md)

  - [<span data-ttu-id="db052-138">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="db052-138">-platform:arm</span></span>](platform.md)

- <span data-ttu-id="db052-139">MSBuild를 사용하고 .NET Framework 4.5를 대상으로 하며, 이 목록의 앞에서 지정된 컴파일러 옵션 중 하나를 설정하지 않은 경우 기본값은 6.00입니다.</span><span class="sxs-lookup"><span data-stu-id="db052-139">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="db052-140">앞의 조건이 하나도 true가 아닌 경우 기본값은 4.00입니다.</span><span class="sxs-lookup"><span data-stu-id="db052-140">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="db052-141">이 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="db052-141">Setting this option</span></span>

<span data-ttu-id="db052-142">Visual Studio에서 **-subsystemversion** 컴파일러 옵션을 설정하려면 .vbproj 파일을 열고 MSBuild XML에서 `SubsystemVersion` 속성의 값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db052-142">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="db052-143">Visual Studio IDE에서는 이 옵션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db052-143">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="db052-144">자세한 내용은 이 항목의 앞부분에 나오는 "기본값"이나 [일반적인 MSBuild 프로젝트 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db052-144">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="db052-145">참조</span><span class="sxs-lookup"><span data-stu-id="db052-145">See also</span></span>

- [<span data-ttu-id="db052-146">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="db052-146">Visual Basic Command-Line Compiler</span></span>](index.md)

- [<span data-ttu-id="db052-147">MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="db052-147">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
