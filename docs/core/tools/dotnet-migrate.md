---
title: dotnet migrate 명령
description: dotnet migrate 명령은 프로젝트와 모든 종속성을 마이그레이션합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 71f587c1bfadd445aca818448bdd5f136f009fe0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463631"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="4b3e0-103">dotnet 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4b3e0-103">dotnet migrate</span></span>

<span data-ttu-id="4b3e0-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="4b3e0-104">**This article applies to:** ✔️ .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="4b3e0-105">name</span><span class="sxs-lookup"><span data-stu-id="4b3e0-105">Name</span></span>

<span data-ttu-id="4b3e0-106">`dotnet migrate` - Preview 2 .NET Core 프로젝트를 .NET Core SDK 스타일 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4b3e0-107">개요</span><span class="sxs-lookup"><span data-stu-id="4b3e0-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json <REPORT_FILE>]
    [-r|--report-file <REPORT_FILE>] [-s|--skip-project-references [Debug|Release]]
    [--skip-backup] [-t|--template-file <TEMPLATE_FILE>] [-v|--sdk-package-version]
    [-x|--xproj-file]

dotnet migrate -h|--help
```

## <a name="description"></a><span data-ttu-id="4b3e0-108">설명</span><span class="sxs-lookup"><span data-stu-id="4b3e0-108">Description</span></span>

<span data-ttu-id="4b3e0-109">이 명령은 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-109">This command is deprecated.</span></span> <span data-ttu-id="4b3e0-110">`dotnet migrate` 명령은 .NET Core 3.0 SDK부터 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-110">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span> <span data-ttu-id="4b3e0-111">미리 보기 2 .NET Core 프로젝트만 1.x .NET Core 프로젝트(지원되지 않음)로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-111">It can only migrate a Preview 2 .NET Core project to a 1.x .NET Core project, which is out of support.</span></span>

<span data-ttu-id="4b3e0-112">기본적으로 이 명령은 루트 프로젝트와, 루트 프로젝트에 포함된 모든 프로젝트 참조를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-112">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="4b3e0-113">이 동작은 런타임에 `--skip-project-references` 옵션을 사용하여 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-113">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="4b3e0-114">다음 자산에 대해 마이그레이션을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-114">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="4b3e0-115">마이그레이션할 *project.json* 파일을 지정하여 단일 프로젝트</span><span class="sxs-lookup"><span data-stu-id="4b3e0-115">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="4b3e0-116">*global.json* 파일로 경로를 전달하여 *global.json* 파일에 지정된 모든 디렉터리</span><span class="sxs-lookup"><span data-stu-id="4b3e0-116">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="4b3e0-117">*solution.sln* 파일: 솔루션에서 참조된 프로젝트를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-117">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="4b3e0-118">지정된 디렉터리의 모든 하위 디렉터리(재귀적).</span><span class="sxs-lookup"><span data-stu-id="4b3e0-118">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="4b3e0-119">`dotnet migrate` 명령은 마이그레이션된 *project.json* 파일을 `backup` 디렉터리에서 유지합니다. 이 디렉터리는 없는 경우 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-119">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="4b3e0-120">이 동작은 `--skip-backup` 옵션을 사용하여 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-120">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="4b3e0-121">기본적으로 마이그레이션 작업은 표준 출력(STDOUT)에 마이그레이션 프로세스의 상태를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-121">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="4b3e0-122">`--report-file <REPORT_FILE>` 옵션을 사용하는 경우 출력이 지정된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-122">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="4b3e0-123">`dotnet migrate` 명령은 유효한 Preview 2 *project.json* 기반 프로젝트만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-123">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="4b3e0-124">즉, DNX 또는 Preview 1 *project.json* 기반 프로젝트를 MSBuild/csproj 프로젝트에 직접 마이그레이션하는 데는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-124">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="4b3e0-125">먼저 수동으로 프로젝트를 Preview 2 *project.json* 기반 프로젝트로 마이그레이션한 다음 `dotnet migrate` 명령을 사용하여 프로젝트를 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-125">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="4b3e0-126">인수</span><span class="sxs-lookup"><span data-stu-id="4b3e0-126">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="4b3e0-127">다음 중 하나의 경로</span><span class="sxs-lookup"><span data-stu-id="4b3e0-127">The path to one of the following:</span></span>

* <span data-ttu-id="4b3e0-128">마이그레이션할 *project.json* 파일</span><span class="sxs-lookup"><span data-stu-id="4b3e0-128">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="4b3e0-129">*global.json* 파일: *global.json*에 지정된 폴더가 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-129">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="4b3e0-130">*solution.sln* 파일: 솔루션에서 참조된 프로젝트가 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-130">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="4b3e0-131">마이그레이션할 디렉터리: 지정한 디렉터리 내에서 마이그레이션할 *project.json* 파일을 재귀적으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-131">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="4b3e0-132">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-132">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="4b3e0-133">옵션</span><span class="sxs-lookup"><span data-stu-id="4b3e0-133">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="4b3e0-134">사용자 메시지가 아닌 JSON으로 마이그레이션 보고서 파일을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-134">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="4b3e0-135">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-135">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="4b3e0-136">마이그레이션 보고서를 콘솔 외에도 파일에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-136">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="4b3e0-137">마이그레이션 프로젝트 참조를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-137">Skip migrating project references.</span></span> <span data-ttu-id="4b3e0-138">기본적으로 프로젝트 참조는 재귀적으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-138">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="4b3e0-139">마이그레이션을 완료한 후 *project.json*, *global.json* 및 *\*.xproj*를 `backup` 디렉터리로 이동하는 작업을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-139">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="4b3e0-140">마이그레이션에 사용할 템플릿 csproj 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-140">Template csproj file to use for migration.</span></span> <span data-ttu-id="4b3e0-141">기본적으로 `dotnet new console`에서 삭제한 것과 동일한 템플릿이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-141">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="4b3e0-142">마이그레이션된 앱에서 참조할 sdk 패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-142">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="4b3e0-143">기본값은 `dotnet new`의 SDK 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-143">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="4b3e0-144">사용할 xproj 파일에 대한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-144">The path to the xproj file to use.</span></span> <span data-ttu-id="4b3e0-145">프로젝트 디렉터리에 둘 이상의 xproj 있을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-145">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="4b3e0-146">예</span><span class="sxs-lookup"><span data-stu-id="4b3e0-146">Examples</span></span>

<span data-ttu-id="4b3e0-147">현재 디렉터리의 프로젝트와 해당하는 모든 프로젝트를 프로젝트 종속성으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-147">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="4b3e0-148">*global.json* 파일에 포함된 프로젝트를 모두 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-148">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="4b3e0-149">현재 프로젝트만 마이그레이션하고 프로젝트 간(P2P) 종속성은 마이그레이션하지 않으며,</span><span class="sxs-lookup"><span data-stu-id="4b3e0-149">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="4b3e0-150">특정 SDK 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b3e0-150">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
