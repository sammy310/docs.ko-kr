---
title: 코드 분석 규칙에 대 한 구성 파일
description: 코드 분석 규칙을 구성 하는 다양 한 구성 파일에 대해 알아봅니다.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: cf9b8f4033e6774684b2b7e3b788ef3c157d95df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594117"
---
# <a name="configuration-files-for-code-analysis-rules"></a><span data-ttu-id="43638-103">코드 분석 규칙에 대 한 구성 파일</span><span class="sxs-lookup"><span data-stu-id="43638-103">Configuration files for code analysis rules</span></span>

<span data-ttu-id="43638-104">코드 분석 규칙에는 다양 한 [구성 옵션이](configuration-options.md)있습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-104">Code analysis rules have various [configuration options](configuration-options.md).</span></span> <span data-ttu-id="43638-105">이러한 옵션은 다음 분석기 구성 파일 중 하나에서 키-값 쌍으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-105">You specify these options as key-value pairs in one of the following analyzer configuration files:</span></span>

- <span data-ttu-id="43638-106">[EditorConfig](#editorconfig) file: 파일 기반 또는 폴더 기반 구성 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-106">[EditorConfig](#editorconfig) file: File-based or folder-based configuration options.</span></span>
- <span data-ttu-id="43638-107">[Global AnalyzerConfig](#global-analyzerconfig) File: 프로젝트 수준 구성 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-107">[Global AnalyzerConfig](#global-analyzerconfig) file: Project-level configuration options.</span></span>

## EditorConfig

<span data-ttu-id="43638-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) 파일은 **특정 원본 파일이 나 폴더에 적용 되는 옵션** 을 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) files are used to provide **options that apply to specific source files or folders**.</span></span> <span data-ttu-id="43638-109">옵션은 해당 하는 파일 및 폴더를 식별 하기 위해 섹션 헤더 아래에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-109">Options are placed under section headers to identify the applicable files and folders.</span></span> <span data-ttu-id="43638-110">구성 하려는 각 규칙에 대 한 항목을 추가 하 고 해당 하는 파일 확장명 섹션 (예:)에 저장 `[*.cs]` 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-110">Add an entry for each rule you want to configure, and place it under the corresponding file extension section, for example, `[*.cs]`.</span></span>

```ini
[*.cs]
<option_name> = <option_value>
```

<span data-ttu-id="43638-111">위의 예제에서 `[*.cs]` 는 `.cs` 하위 폴더를 비롯 하 여 현재 폴더 내에서 파일 확장명이 있는 모든 c # 파일을 선택 하는 editorconfig 섹션 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-111">In the above example, `[*.cs]` is an editorconfig section header to select all C# files with `.cs` file extension within the current folder, including subfolders.</span></span> <span data-ttu-id="43638-112">이후 항목인은 `<option_name> = <option_value>` 모든 c # 파일에 적용 되는 분석기 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-112">The subsequent entry, `<option_name> = <option_value>`, is an analyzer option that will be applied to all the C# files.</span></span>

<span data-ttu-id="43638-113">파일을 EditorConfig 해당 디렉터리에 배치 하 여 폴더, 프로젝트 또는 전체 리포지토리에 파일 규칙을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-113">You can apply EditorConfig file conventions to a folder, a project, or an entire repo by placing the file in the corresponding directory.</span></span> <span data-ttu-id="43638-114">이러한 옵션은 빌드 시 분석을 실행 하 고 Visual Studio에서 코드를 편집 하는 동안 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-114">These options are applied when executing the analysis at build time and while you edit code in Visual Studio.</span></span>

<span data-ttu-id="43638-115">들여쓰기 크기 또는 후행 공백을 잘라낼 지 여부와 같은 편집기 설정에 대 한 기존 *editorconfig* 파일이 있는 경우 코드 분석 구성 옵션을 동일한 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-115">If you have an existing *.editorconfig* file for editor settings such as indent size or whether to trim trailing whitespace, you can place your code analysis configuration options in the same file.</span></span>

> [!TIP]
> <span data-ttu-id="43638-116">Visual Studio에서는 이러한 파일 중 하나를 프로젝트에 쉽게 추가할 수 있는 *editorconfig* 항목 템플릿을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-116">Visual Studio provides an *.editorconfig* item template that makes is easy to add one of these files to your project.</span></span> <span data-ttu-id="43638-117">자세한 내용은 [ EditorConfig 프로젝트에 파일 추가](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43638-117">For more information, see [Add an EditorConfig file to a project](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).</span></span>

### <a name="example"></a><span data-ttu-id="43638-118">예제</span><span class="sxs-lookup"><span data-stu-id="43638-118">Example</span></span>

<span data-ttu-id="43638-119">다음은 EditorConfig 옵션 및 규칙 심각도를 구성 하는 예제 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-119">Following is an example EditorConfig file to configure options and rule severity:</span></span>

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="global-analyzerconfig"></a><span data-ttu-id="43638-120">글로벌 AnalyzerConfig</span><span class="sxs-lookup"><span data-stu-id="43638-120">Global AnalyzerConfig</span></span>

<span data-ttu-id="43638-121">Visual Studio 2019 버전 16.8 이상 버전에서 지원 되는 .NET 5.0 SDK부터 전역 _AnalyzerConfig_ 파일을 사용 하 여 분석기 옵션을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-121">Starting with the .NET 5.0 SDK (which is supported in Visual Studio 2019 version 16.8 and later versions), you can also configure analyzer options with global _AnalyzerConfig_ files.</span></span> <span data-ttu-id="43638-122">이러한 파일은 해당 파일 이름이 나 파일 경로에 관계 없이 **프로젝트의 모든 소스 파일에 적용 되는 옵션** 을 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-122">These files are used to provide **options that apply to all the source files in a project**, regardless of their file names or file paths.</span></span>

<span data-ttu-id="43638-123">[EditorConfig](#editorconfig)파일과 달리 전역 구성 파일은 들여쓰기 크기 또는 후행 공백을 잘라낼 지 여부와 같은 ide의 편집기 스타일 설정을 구성 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-123">Unlike [EditorConfig](#editorconfig) files, global config files can't be used to configure editor style settings for IDEs, such as indent size or whether to trim trailing whitespace.</span></span> <span data-ttu-id="43638-124">대신 프로젝트 수준 분석기 구성 옵션을 지정 하기 위한 용도로만 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-124">Instead, they are designed purely for specifying project-level analyzer configuration options.</span></span>

### <a name="format"></a><span data-ttu-id="43638-125">서식</span><span class="sxs-lookup"><span data-stu-id="43638-125">Format</span></span>

<span data-ttu-id="43638-126">해당 하는 EditorConfig 파일 및 폴더를 식별 하기 위해와 같이 섹션 헤더를 포함 해야 하는 파일과 달리 `[*.cs]` global AnalyzerConfig 파일에는 섹션 머리글이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-126">Unlike EditorConfig files, which must have section headers, such as `[*.cs]`, to identify the applicable files and folders, global AnalyzerConfig files don't have section headers.</span></span> <span data-ttu-id="43638-127">대신 `is_global = true` 일반 파일과 구분 하기 위해 양식의 최상위 항목이 필요 EditorConfig 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-127">Instead, they require a top level entry of the form `is_global = true` to differentiate them from regular EditorConfig files.</span></span> <span data-ttu-id="43638-128">이는 파일의 모든 옵션이 전체 프로젝트에 적용 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43638-128">This indicates that all the options in the file apply to the entire project.</span></span> <span data-ttu-id="43638-129">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="43638-129">For example:</span></span>

```ini
is_global = true
<option_name> = <option_value>
```

### <a name="naming"></a><span data-ttu-id="43638-130">이름 지정</span><span class="sxs-lookup"><span data-stu-id="43638-130">Naming</span></span>

<span data-ttu-id="43638-131">명명 되어야 하는 파일의 경우와 달리 EditorConfig `.editorconfig` 전역 구성 파일에는 특정 이름 또는 확장명이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-131">Unlike EditorConfig files, which must be named `.editorconfig`, global config files do not need to have a specific name or extension.</span></span> <span data-ttu-id="43638-132">그러나 이러한 파일의 이름을로 지정할 경우 `.globalconfig` 하위 폴더를 포함 하 여 현재 폴더 내의 모든 c # 및 Visual Basic 프로젝트에 암시적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-132">However, if you name these files as `.globalconfig` then they will be implicitly applied to all the C# and Visual Basic projects within the current folder, including subfolders.</span></span> <span data-ttu-id="43638-133">그렇지 않은 경우 `GlobalAnalyzerConfigFiles` MSBuild 프로젝트 파일에 항목을 명시적으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-133">Otherwise, you must explicitly add the `GlobalAnalyzerConfigFiles` item to your MSBuild project file:</span></span>

```xml
<ItemGroup>
  <GlobalAnalyzerConfigFiles Include="<path_to_global_analyzer_config>" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="43638-134">최상위 항목은 `is_global = true` 파일의 이름을 지정 하는 경우에도 필요 `.globalconfig` 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-134">The top-level entry `is_global = true` is required even when the file is named `.globalconfig`.</span></span>

### <a name="example"></a><span data-ttu-id="43638-135">예제</span><span class="sxs-lookup"><span data-stu-id="43638-135">Example</span></span>

<span data-ttu-id="43638-136">다음은 프로젝트 수준에서 옵션 및 규칙 심각도를 구성 하는 예제 전역 AnalyzerConfig 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-136">Following is an example global AnalyzerConfig file to configure options and rule severity at the project level:</span></span>

```ini
# Top level entry required to mark this as a global AnalyzerConfig file
is_global = true

# NOTE: No section headers for configuration entries

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="precedence"></a><span data-ttu-id="43638-137">우선 순위</span><span class="sxs-lookup"><span data-stu-id="43638-137">Precedence</span></span>

<span data-ttu-id="43638-138">EditorConfig파일 및 전역 AnalyzerConfig 파일은 모두 각 옵션에 대 한 키-값 쌍을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-138">Both EditorConfig files and global AnalyzerConfig files specify a key-value pair for each option.</span></span> <span data-ttu-id="43638-139">키가 같지만 값이 다른 항목이 여러 개 있는 경우 충돌이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-139">Conflicts arise when there are multiple entries with the same key but different values.</span></span>

### <a name="general-options"></a><span data-ttu-id="43638-140">일반 옵션</span><span class="sxs-lookup"><span data-stu-id="43638-140">General options</span></span>

<span data-ttu-id="43638-141">옵션 간에 충돌이 발생할 경우 충돌을 해결 하는 데 다음과 같은 우선 순위 규칙이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-141">When conflicts arise between options, the following precedence rules are used to resolve the conflicts:</span></span>

- <span data-ttu-id="43638-142">동일한 구성 파일의 일치 하는 항목: 파일에서 나중에 표시 되는 항목은 wins입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-142">Conflicting entries in the same configuration file: The entry that appears later in the file wins.</span></span> <span data-ttu-id="43638-143">단일 파일 내의 충돌 하는 항목과 EditorConfig 단일 전역 AnalyzerConfig 파일 내에 있는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-143">This is true for conflicting entries within a single EditorConfig file and also within a single global AnalyzerConfig file.</span></span>

- <span data-ttu-id="43638-144">두 파일에서 충돌 하 EditorConfig 는 항목: 파일 시스템에서 더 심층적 파일의 항목으로 EditorConfig , 파일 경로가 더 긴 경우 wins.</span><span class="sxs-lookup"><span data-stu-id="43638-144">Conflicting entries in two EditorConfig files: The entry in the EditorConfig file that's deeper in the file system, and hence has a longer file path, wins.</span></span>

- <span data-ttu-id="43638-145">두 전역 AnalyzerConfig 파일의 충돌 항목: 컴파일러 경고가 보고 되 고 두 항목이 모두 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-145">Conflicting entries in two global AnalyzerConfig files: A compiler warning is reported and both entries are ignored.</span></span>

- <span data-ttu-id="43638-146">EditorConfig파일 및 전역 AnalyzerConfig 파일에서 충돌 하는 항목: 파일의 항목은 EditorConfig wins입니다.</span><span class="sxs-lookup"><span data-stu-id="43638-146">Conflicting entries in an EditorConfig file and a Global AnalyzerConfig file: The entry in the EditorConfig file wins.</span></span>

### <a name="severity-options"></a><span data-ttu-id="43638-147">심각도 옵션</span><span class="sxs-lookup"><span data-stu-id="43638-147">Severity options</span></span>

<span data-ttu-id="43638-148">이전 [일반 우선 순위 규칙](#general-options) 은 구성 파일에 지정 된 모든 옵션에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43638-148">The previous [general precedence rules](#general-options) apply for all options specified in configuration files.</span></span> <span data-ttu-id="43638-149">[심각도 구성](configuration-options.md#severity-level) 옵션의 경우 다음과 같은 추가 선행 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-149">For [severity configuration](configuration-options.md#severity-level) options, the following additional precedence rules apply:</span></span>

- <span data-ttu-id="43638-150">컴파일러 옵션 (또는)으로 명령줄에서 지정 된 심각도 옵션은 `/nowarn` `/warnaserror` 항상 및 전역 AnalyzerConfig 파일에 지정 된 [심각도 구성](configuration-options.md#severity-level) 옵션을 재정의 EditorConfig 합니다.</span><span class="sxs-lookup"><span data-stu-id="43638-150">Severity options specified at the command line as compiler options (`/nowarn` or `/warnaserror`) always override [severity configuration](configuration-options.md#severity-level) options specified in EditorConfig and global AnalyzerConfig files.</span></span>

- <span data-ttu-id="43638-151">심각도 옵션은 [규칙 집합](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) 파일을 사용 하 여 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-151">Severity options can also be specified with a [Ruleset](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) file.</span></span> <span data-ttu-id="43638-152">그러나 및 전역 AnalyzerConfig 파일의 경우에는 규칙 집합 파일이 더 이상 사용 되지 않습니다 EditorConfig .</span><span class="sxs-lookup"><span data-stu-id="43638-152">However, rulesets files are deprecated in favor of EditorConfig and global AnalyzerConfig files.</span></span> <span data-ttu-id="43638-153">[규칙 집합 파일을 해당 EditorConfig 파일로 변환](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file)하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-153">It's recommended that you [convert ruleset files to an equivalent EditorConfig file](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file).</span></span> <span data-ttu-id="43638-154">규칙 집합 파일 및 또는 전역 AnalyzerConfig 파일에서 충돌 하는 심각도 항목에 대 한 우선 순위 EditorConfig 는 _정의_ 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43638-154">Precedence for conflicting severity entries from a ruleset file and EditorConfig or global AnalyzerConfig files is _undefined_.</span></span>

- <span data-ttu-id="43638-155">서로 다른 키를 사용 하는 관련 심각도 옵션의 우선 순위 규칙에 대 한 자세한 내용은 (예: 단일 규칙에 대해 서로 다른 심각도가 지정 된 경우 및 해당 규칙이 적용 되는 범주) [코드 분석 구성 옵션](configuration-options.md#precedence)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43638-155">For information about precedence rules for related severity options with different keys, for example, when different severities are specified for a single rule and for the category that rule falls under, see [Configuration options for code analysis](configuration-options.md#precedence).</span></span>

## <a name="see-also"></a><span data-ttu-id="43638-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43638-156">See also</span></span>

- [<span data-ttu-id="43638-157">EditorConfig vs global AnalyzerConfig 디자인 문제</span><span class="sxs-lookup"><span data-stu-id="43638-157">EditorConfig vs global AnalyzerConfig design issue</span></span>](https://github.com/dotnet/roslyn/issues/47707)
