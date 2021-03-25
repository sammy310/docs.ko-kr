---
description: 고급 C# 컴파일러 옵션. 이러한 옵션은 고급 시나리오에서 사용됩니다.
title: C# 컴파일러 옵션 - 고급 시나리오
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- BaseAddress compiler option [C#]
- ChecksumAlgorithm compiler option [C#]
- CodePage compiler option [C#]
- Utf8Output compiler option [C#]
- MainEntryPoint compiler option [C#]
- GenerateFullPaths compiler option [C#]
- FileAlignment compiler option [C#]
- PathMap compiler option [C#]
- PdbFile compiler option [C#]
- ErrorEndLocation compiler option [C#]
- NoStandardLib compiler option [C#]
- PreferredUILang compiler option [C#]
- SubsystemVersion compiler option [C#]
- AdditionalLibPaths compiler option [C#]
- ApplicationConfiguration compiler option [C#]
- ModuleAssemblyName compiler option [C#]
ms.openlocfilehash: 47c84968682e056acdb73805807d907c6bb7c7ee
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104652765"
---
# <a name="advanced-c-compiler-options"></a><span data-ttu-id="2d00d-104">고급 C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="2d00d-104">Advanced C# compiler options</span></span>

<span data-ttu-id="2d00d-105">다음 옵션은 고급 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-105">The following options support advanced scenarios.</span></span> <span data-ttu-id="2d00d-106">새 MSBuild 구문은 **굵게** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-106">The new MSBuild syntax is shown in **Bold**.</span></span> <span data-ttu-id="2d00d-107">이전 `csc.exe` 구문은 `code style`에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-107">The older `csc.exe` syntax is shown in `code style`.</span></span>

- <span data-ttu-id="2d00d-108">**MainEntryPoint**, **StartupObject** / `-main`: 진입점을 포함하는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-108">**MainEntryPoint**, **StartupObject** / `-main`: Specify the type that contains the entry point.</span></span>
- <span data-ttu-id="2d00d-109">**PdbFile** / `-pdb`: 디버그 정보 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-109">**PdbFile** / `-pdb`: Specify debug information file name.</span></span>
- <span data-ttu-id="2d00d-110">**PathMap** / `-pathmap`: 컴파일러에서 출력되는 소스 경로 이름에 대한 매핑을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-110">**PathMap** / `-pathmap`: Specify a mapping for source path names output by the compiler.</span></span>
- <span data-ttu-id="2d00d-111">**ApplicationConfiguration** / `-appconfig`: 어셈블리 바인딩 설정을 포함하는 애플리케이션 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-111">**ApplicationConfiguration** / `-appconfig`: Specify an application configuration file containing assembly binding settings.</span></span>
- <span data-ttu-id="2d00d-112">**AdditionalLibPaths** / `-lib`: 참조를 검색할 추가 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-112">**AdditionalLibPaths** / `-lib`: Specify additional directories to search in for references.</span></span>
- <span data-ttu-id="2d00d-113">**GenerateFullPaths** / `-fullpath`: 컴파일러는 정규화된 경로를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-113">**GenerateFullPaths** / `-fullpath`: Compiler generates fully qualified paths.</span></span>
- <span data-ttu-id="2d00d-114">**PreferredUILang** / `-preferreduilang`: 기본 출력 언어 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-114">**PreferredUILang** / `-preferreduilang`: Specify the preferred output language name.</span></span>
- <span data-ttu-id="2d00d-115">**BaseAddress** / `-baseaddress`: 빌드할 라이브러리의 기준 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-115">**BaseAddress** / `-baseaddress`: Specify the base address for the library to be built.</span></span>
- <span data-ttu-id="2d00d-116">**ChecksumAlgorithm** / `-checksumalgorithm`: PDB에 저장된 소스 파일 체크섬을 계산하기 위한 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-116">**ChecksumAlgorithm** / `-checksumalgorithm` : Specify algorithm for calculating source file checksum stored in PDB.</span></span>
- <span data-ttu-id="2d00d-117">**CodePage** / `-codepage`: 소스 파일을 열 때 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-117">**CodePage** / `-codepage`: Specify the codepage to use when opening source files.</span></span>
- <span data-ttu-id="2d00d-118">**Utf8Output** / `-utf8output`: 컴파일러 메시지를 UTF-8 인코딩으로 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-118">**Utf8Output** / `-utf8output`: Output compiler messages in UTF-8 encoding.</span></span>
- <span data-ttu-id="2d00d-119">**FileAlignment** / `-filealign`: 출력 파일 섹션에 사용되는 맞춤을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-119">**FileAlignment** / `-filealign`: Specify the alignment used for output file sections.</span></span>
- <span data-ttu-id="2d00d-120">**ErrorEndLocation** / `-errorendlocation`: 각 오류의 끝 위치에 해당하는 줄과 열을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-120">**ErrorEndLocation** / `-errorendlocation`: Output line and column of the end location of each error.</span></span>
- <span data-ttu-id="2d00d-121">**NoStandardLib** / `-nostdlib`: 표준 라이브러리 *mscorlib.dll* 을 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-121">**NoStandardLib** / `-nostdlib`: Don't reference standard library *mscorlib.dll*.</span></span>
- <span data-ttu-id="2d00d-122">**SubsystemVersion** / `-subsystemversion`: 이 어셈블리의 하위 시스템 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-122">**SubsystemVersion** / `-subsystemversion`: Specify subsystem version of this assembly.</span></span>
- <span data-ttu-id="2d00d-123">**ModuleAssemblyName** / `-moduleassemblyname`: 이 모듈이 속할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-123">**ModuleAssemblyName** / `-moduleassemblyname`: Name of the assembly that this module will be a part of.</span></span>

## <a name="mainentrypoint-or-startupobject"></a><span data-ttu-id="2d00d-124">MainEntryPoint 또는 StartupObject</span><span class="sxs-lookup"><span data-stu-id="2d00d-124">MainEntryPoint or StartupObject</span></span>

<span data-ttu-id="2d00d-125">이 옵션은 둘 이상의 클래스에 `Main` 메서드가 포함된 경우 프로그램에 대한 진입점을 포함하는 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-125">This option specifies the class that contains the entry point to the program, if more than one class contains a `Main` method.</span></span>

```xml
<StartupObject>MyNamespace.Program</StartupObject>
```

<span data-ttu-id="2d00d-126">또는</span><span class="sxs-lookup"><span data-stu-id="2d00d-126">or</span></span>

```xml
<MainEntryPoint>MyNamespace.Program</MainEntryPoint>
```

<span data-ttu-id="2d00d-127">여기서 `Program`은 `Main` 메서드를 포함하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-127">Where `Program` is the type that contains the `Main` method.</span></span> <span data-ttu-id="2d00d-128">제공된 클래스 이름은 완전히 정규화되어야 하며, 클래스를 포함하는 전체 네임스페이스와 클래스 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-128">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="2d00d-129">예를 들어 `Main` 메서드가 `MyApplication.Core` 네임스페이스의 `Program` 클래스 내에 있는 경우 컴파일러 옵션은 `-main:MyApplication.Core.Program`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-129">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span> <span data-ttu-id="2d00d-130">컴파일에 [`Main`](../../programming-guide/main-and-command-args/index.md) 메서드가 있는 유형이 두 개 이상 포함된 경우 `Main` 메서드를 포함하는 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-130">If your compilation includes more than one type with a [`Main`](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the `Main` method.</span></span>

> [!NOTE]
> <span data-ttu-id="2d00d-131">이 옵션은 프로젝트에 하나 이상의 `Main` 메서드가 포함되어 있더라도 [최상위 문](../../programming-guide/main-and-command-args/top-level-statements.md)을 포함하는 프로젝트에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-131">This option can't be used for a project that includes [top-level statements](../../programming-guide/main-and-command-args/top-level-statements.md), even if that project contains one or more `Main` methods.</span></span>

## <a name="pdbfile"></a><span data-ttu-id="2d00d-132">PdbFile</span><span class="sxs-lookup"><span data-stu-id="2d00d-132">PdbFile</span></span>

<span data-ttu-id="2d00d-133">**PdbFile** 컴파일러 옵션은 디버그 기호 파일의 이름과 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-133">The **PdbFile** compiler option specifies the name and location of the debug symbols file.</span></span>  <span data-ttu-id="2d00d-134">`filename` 값은 디버그 기호 파일의 이름과 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-134">The `filename` value specifies the name and location of the debug symbols file.</span></span>  

```xml
<PdbFile>filename</PdbFile>
```

<span data-ttu-id="2d00d-135">[**DebugType**](code-generation.md#debugtype)을 지정하면 컴파일러는 컴파일러가 출력 파일(.exe 또는 .dll)을 만드는 동일한 디렉터리에 *.pdb* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-135">When you specify [**DebugType**](code-generation.md#debugtype), the compiler will create a *.pdb* file in the same directory where the compiler will create the output file (.exe or .dll).</span></span> <span data-ttu-id="2d00d-136">*.Pdb* 파일은 출력 파일의 이름과 동일한 기본 파일 이름을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-136">The *.pdb* file has the same base file name as the name of the output file.</span></span> <span data-ttu-id="2d00d-137">**PdbFile** 을 사용하면 .pdb 파일에 대해 기본값이 아닌 파일 이름과 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-137">**PdbFile** allows you to specify a non-default file name and location for the .pdb file.</span></span> <span data-ttu-id="2d00d-138">Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-138">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  

## <a name="pathmap"></a><span data-ttu-id="2d00d-139">PathMap</span><span class="sxs-lookup"><span data-stu-id="2d00d-139">PathMap</span></span>

<span data-ttu-id="2d00d-140">**PathMap** 컴파일러 옵션은 실제 경로를 컴파일러에서 출력되는 소스 경로 이름에 매핑하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-140">The **PathMap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span> <span data-ttu-id="2d00d-141">이 옵션은 컴파일러가 실행되는 컴퓨터의 실제 경로 각각을 출력 파일에 써야 하는 해당 경로에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-141">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span> <span data-ttu-id="2d00d-142">다음 예제에서 `path1`은 현재 환경에 있는 원본 파일의 전체 경로이고 `sourcePath1`은 출력 파일에서 `path1`을 대체하는 소스 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-142">In the following example, `path1` is the full path to the source files in the current environment, and `sourcePath1` is the source path substituted for `path1` in any output files.</span></span> <span data-ttu-id="2d00d-143">매핑되는 소스 경로를 여러 개 지정하려면 각각을 세미콜론으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-143">To specify multiple mapped source paths, separate each with a semicolon.</span></span>

```xml
<PathMap>path1=sourcePath1;path2=sourcePath2</PathMap>
```

<span data-ttu-id="2d00d-144">컴파일러가 출력에 소스 경로를 쓰는 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-144">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="2d00d-145">선택적 매개 변수에 <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>를 적용할 때 소스 경로가 인수 대신 사용되는 경우</span><span class="sxs-lookup"><span data-stu-id="2d00d-145">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="2d00d-146">소스 경로가 PDB 파일에 포함된 경우</span><span class="sxs-lookup"><span data-stu-id="2d00d-146">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="2d00d-147">PDB 파일의 경로가 PE(이식 가능한 실행 파일) 파일에 포함된 경우</span><span class="sxs-lookup"><span data-stu-id="2d00d-147">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

## <a name="applicationconfiguration"></a><span data-ttu-id="2d00d-148">ApplicationConfiguration</span><span class="sxs-lookup"><span data-stu-id="2d00d-148">ApplicationConfiguration</span></span>

<span data-ttu-id="2d00d-149">**ApplicationConfiguration** 컴파일러 옵션을 사용하면 C# 애플리케이션이 어셈블리 바인딩 시간에 어셈블리의 애플리케이션 구성(app.config) 파일 위치를 CLR(공용 언어 런타임)에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-149">The **ApplicationConfiguration** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>

```xml
<ApplicationConfiguration>file</ApplicationConfiguration>
```

<span data-ttu-id="2d00d-150">여기서 `file`은 어셈블리 바인딩 설정이 포함된 애플리케이션 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-150">Where `file` is the application configuration file that contains assembly binding settings.</span></span> <span data-ttu-id="2d00d-151">**ApplicationConfiguration** 의 한 가지 용도는 어셈블리가 특정 참조 어셈블리의 .NET Framework 버전과 .NET Framework for Silverlight 버전을 동시에 둘 다 참조해야 하는 고급 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-151">One use of **ApplicationConfiguration** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="2d00d-152">예를 들어 WPF(Windows Presentation Foundation)로 작성된 XAML 디자이너는 디자이너의 사용자 인터페이스를 위한 WPF 데스크톱 및 Silverlight에 포함된 WPF 하위 집합을 둘 다 참조해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-152">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="2d00d-153">같은 디자이너 어셈블리가 두 어셈블리에 모두 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-153">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="2d00d-154">기본적으로, 어셈블리 바인딩 시 두 어셈블리가 동등한 것으로 간주되기 때문에 서로 다른 참조를 사용할 경우 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-154">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="2d00d-155">**ApplicationConfiguration** 컴파일러 옵션을 사용하면 다음 예제와 같이 `<supportPortability>` 태그를 사용하여 기본 동작을 비활성화하는 app.config 파일의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-155">The **ApplicationConfiguration** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>

```xml
<supportPortability PKT="7cec85d7bea7798e" enable="false"/>
```

<span data-ttu-id="2d00d-156">컴파일러는 이 파일 위치를 CLR의 어셈블리 바인딩 논리에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-156">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>

> [!NOTE]
> <span data-ttu-id="2d00d-157">프로젝트에 이미 설정된 app.config 파일을 사용하려면 속성 태그 `<UseAppConfigForCompiler>`를 *.csproj* 파일에 추가하고 해당 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-157">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the *.csproj* file and set its value to `true`.</span></span> <span data-ttu-id="2d00d-158">다른 app.config 파일을 지정하려면 속성 태그 `<AppConfigForCompiler>`를 추가하고 해당 값을 파일 위치로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-158">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>

<span data-ttu-id="2d00d-159">다음 예제에서는 애플리케이션이 두 구현에 모두 있는 .NET Framework 어셈블리의 .NET Framework for Silverlight 구현과 .NET Framework 구현 둘 다에 대한 참조를 사용할 수 있도록 하는 app.config 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-159">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="2d00d-160">**ApplicationConfiguration** 컴파일러 옵션은 이 app.config 파일의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-160">The **ApplicationConfiguration** compiler option specifies the location of this app.config file.</span></span>

```xml
<configuration>
  <runtime>
    <assemblyBinding>
      <supportPortability PKT="7cec85d7bea7798e" enable="false"/>
      <supportPortability PKT="31bf3856ad364e35" enable="false"/>
    </assemblyBinding>
  </runtime>
</configuration>
```

## <a name="additionallibpaths"></a><span data-ttu-id="2d00d-161">AdditionalLibPaths</span><span class="sxs-lookup"><span data-stu-id="2d00d-161">AdditionalLibPaths</span></span>

<span data-ttu-id="2d00d-162">**AdditionalLibPaths** 옵션은 [**References**](inputs.md#references) 옵션으로 참조되는 어셈블리의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-162">The **AdditionalLibPaths** option specifies the location of assemblies referenced with the [**References**](inputs.md#references) option.</span></span>

```xml
<AdditionalLibPaths>dir1[,dir2]</AdditionalLibPaths>
```

<span data-ttu-id="2d00d-163">여기서 `dir1`은 참조된 어셈블리를 현재 작업 디렉터리(컴파일러를 호출하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리에서 찾을 수 없는 경우 컴파일러에서 확인할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-163">Where `dir1` is a directory for the compiler to look in if a referenced assembly isn't found in the current working directory (the directory from which you're invoking the compiler) or in the common language runtime's system directory.</span></span> <span data-ttu-id="2d00d-164">`dir2`는 어셈블리 참조를 검색할 하나 이상의 추가 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-164">`dir2` is one or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="2d00d-165">이름 사이에 공백 없이 디렉터리 이름을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-165">Separate directory names with a comma, and without white space between them.</span></span> <span data-ttu-id="2d00d-166">컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-166">The compiler searches for assembly references that aren't fully qualified in the following order:</span></span>  

1. <span data-ttu-id="2d00d-167">현재 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-167">Current working directory.</span></span>
1. <span data-ttu-id="2d00d-168">공용 언어 런타임 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-168">The common language runtime system directory.</span></span>
1. <span data-ttu-id="2d00d-169">**AdditionalLibPaths** 로 지정된 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="2d00d-169">Directories specified by **AdditionalLibPaths**.</span></span>
1. <span data-ttu-id="2d00d-170">LIB 환경 변수로 지정된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-170">Directories specified by the LIB environment variable.</span></span>

<span data-ttu-id="2d00d-171">**Reference** 를 사용하여 어셈블리 참조를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-171">Use **Reference** to specify an assembly reference.</span></span> <span data-ttu-id="2d00d-172">**AdditionalLibPaths** 는 누적됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-172">**AdditionalLibPaths** is additive.</span></span> <span data-ttu-id="2d00d-173">두 번 이상 지정하면 이전 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-173">Specifying it more than once appends to any prior values.</span></span> <span data-ttu-id="2d00d-174">종속 어셈블리의 경로가 어셈블리 매니페스트에 지정되지 않았으므로 애플리케이션이 전역 어셈블리 캐시에서 어셈블리를 찾아 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-174">Since the path to the dependent assembly isn't specified in the assembly manifest, the application will find and use the assembly in the global assembly cache.</span></span> <span data-ttu-id="2d00d-175">어셈블리를 참조하는 컴파일러는 공용 언어 런타임이 런타임에 어셈블리를 찾아 로드할 수 있음을 의미하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-175">The compiler referencing the assembly doesn't imply the common language runtime can find and load the assembly at runtime.</span></span> <span data-ttu-id="2d00d-176">런타임에서 참조된 어셈블리를 검색하는 방법에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d00d-176">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  

## <a name="generatefullpaths"></a><span data-ttu-id="2d00d-177">GenerateFullPaths</span><span class="sxs-lookup"><span data-stu-id="2d00d-177">GenerateFullPaths</span></span>

<span data-ttu-id="2d00d-178">**GenerateFullPaths** 옵션을 사용하면 컴파일러에서는 컴파일 오류 및 경고 목록을 만들 때 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-178">The **GenerateFullPaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>
  
```Xml
<GenerateFullPaths>true</GenerateFullPaths>
```

<span data-ttu-id="2d00d-179">기본적으로 컴파일 도중 발생하는 오류와 경고에서는 오류가 발견된 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-179">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="2d00d-180">**GenerateFullPaths** 옵션을 사용하면 컴파일러에서는 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-180">The **GenerateFullPaths** option causes the compiler to specify the full path to the file.</span></span> <span data-ttu-id="2d00d-181">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-181">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>

## <a name="preferreduilang"></a><span data-ttu-id="2d00d-182">PreferredUILang</span><span class="sxs-lookup"><span data-stu-id="2d00d-182">PreferredUILang</span></span>

<span data-ttu-id="2d00d-183">**PreferredUILang** 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지 등의 출력을 표시하는 언어를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-183">By using the **PreferredUILang** compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>

```xml
<PreferredUILang>language</PreferredUILang>
```

<span data-ttu-id="2d00d-184">여기서 `language`는 컴파일러 출력에 사용할 언어의 [언어 이름](/windows/desktop/Intl/language-names)입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-184">Where `language` is the [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span> <span data-ttu-id="2d00d-185">**PreferredUILang** 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지와 기타 명령줄 출력에 사용할 언어를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-185">You can use the **PreferredUILang** compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="2d00d-186">해당 언어의 언어 팩이 설치되지 않은 경우 운영 체제의 언어 설정이 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-186">If the language pack for the language isn't installed, the language setting of the operating system is used instead.</span></span>

## <a name="baseaddress"></a><span data-ttu-id="2d00d-187">BaseAddress</span><span class="sxs-lookup"><span data-stu-id="2d00d-187">BaseAddress</span></span>

<span data-ttu-id="2d00d-188">**BaseAddress** 옵션을 사용하면 DLL을 로드할 기본 기준 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-188">The **BaseAddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="2d00d-189">이 옵션을 사용하는 시기와 이유에 대한 자세한 내용은 [Larry Osterman's WebLog](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d00d-189">For more information about when and why to use this option, see [Larry Osterman's WebLog](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span></span>

```xml
<BaseAddress>address</BaseAddress>
```

<span data-ttu-id="2d00d-190">여기서 `address`는 DLL의 기준 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-190">Where `address` is the base address for the DLL.</span></span> <span data-ttu-id="2d00d-191">이 주소는 10진수, 16진수 또는 8진수 숫자로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-191">This address can be specified as a decimal, hexadecimal, or octal number.</span></span> <span data-ttu-id="2d00d-192">DLL의 기본 기준 주소는 .NET 공용 언어 런타임에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-192">The default base address for a DLL is set by the .NET common language runtime.</span></span> <span data-ttu-id="2d00d-193">이 주소의 하위 단어는 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-193">The lower-order word in this address will be rounded.</span></span> <span data-ttu-id="2d00d-194">예를 들어 `0x11110001`을 지정하면 `0x11110000`으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-194">For example, if you specify `0x11110001`, it will be rounded to `0x11110000`.</span></span> <span data-ttu-id="2d00d-195">DLL에 대한 서명 프로세스를 완료하려면 SN.EXE에 -R 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-195">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>

## <a name="checksumalgorithm"></a><span data-ttu-id="2d00d-196">ChecksumAlgorithm</span><span class="sxs-lookup"><span data-stu-id="2d00d-196">ChecksumAlgorithm</span></span>

<span data-ttu-id="2d00d-197">이 옵션은 PDB에서 원본 파일을 인코딩하는 데 사용하는 체크섬 알고리즘을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-197">This option controls the checksum algorithm we use to encode source files in the PDB.</span></span>

```xml
<ChecksumAlgorithm>algorithm</ChecksumAlgorithm>
```

<span data-ttu-id="2d00d-198">`algorithm`은 `SHA1`(기본값) 또는 `SHA256` 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-198">The `algorithm` must be either `SHA1` (default) or `SHA256`.</span></span>

## <a name="codepage"></a><span data-ttu-id="2d00d-199">CodePage</span><span class="sxs-lookup"><span data-stu-id="2d00d-199">CodePage</span></span>

<span data-ttu-id="2d00d-200">이 옵션은 필수 페이지가 시스템에 대한 현재 기본 코드 페이지가 아닌 경우 컴파일 중에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-200">This option specifies which codepage to use during compilation if the required page isn't the current default codepage for the system.</span></span>
  
```xml
<CodePage>id</CodePage>
```

<span data-ttu-id="2d00d-201">여기서 `id`는 컴파일에 있는 모든 소스 코드 파일에 사용할 코드 페이지의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-201">Where `id` is the id of the code page to use for all source code files in the compilation.</span></span> <span data-ttu-id="2d00d-202">컴파일러는 먼저 모든 소스 파일을 UTF-8로 해석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-202">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="2d00d-203">소스 코드 파일이 UTF-8 이외의 인코딩에 있고 7비트 ASCII 문자가 아닌 문자를 사용하는 경우 **CodePage** 옵션을 통해 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-203">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **CodePage** option to specify which code page should be used.</span></span> <span data-ttu-id="2d00d-204">**CodePage** 는 컴파일에 있는 모든 소스 코드 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-204">**CodePage** applies to all source code files in your compilation.</span></span> <span data-ttu-id="2d00d-205">시스템에서 지원되는 코드 페이지를 찾는 방법에 대한 자세한 내용은 [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d00d-205">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>

## <a name="utf8output"></a><span data-ttu-id="2d00d-206">Utf8Output</span><span class="sxs-lookup"><span data-stu-id="2d00d-206">Utf8Output</span></span>

<span data-ttu-id="2d00d-207">**Utf8Output** 옵션은 UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-207">The **Utf8Output** option displays compiler output using UTF-8 encoding.</span></span>

```xml
<Utf8Output>true</Utf8Output>
```

<span data-ttu-id="2d00d-208">일부 국제 구성에서는 컴파일러 출력이 콘솔에 올바르게 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-208">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="2d00d-209">**Utf8Output** 을 사용하고 컴파일러 출력을 파일로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-209">Use **Utf8Output** and redirect compiler output to a file.</span></span>

## <a name="filealignment"></a><span data-ttu-id="2d00d-210">FileAlignment</span><span class="sxs-lookup"><span data-stu-id="2d00d-210">FileAlignment</span></span>

<span data-ttu-id="2d00d-211">**FileAlignment** 옵션을 사용하면 출력 파일의 섹션 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-211">The **FileAlignment** option lets you specify the size of sections in your output file.</span></span> <span data-ttu-id="2d00d-212">유효한 값은 512, 1024, 2048, 4096 및 8192입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-212">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="2d00d-213">이러한 값은 바이트 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-213">These values are in bytes.</span></span>

```xml
<FileAlignment>number</FileAlignment>
```

<span data-ttu-id="2d00d-214">Visual Studio에서 프로젝트에 대한 **빌드** 속성의 **고급** 페이지에서 **FileAlignment** 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-214">You set the **FileAlignment** option from the **Advanced** page of the **Build** properties for your project in Visual Studio.</span></span> <span data-ttu-id="2d00d-215">각 섹션은 **FileAlignment** 값의 배수인 경계에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-215">Each section will be aligned on a boundary that is a multiple of the **FileAlignment** value.</span></span> <span data-ttu-id="2d00d-216">고정된 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-216">There's no fixed default.</span></span> <span data-ttu-id="2d00d-217">**FileAlignment** 를 지정하지 않으면 공용언어 런타임에서 컴파일 시간에 기본값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-217">If **FileAlignment** isn't specified, the common language runtime picks a default at compile time.</span></span> <span data-ttu-id="2d00d-218">섹션 크기를 지정하면 출력 파일의 크기에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-218">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="2d00d-219">섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-219">Modifying section size may be useful for programs that will run on smaller devices.</span></span> <span data-ttu-id="2d00d-220">출력 파일의 섹션에 대한 정보를 확인하려면 [DUMPBIN](/cpp/build/reference/dumpbin-options)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2d00d-220">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>

## <a name="errorendlocation"></a><span data-ttu-id="2d00d-221">ErrorEndLocation</span><span class="sxs-lookup"><span data-stu-id="2d00d-221">ErrorEndLocation</span></span>

<span data-ttu-id="2d00d-222">컴파일러에게 각 오류의 끝 위치에 해당하는 줄과 열을 출력하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-222">Instructs the compiler to output line and column of the end location of each error.</span></span>

```xml
<ErrorEndLocation>filename</ErrorEndLocation>
```

<span data-ttu-id="2d00d-223">기본적으로 컴파일러는 모든 오류 및 경고에 대한 시작 위치를 원본에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-223">By default, the compiler writes the starting location in source for all errors and warnings.</span></span> <span data-ttu-id="2d00d-224">이 옵션을 true로 설정하면 컴파일러는 각 오류 및 경고에 대한 시작 및 끝 위치를 모두 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-224">When this option is set to true, the compiler writes both the starting and end location for each error and warning.</span></span>

## <a name="nostandardlib"></a><span data-ttu-id="2d00d-225">NoStandardLib</span><span class="sxs-lookup"><span data-stu-id="2d00d-225">NoStandardLib</span></span>

<span data-ttu-id="2d00d-226">**NoStandardLib** 를 사용하면 전체 시스템 네임스페이스를 정의하는 mscorlib.dll을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-226">**NoStandardLib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

```xml
<NoStandardLib>true</NoStandardLib>
```

<span data-ttu-id="2d00d-227">고유한 시스템 네임스페이스와 개체를 정의하거나 만들려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-227">Use this option if you want to define or create your own System namespace and objects.</span></span> <span data-ttu-id="2d00d-228">**NoStandardLib** 를 지정하지 않으면 mscorlib.dll을 프로그램으로 가져옵니다(`<NoStandardLib>false</NoStandardLib>` 지정과 동일함).</span><span class="sxs-lookup"><span data-stu-id="2d00d-228">If you don't specify **NoStandardLib**, mscorlib.dll is imported into your program (same as specifying `<NoStandardLib>false</NoStandardLib>`).</span></span>

## <a name="subsystemversion"></a><span data-ttu-id="2d00d-229">SubsystemVersion</span><span class="sxs-lookup"><span data-stu-id="2d00d-229">SubsystemVersion</span></span>

<span data-ttu-id="2d00d-230">실행 파일이 실행되는 하위 시스템의 최소 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-230">Specifies the minimum version of the subsystem on which the executable file runs.</span></span> <span data-ttu-id="2d00d-231">가장 일반적으로, 이 옵션을 사용하면 실행 파일이 이전 버전의 Windows에서 사용할 수 없는 보안 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-231">Most commonly, this option ensures that the executable file can use security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="2d00d-232">하위 시스템 자체를 지정하려면 [**TargetType**](./output.md#targettype) 컴파일러 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-232">To specify the subsystem itself, use the [**TargetType**](./output.md#targettype) compiler option.</span></span>

```xml
<SubsystemVersion>major.minor</SubsystemVersion>
```

<span data-ttu-id="2d00d-233">`major.minor`는 주 버전과 부 버전의 점 표기법으로 표현된 하위 시스템의 필수 최소 버전을 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-233">The `major.minor` specify the minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="2d00d-234">예를 들어 Windows 7 이전 버전의 운영 체제에서는 애플리케이션을 실행할 수 없도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-234">For example, you can specify that an application can't run on an operating system that's older than Windows 7.</span></span> <span data-ttu-id="2d00d-235">이 문서의 뒷부분에 나오는 표에서 설명하는 것처럼 이 옵션의 값을 6.01로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-235">Set the value of this option to 6.01, as the table later in this article describes.</span></span> <span data-ttu-id="2d00d-236">`major` 및 `minor`의 값을 정수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-236">You specify the values for `major` and `minor` as integers.</span></span> <span data-ttu-id="2d00d-237">`minor` 버전에서 선행 0은 버전을 변경하지 않지만 후행 0은 버전을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-237">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="2d00d-238">예를 들어 6.1과 6.01은 동일한 버전을 가리키지만 6.10은 다른 버전을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-238">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="2d00d-239">혼동을 피하기 위해 부 버전을 두 자리로 표현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-239">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

<span data-ttu-id="2d00d-240">다음 표에는 Windows의 일반적인 하위 시스템 버전이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-240">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="2d00d-241">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="2d00d-241">Windows version</span></span>|<span data-ttu-id="2d00d-242">하위 시스템 버전</span><span class="sxs-lookup"><span data-stu-id="2d00d-242">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="2d00d-243">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="2d00d-243">Windows 2000</span></span>|<span data-ttu-id="2d00d-244">5.00</span><span class="sxs-lookup"><span data-stu-id="2d00d-244">5.00</span></span>|
|<span data-ttu-id="2d00d-245">Windows XP</span><span class="sxs-lookup"><span data-stu-id="2d00d-245">Windows XP</span></span>|<span data-ttu-id="2d00d-246">5.01</span><span class="sxs-lookup"><span data-stu-id="2d00d-246">5.01</span></span>|
|<span data-ttu-id="2d00d-247">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="2d00d-247">Windows Server 2003</span></span>|<span data-ttu-id="2d00d-248">5.02</span><span class="sxs-lookup"><span data-stu-id="2d00d-248">5.02</span></span>|
|<span data-ttu-id="2d00d-249">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="2d00d-249">Windows Vista</span></span>|<span data-ttu-id="2d00d-250">6.00</span><span class="sxs-lookup"><span data-stu-id="2d00d-250">6.00</span></span>|
|<span data-ttu-id="2d00d-251">Windows 7</span><span class="sxs-lookup"><span data-stu-id="2d00d-251">Windows 7</span></span>|<span data-ttu-id="2d00d-252">6.01</span><span class="sxs-lookup"><span data-stu-id="2d00d-252">6.01</span></span>|
|<span data-ttu-id="2d00d-253">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="2d00d-253">Windows Server 2008</span></span>|<span data-ttu-id="2d00d-254">6.01</span><span class="sxs-lookup"><span data-stu-id="2d00d-254">6.01</span></span>|
|<span data-ttu-id="2d00d-255">Windows 8</span><span class="sxs-lookup"><span data-stu-id="2d00d-255">Windows 8</span></span>|<span data-ttu-id="2d00d-256">6.02</span><span class="sxs-lookup"><span data-stu-id="2d00d-256">6.02</span></span>|

<span data-ttu-id="2d00d-257">**SubsystemVersion** 컴파일러 옵션의 기본값은 다음 목록의 조건에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-257">The default value of the **SubsystemVersion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="2d00d-258">다음 목록의 컴파일러 옵션이 설정된 경우 기본값은 6.02입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-258">The default value is 6.02 if any compiler option in the following list is set:</span></span>
  - [<span data-ttu-id="2d00d-259">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="2d00d-259">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)
  - [<span data-ttu-id="2d00d-260">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="2d00d-260">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)
  - [<span data-ttu-id="2d00d-261">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="2d00d-261">-platform:arm</span></span>](./platform-compiler-option.md)
- <span data-ttu-id="2d00d-262">MSBuild를 사용하고 .NET Framework 4.5를 대상으로 하며, 이 목록의 앞에서 지정된 컴파일러 옵션 중 하나를 설정하지 않은 경우 기본값은 6.00입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-262">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>
- <span data-ttu-id="2d00d-263">앞의 조건 중 어느 것도 true가 아닌 경우 기본값은 4.00입니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-263">The default value is 4.00 if none of the previous conditions are true.</span></span>

## <a name="moduleassemblyname"></a><span data-ttu-id="2d00d-264">ModuleAssemblyName</span><span class="sxs-lookup"><span data-stu-id="2d00d-264">ModuleAssemblyName</span></span>

<span data-ttu-id="2d00d-265">*.netmodule* 에서 public이 아닌 형식에 액세스할 수 있는 어셈블리 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-265">Specifies the name of an assembly whose non-public types a *.netmodule* can access.</span></span>

```xml
<ModuleAssemblyName>assembly_name</ModuleAssemblyName>
```

<span data-ttu-id="2d00d-266">**ModuleAssemblyName** 은 *.netmodule* 을 빌드할 때와 다음 조건이 충족되는 경우 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-266">**ModuleAssemblyName** should be used when building a *.netmodule*, and where the following conditions are true:</span></span>

- <span data-ttu-id="2d00d-267">*.netmodule* 은 기존 어셈블리의 public이 아닌 형식에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-267">The *.netmodule* needs access to non-public types in an existing assembly.</span></span>
- <span data-ttu-id="2d00d-268">.netmodule을 빌드할 어셈블리의 이름을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-268">You know the name of the assembly into which the .netmodule will be built.</span></span>
- <span data-ttu-id="2d00d-269">기존 어셈블리는 friend 어셈블리(friend assembly)에 *.netmodule* 을 빌드할 어셈블리에 대한 액세스를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="2d00d-269">The existing assembly has granted friend assembly access to the assembly into which the .*netmodule* will be built.</span></span>

<span data-ttu-id="2d00d-270">.netmodule 빌드 방법에 대한 자세한 내용은 **module** 의 [**TargetType**](output.md#targettype) 옵션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d00d-270">For more information on building a .netmodule, see [**TargetType**](output.md#targettype) option of **module**.</span></span> <span data-ttu-id="2d00d-271">friend 어셈블리에 대한 자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d00d-271">For more information on friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>
