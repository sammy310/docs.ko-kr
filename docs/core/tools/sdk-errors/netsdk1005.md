---
title: 'NETSDK1005 및 NETSDK1047: 자산 파일에 대상이 없음'
description: 자산 파일에 대상이 없는 문제를 해결하는 방법입니다.
author: sfoslund
ms.topic: error-reference
ms.date: 12/17/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: e3e7389adf6a9a715d44661a5f7cbae5efe299e4
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678164"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="dccde-103">NETSDK1005 및 NETSDK1047: 자산 파일에 대상이 없음</span><span class="sxs-lookup"><span data-stu-id="dccde-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="dccde-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="dccde-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="dccde-105">.NET SDK가 NETSDK1005 또는 NETSDK1047 오류를 실행하는 경우 프로젝트의 자산 파일에 대상 프레임워크 중 하나의 정보가 누락된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="dccde-106">NuGet은 *obj* 폴더에 *project.assets.json* 이라는 파일을 작성하고 .NET SDK는 해당 파일을 사용하여 패키지 정보를 컴파일러에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-106">NuGet writes a file named *project.assets.json* in the *obj* folder, and the .NET SDK uses it to get information about packages to pass into the compiler.</span></span> <span data-ttu-id="dccde-107">.NET 5에서 NuGet에 `TargetFrameworkAlias`라는 새 필드가 추가되었으므로 이전 버전의 MSBuild 또는 NuGet은 새 필드 없이 자산 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-107">In .NET 5, NuGet added a new field named `TargetFrameworkAlias`, so earlier versions of MSBuild or NuGet generate an assets file without the new field.</span></span> <span data-ttu-id="dccde-108">자세한 내용은 [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html)(오류 NETSDK1005)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dccde-108">For more information, see [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).</span></span>

<span data-ttu-id="dccde-109">다음의 몇 가지 작업을 통해 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-109">Here are some actions you can take that may resolve the error:</span></span>

* <span data-ttu-id="dccde-110">MSBuild 버전 16.8 이상과 NuGet 버전 5.8 이상을 사용 중인지 확인하고 도구를 업데이트한 후 프로젝트를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-110">Make sure that you're using MSBuild version 16.8 or later and NuGet version 5.8 or later, and restore the project after updating your tools.</span></span> <span data-ttu-id="dccde-111">NuGet 버전 5.8 이상을 사용 중인 경우 Visual Studio 2019 버전 16.8 이상, MSBuild 버전 16.8 이상, .NET 5.0 SDK 이상을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-111">When you're using NuGet version 5.8 or later, you should be using Visual Studio 2019 version 16.8 or later, MSBuild version 16.8 or later, and .NET 5.0 SDK or later.</span></span>

* <span data-ttu-id="dccde-112">Visual Studio 2019에서 버전 16.8을 설치한 후나 프로젝트의 대상 프레임워크를 변경한 후 처음으로 프로젝트를 빌드하는 동안 오류가 발생하는 경우 프로젝트를 두 번째로 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-112">If you get the error while building a project in Visual Studio 2019 for the first time after installing version 16.8 or after changing the project's target framework, build the project a second time.</span></span>

* <span data-ttu-id="dccde-113">프로젝트를 빌드하기 전에 *obj* 폴더를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-113">Delete the *obj* folder before building the project.</span></span>

* <span data-ttu-id="dccde-114">누락된 대상 값이 프로젝트의 `TargetFrameworks` 속성에 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dccde-114">Make sure that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>
