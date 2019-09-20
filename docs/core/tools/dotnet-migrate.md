---
title: dotnet migrate 명령
description: dotnet migrate 명령은 프로젝트와 모든 종속성을 마이그레이션합니다.
ms.date: 08/08/2019
ms.openlocfilehash: 790c607070ff348ca7cfe30137268de18dcb0293
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990424"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="ed8f3-103">dotnet 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ed8f3-103">dotnet migrate</span></span>

<span data-ttu-id="ed8f3-104">**이 문서 적용 대상: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="ed8f3-104">**This article applies to: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="ed8f3-105">name</span><span class="sxs-lookup"><span data-stu-id="ed8f3-105">Name</span></span>

<span data-ttu-id="ed8f3-106">`dotnet migrate` - Preview 2 .NET Core 프로젝트를 .NET Core SDK 스타일 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ed8f3-107">개요</span><span class="sxs-lookup"><span data-stu-id="ed8f3-107">Synopsis</span></span>

```console
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ed8f3-108">설명</span><span class="sxs-lookup"><span data-stu-id="ed8f3-108">Description</span></span>

<span data-ttu-id="ed8f3-109">`dotnet migrate` 명령은 유효한 Preview 2 *project.json* 기반 프로젝트를 유효한 .NET Core SDK 스타일 *csproj* 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-109">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK-style *csproj* project.</span></span>

<span data-ttu-id="ed8f3-110">기본적으로 이 명령은 루트 프로젝트와, 루트 프로젝트에 포함된 모든 프로젝트 참조를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-110">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="ed8f3-111">이 동작은 런타임에 `--skip-project-references` 옵션을 사용하여 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-111">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="ed8f3-112">다음 자산에 대해 마이그레이션을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-112">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="ed8f3-113">마이그레이션할 *project.json* 파일을 지정하여 단일 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ed8f3-113">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="ed8f3-114">*global.json* 파일로 경로를 전달하여 *global.json* 파일에 지정된 모든 디렉터리</span><span class="sxs-lookup"><span data-stu-id="ed8f3-114">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="ed8f3-115">*solution.sln* 파일: 솔루션에서 참조된 프로젝트를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-115">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="ed8f3-116">지정된 디렉터리의 모든 하위 디렉터리(재귀적).</span><span class="sxs-lookup"><span data-stu-id="ed8f3-116">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="ed8f3-117">`dotnet migrate` 명령은 마이그레이션된 *project.json* 파일을 `backup` 디렉터리에서 유지합니다. 이 디렉터리는 없는 경우 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-117">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="ed8f3-118">이 동작은 `--skip-backup` 옵션을 사용하여 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-118">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="ed8f3-119">기본적으로 마이그레이션 작업은 표준 출력(STDOUT)에 마이그레이션 프로세스의 상태를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-119">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="ed8f3-120">`--report-file <REPORT_FILE>` 옵션을 사용하는 경우 출력이 지정된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-120">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="ed8f3-121">`dotnet migrate` 명령은 유효한 Preview 2 *project.json* 기반 프로젝트만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-121">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="ed8f3-122">즉, DNX 또는 Preview 1 *project.json* 기반 프로젝트를 MSBuild/csproj 프로젝트에 직접 마이그레이션하는 데는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-122">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="ed8f3-123">먼저 수동으로 프로젝트를 Preview 2 *project.json* 기반 프로젝트로 마이그레이션한 다음 `dotnet migrate` 명령을 사용하여 프로젝트를 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-123">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

<span data-ttu-id="ed8f3-124">`dotnet migrate` 명령은 .NET Core 3.0 SDK부터 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-124">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span>

## <a name="arguments"></a><span data-ttu-id="ed8f3-125">인수</span><span class="sxs-lookup"><span data-stu-id="ed8f3-125">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="ed8f3-126">다음 중 하나의 경로</span><span class="sxs-lookup"><span data-stu-id="ed8f3-126">The path to one of the following:</span></span>

* <span data-ttu-id="ed8f3-127">마이그레이션할 *project.json* 파일</span><span class="sxs-lookup"><span data-stu-id="ed8f3-127">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="ed8f3-128">*global.json* 파일: *global.json*에 지정된 폴더가 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-128">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="ed8f3-129">*solution.sln* 파일: 솔루션에서 참조된 프로젝트가 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-129">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="ed8f3-130">마이그레이션할 디렉터리: 지정한 디렉터리 내에서 마이그레이션할 *project.json* 파일을 재귀적으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-130">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="ed8f3-131">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-131">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="ed8f3-132">옵션</span><span class="sxs-lookup"><span data-stu-id="ed8f3-132">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="ed8f3-133">사용자 메시지가 아닌 JSON으로 마이그레이션 보고서 파일을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-133">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="ed8f3-134">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-134">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="ed8f3-135">마이그레이션 보고서를 콘솔 외에도 파일에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-135">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="ed8f3-136">마이그레이션 프로젝트 참조를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-136">Skip migrating project references.</span></span> <span data-ttu-id="ed8f3-137">기본적으로 프로젝트 참조는 재귀적으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-137">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="ed8f3-138">마이그레이션을 완료한 후 *project.json*, *global.json* 및 *\*.xproj*를 `backup` 디렉터리로 이동하는 작업을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-138">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="ed8f3-139">마이그레이션에 사용할 템플릿 csproj 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-139">Template csproj file to use for migration.</span></span> <span data-ttu-id="ed8f3-140">기본적으로 `dotnet new console`에서 삭제한 것과 동일한 템플릿이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-140">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="ed8f3-141">마이그레이션된 앱에서 참조할 sdk 패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-141">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="ed8f3-142">기본값은 `dotnet new`의 SDK 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-142">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="ed8f3-143">사용할 xproj 파일에 대한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-143">The path to the xproj file to use.</span></span> <span data-ttu-id="ed8f3-144">프로젝트 디렉터리에 둘 이상의 xproj 있을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-144">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="ed8f3-145">예제</span><span class="sxs-lookup"><span data-stu-id="ed8f3-145">Examples</span></span>

<span data-ttu-id="ed8f3-146">현재 디렉터리의 프로젝트와 해당하는 모든 프로젝트를 프로젝트 종속성으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-146">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="ed8f3-147">*global.json* 파일에 포함된 프로젝트를 모두 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-147">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="ed8f3-148">현재 프로젝트만 마이그레이션하고 프로젝트 간(P2P) 종속성은 마이그레이션하지 않으며,</span><span class="sxs-lookup"><span data-stu-id="ed8f3-148">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="ed8f3-149">특정 SDK 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8f3-149">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
