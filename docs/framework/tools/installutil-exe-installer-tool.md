---
title: Installutil.exe(설치 관리자 도구)
description: Installutil.exe 즉, 설치 관리자 도구를 사용합니다. 아 이 도구를 사용하면 특정 어셈블리에서 설치 관리자 구성 요소를 실행하여 서버 리소스를 설치하고 제거할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- uninstalling server resources
- removing server resources
- status information for installation
- installation progress reports
- installing server resources
- Installer tool
- Installutil.exe
- files, Installer tool
- progress information for installation
- reporting installation progress
ms.assetid: 3f9d0533-f895-4897-b4ea-528284e0241d
ms.openlocfilehash: 042e5f64a7a863173db9c4e601d3152b0df46d97
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164439"
---
# <a name="installutilexe-installer-tool"></a><span data-ttu-id="2b6db-104">Installutil.exe(설치 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="2b6db-104">Installutil.exe (Installer Tool)</span></span>

<span data-ttu-id="2b6db-105">설치 관리자 도구는 특정 어셈블리에서 설치 관리자 구성 요소를 실행하는 방법으로 서버 리소스를 설치하고 제거하는 데 사용할 수 있는 명령줄 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-105">The Installer tool is a command-line utility that allows you to install and uninstall server resources by executing the installer components in specified assemblies.</span></span> <span data-ttu-id="2b6db-106">이 도구는 <xref:System.Configuration.Install> 네임스페이스의 클래스와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-106">This tool works in conjunction with classes in the <xref:System.Configuration.Install> namespace.</span></span>

<span data-ttu-id="2b6db-107">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="2b6db-108">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="2b6db-109">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6db-109">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="2b6db-110">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-110">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="2b6db-111">구문</span><span class="sxs-lookup"><span data-stu-id="2b6db-111">Syntax</span></span>

```console
installutil [/u[ninstall]] [options] assembly [[options] assembly] ...
```

## <a name="parameters"></a><span data-ttu-id="2b6db-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b6db-112">Parameters</span></span>

|<span data-ttu-id="2b6db-113">인수</span><span class="sxs-lookup"><span data-stu-id="2b6db-113">Argument</span></span>|<span data-ttu-id="2b6db-114">Description</span><span class="sxs-lookup"><span data-stu-id="2b6db-114">Description</span></span>|
|--------------|-----------------|
|`assembly`|<span data-ttu-id="2b6db-115">설치 관리자 구성 요소를 실행할 어셈블리의 파일 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-115">The file name of the assembly in which to execute the installer components.</span></span> <span data-ttu-id="2b6db-116">`/AssemblyName` 옵션을 사용하여 어셈블리의 강력한 이름을 지정하려면 이 매개 변수를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-116">Omit this parameter if you want to specify the assembly's strong name by using the `/AssemblyName` option.</span></span>|

<a name="options"></a>

## <a name="options"></a><span data-ttu-id="2b6db-117">옵션</span><span class="sxs-lookup"><span data-stu-id="2b6db-117">Options</span></span>

|<span data-ttu-id="2b6db-118">옵션</span><span class="sxs-lookup"><span data-stu-id="2b6db-118">Option</span></span>|<span data-ttu-id="2b6db-119">설명</span><span class="sxs-lookup"><span data-stu-id="2b6db-119">Description</span></span>|
|------------|-----------------|
|`/h[elp]`<br /><br /> <span data-ttu-id="2b6db-120">또는</span><span class="sxs-lookup"><span data-stu-id="2b6db-120">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="2b6db-121">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-121">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="2b6db-122">`/help` *assembly*</span><span class="sxs-lookup"><span data-stu-id="2b6db-122">`/help` *assembly*</span></span><br /><br /> <span data-ttu-id="2b6db-123">또는</span><span class="sxs-lookup"><span data-stu-id="2b6db-123">-or-</span></span><br /><br /> <span data-ttu-id="2b6db-124">`/?` *assembly*</span><span class="sxs-lookup"><span data-stu-id="2b6db-124">`/?` *assembly*</span></span>|<span data-ttu-id="2b6db-125">InstallUtil.exe에 대한 명령 구문 및 옵션과 함께 지정된 어셈블리 내의 개별 설치 프로그램에서 재구성한 추가 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-125">Displays additional options recognized by individual installers within the specified assembly, along with command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="2b6db-126">이 옵션은 각 설치 관리자 구성 요소의 <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> 속성에서 반환되는 텍스트를 InstallUtil.exe의 도움말 텍스트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-126">This option adds the text returned by each installer component's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property to the help text of InstallUtil.exe.</span></span>|
|<span data-ttu-id="2b6db-127">`/AssemblyName` "*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="2b6db-127">`/AssemblyName` "*assemblyName*</span></span><br /><br /> <span data-ttu-id="2b6db-128">,Version=*major.minor.build.revision*</span><span class="sxs-lookup"><span data-stu-id="2b6db-128">,Version=*major.minor.build.revision*</span></span><br /><br /> <span data-ttu-id="2b6db-129">,Culture=*locale*</span><span class="sxs-lookup"><span data-stu-id="2b6db-129">,Culture=*locale*</span></span><br /><br /> <span data-ttu-id="2b6db-130">,PublicKeyToken=*publicKeyToken*"</span><span class="sxs-lookup"><span data-stu-id="2b6db-130">,PublicKeyToken=*publicKeyToken*"</span></span>|<span data-ttu-id="2b6db-131">전역 어셈블리 캐시에 등록해야 하는 어셈블리의 이름 또는 강력한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-131">Specifies the strong name of an assembly, which must be registered in the global assembly cache.</span></span> <span data-ttu-id="2b6db-132">어셈블리의 버전, 문화권 및 공개 키 토큰을 사용하여 어셈블리 이름을 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-132">The assembly name must be fully qualified with the version, culture, and public key token of the assembly.</span></span> <span data-ttu-id="2b6db-133">정규화된 어셈블리 이름은 따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-133">The fully qualified name must be surrounded by quotes.</span></span><br /><br /> <span data-ttu-id="2b6db-134">예를 들어, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"은 정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-134">For example, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" is a fully qualified assembly name.</span></span>|
|<span data-ttu-id="2b6db-135">`/InstallStateDir=[` *directoryName* `]`</span><span class="sxs-lookup"><span data-stu-id="2b6db-135">`/InstallStateDir=[` *directoryName* `]`</span></span>|<span data-ttu-id="2b6db-136">어셈블리를 제거하는 데 사용한 데이터가 포함된 .InstallState 파일의 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-136">Specifies the directory of the .InstallState file that contains the data used to uninstall the assembly.</span></span> <span data-ttu-id="2b6db-137">기본 디렉터리는 어셈블리가 들어 있는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-137">The default is the directory that contains the assembly.</span></span>|
|<span data-ttu-id="2b6db-138">`/LogFile=`[*filename*]</span><span class="sxs-lookup"><span data-stu-id="2b6db-138">`/LogFile=`[*filename*]</span></span>|<span data-ttu-id="2b6db-139">설치 진행 정보가 기록되는 로그 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-139">Specifies the name of the log file where installation progress is recorded.</span></span> <span data-ttu-id="2b6db-140">기본적으로 `/LogFile` 옵션을 생략하면 *assemblyname*.InstallLog라는 로그 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-140">By default, if the `/LogFile` option is omitted, a log file named *assemblyname*.InstallLog is created.</span></span> <span data-ttu-id="2b6db-141">*filename*을 생략하면 로그 파일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-141">If *filename* is omitted, no log file is generated.</span></span>|
|<span data-ttu-id="2b6db-142">`/LogToConsole`={`true`&#124;`false`}</span><span class="sxs-lookup"><span data-stu-id="2b6db-142">`/LogToConsole`={`true`&#124;`false`}</span></span>|<span data-ttu-id="2b6db-143">`true`인 경우 출력을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-143">If `true`, displays output to the console.</span></span> <span data-ttu-id="2b6db-144">`false`(기본값)이면 출력 내용을 콘솔에 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-144">If `false` (the default), suppresses output to the console.</span></span>|
|`/ShowCallStack`|<span data-ttu-id="2b6db-145">설치 도중 어느 한 지점에서 예외가 발생하면 호출 스택을 로그 파일에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-145">Outputs the call stack to the log file if an exception occurs at any point during installation.</span></span>|
|<span data-ttu-id="2b6db-146">`/u`[`ninstall`]</span><span class="sxs-lookup"><span data-stu-id="2b6db-146">`/u`[`ninstall`]</span></span>|<span data-ttu-id="2b6db-147">지정된 어셈블리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-147">Uninstalls the specified assemblies.</span></span> <span data-ttu-id="2b6db-148">다른 옵션과 달리, `/u`는 명령줄에서 옵션이 표시되는 위치에 관계없이 모든 어셈블리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-148">Unlike the other options, `/u` applies to all assemblies regardless of where the option appears on the command line.</span></span>|

<a name="cmdline"></a>

## <a name="additional-installer-options"></a><span data-ttu-id="2b6db-149">추가 설치 관리자 옵션</span><span class="sxs-lookup"><span data-stu-id="2b6db-149">Additional Installer Options</span></span>

<span data-ttu-id="2b6db-150">어셈블리 내에서 사용되는 개별 설치 관리자는 [옵션](#options) 섹션에서 나열한 옵션 이외의 옵션도 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-150">Individual installers used within an assembly may recognize options in addition to those listed in the [Options](#options) section.</span></span> <span data-ttu-id="2b6db-151">이 옵션에 대해 자세히 알아보려면 InstallUtil.exe를 `/?` 또는 `/help` 옵션에 따라 명령줄에서 어셈블리 경로와 함께 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-151">To learn about these options, run InstallUtil.exe with the paths of the assemblies on the command line along with the `/?` or `/help` option.</span></span> <span data-ttu-id="2b6db-152">이러한 옵션을 지정하려면 InstallUtil.exe에서 인식하는 옵션과 함께 명령줄에 이 옵션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-152">To specify these options, you include them on the command line along with the options recognized by InstallUtil.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="2b6db-153">개별 설치 관리자 구성 요소에서 지원하는 옵션에 대한 도움말 텍스트는 <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> 속성에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-153">Help text on the options supported by individual installer components is returned by the <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2b6db-154">명령줄에 입력한 개별 옵션은 <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType> 속성에서 프로그래밍 방식으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-154">The individual options that have been entered on the command line are accessible programmatically from the <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="2b6db-155">모든 옵션 및 명령줄 매개 변수는 설치 로그 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-155">All options and command-line parameters are written to the installation log file.</span></span> <span data-ttu-id="2b6db-156">그러나 일부 설치 관리자 구성 요소에서 인식되는 `/Password` 매개 변수를 사용하는 경우 암호 정보는 8개의 별표(\*)로 대체되며 로그 파일에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-156">However, if you use the `/Password` parameter, which is recognized by some installer components, the password information will be replaced by eight asterisks (\*) and will not appear in the log file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b6db-157">경우에 따라 설치 관리자에 전달되는 매개 변수는 중요하거나 개인적으로 식별할 수 있는 정보를 포함할 수 있으며 기본적으로 일반 텍스트 파일로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-157">In some cases, parameters passed to the installer may include sensitive or personally identifiable information, which, by default, is written to a plain text log file.</span></span> <span data-ttu-id="2b6db-158">이 동작을 방지하려면 명령줄에서 Installutil.exe를 실행한 후 `/LogFile=`(*filename* 인수 없음)을 지정하여 로그 파일을 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-158">To prevent this behavior, you can suppress the log file by specifying `/LogFile=` (with no *filename* argument) after Installutil.exe on the command line.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b6db-159">설명</span><span class="sxs-lookup"><span data-stu-id="2b6db-159">Remarks</span></span>

<span data-ttu-id="2b6db-160">.NET Framework 애플리케이션은 일반적인 프로그램 파일과 애플리케이션 배포 시 만들어야 하는 메시지 큐, 이벤트 로그 및 성능 카운터 등의 관련 리소스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-160">.NET Framework applications consist of traditional program files and associated resources, such as message queues, event logs, and performance counters that must be created when the application is deployed.</span></span> <span data-ttu-id="2b6db-161">어셈블리의 설치 관리자 구성 요소를 사용하면 애플리케이션 설치 시에는 이러한 리소스를 만들고, 애플리케이션 제거 시에는 이러한 리소스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-161">You can use an assembly's installer components to create these resources when your application is installed and to remove them when your application is uninstalled.</span></span> <span data-ttu-id="2b6db-162">Installutil.exe를 사용하여 이러한 설치 관리자 구성 요소를 감지하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-162">Installutil.exe detects and executes these installer components.</span></span>

<span data-ttu-id="2b6db-163">동일한 명령줄에서 여러 개의 어셈블리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-163">You can specify multiple assemblies on the same command line.</span></span> <span data-ttu-id="2b6db-164">어셈블리 이름 앞에 나타나는 모든 옵션은 해당 어셈블리의 설치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-164">Any option that occurs before an assembly name applies to that assembly's installation.</span></span> <span data-ttu-id="2b6db-165">`/u` 및 `/AssemblyName`을 제외한 옵션은 누적되지만 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-165">Except for `/u` and `/AssemblyName`, options are cumulative but overridable.</span></span> <span data-ttu-id="2b6db-166">즉, 한 어셈블리에 대해 지정된 옵션은 이 옵션이 새 값으로 지정되지 않는 한 모든 후속 어셈블리에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-166">That is, options specified for one assembly apply to all subsequent assemblies unless the option is specified with a new value.</span></span>

<span data-ttu-id="2b6db-167">아무 옵션도 지정하지 않고 어셈블리에 대해 Installutil.exe를 실행하면 다음 세 개의 파일이 해당 어셈블리의 디렉터리에 놓입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-167">If you run Installutil.exe against an assembly without specifying any options, it places the following three files into the assembly's directory:</span></span>

- <span data-ttu-id="2b6db-168">InstallUtil.InstallLog - 설치 진행에 대한 일반적인 설명이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-168">InstallUtil.InstallLog - Contains a general description of the installation progress.</span></span>

- <span data-ttu-id="2b6db-169">*assemblyname*.InstallLog - 설치 프로세스의 커밋 단계와 관련된 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-169">*assemblyname*.InstallLog - Contains information specific to the commit phase of the installation process.</span></span> <span data-ttu-id="2b6db-170">커밋 단계에 대한 자세한 내용은 <xref:System.Configuration.Install.Installer.Commit%2A> 메서드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b6db-170">For more information about the commit phase, see the <xref:System.Configuration.Install.Installer.Commit%2A> method.</span></span>

- <span data-ttu-id="2b6db-171">*assemblyname*.InstallState - 어셈블리를 제거하는 데 사용되는 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-171">*assemblyname*.InstallState - Contains data used to uninstall the assembly.</span></span>

<span data-ttu-id="2b6db-172">Installutil.exe에서 리플렉션을 사용하여 지정된 어셈블리를 검사하고 <xref:System.Configuration.Install.Installer>에 대한 <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> 특성 집합을 가지는 모든 `true` 형식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-172">Installutil.exe uses reflection to inspect the specified assemblies and to find all <xref:System.Configuration.Install.Installer> types that have the <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> attribute set to `true`.</span></span> <span data-ttu-id="2b6db-173">그런 다음 도구는 <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> 형식의 각 인스턴스에서 <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> 또는 <xref:System.Configuration.Install.Installer> 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-173">The tool then executes either the <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> or the <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> method on each instance of the <xref:System.Configuration.Install.Installer> type.</span></span> <span data-ttu-id="2b6db-174">Installutil.exe를 사용하면 트랜잭션 방식으로 설치를 수행할 수도 있습니다. 즉, 어셈블리가 하나라도 설치되지 않으면 다른 모든 어셈블리의 설치도 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-174">Installutil.exe performs installation in a transactional manner; that is, if one of the assemblies fails to install, it rolls back the installations of all other assemblies.</span></span> <span data-ttu-id="2b6db-175">그러나 제거 시에는 트랜잭션 방식이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-175">Uninstall is not transactional.</span></span>

<span data-ttu-id="2b6db-176">Installutil.exe를 사용하면 서명이 연기된 어셈블리를 설치하거나 제거할 수 없지만 강력한 이름의 어셈블리는 설치하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-176">Installutil.exe cannot install or uninstall delay-signed assemblies, but it can install or uninstall strong-named assemblies.</span></span>

<span data-ttu-id="2b6db-177">.NET Framework 버전 2.0부터는 32비트 버전의 CLR(공용 언어 런타임)이 32비트 버전의 설치 관리자 도구에만 제공되며, 64비트 버전의 CLR은 32비트 및 64비트 버전의 설치 관리자 도구 모두에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-177">Starting with the .NET Framework version 2.0, the 32-bit version of the common language runtime (CLR) ships with only the 32-bit version of the Installer tool, but the 64-bit version of the CLR ships with both 32-bit and 64-bit versions of the Installer tool.</span></span> <span data-ttu-id="2b6db-178">64비트 CLR을 사용할 경우에는 32비트 설치 관리자 도구를 사용하여 32비트 어셈블리를 설치하고, 64비트 설치 관리자 도구를 사용하여 64비트 및 MSIL(Microsoft Intermediate Language) 어셈블리를 설치하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b6db-178">When using the 64-bit CLR, use the 32-bit Installer tool to install 32-bit assemblies, and the 64-bit Installer tool to install 64-bit and Microsoft intermediate language (MSIL) assemblies.</span></span> <span data-ttu-id="2b6db-179">두 버전의 설치 관리자 도구가 동일하게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-179">Both versions of the Installer tool behave the same.</span></span>

<span data-ttu-id="2b6db-180">Installutil.exe는 C++ 컴파일러에 의해 생성되는 포함된 네이티브 코드를 인식할 수 없으므로 C++를 사용하여 만든 Windows 서비스를 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-180">You cannot use Installutil.exe to deploy a Windows service that was created by using C++, because Installutil.exe cannot recognize the embedded native code that is produced by the C++ compiler.</span></span> <span data-ttu-id="2b6db-181">Installutil.exe로 만든 C++ Windows 서비스를 배포하려고 시도하면 <xref:System.BadImageFormatException>과 같은 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-181">If you try to deploy a C++ Windows service with Installutil.exe, an exception such as <xref:System.BadImageFormatException> will be thrown.</span></span> <span data-ttu-id="2b6db-182">이 시나리오를 사용하여 작업하려면 C++ 모듈로 서비스 코드를 이동한 후 설치 관리자 개체를 C# 또는 Visual Basic에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-182">To work with this scenario, move the service code to a C++ module, and then write the installer object in C# or Visual Basic.</span></span>

## <a name="examples"></a><span data-ttu-id="2b6db-183">예</span><span class="sxs-lookup"><span data-stu-id="2b6db-183">Examples</span></span>

<span data-ttu-id="2b6db-184">다음 명령은 InstallUtil.exe에 대한 옵션 및 명령 구문에 대한 설명을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-184">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span>

```console
installutil /?
```

<span data-ttu-id="2b6db-185">다음 명령은 InstallUtil.exe에 대한 옵션 및 명령 구문에 대한 설명을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-185">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="2b6db-186">도움말 텍스트가 설치 관리자의 <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> 속성에 지정된 경우 `myAssembly.exe`의 설치 관리자 구성 요소에 의해 지원되는 옵션 목록 및 설명도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-186">It also displays a description and list of options supported by the installer components in `myAssembly.exe` if help text has been assigned to the installer's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span>

```console
installutil /? myAssembly.exe
```

<span data-ttu-id="2b6db-187">다음 명령을 사용하여 어셈블리 `myAssembly.exe`에서 설치 관리자 구성 요소를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-187">The following command executes the installer components in the assembly `myAssembly.exe`.</span></span>

```console
installutil myAssembly.exe
```

<span data-ttu-id="2b6db-188">다음 명령은 `/AssemblyName` 스위치와 정규화된 이름을 사용하여 어셈블리에서 설치 관리자 구성 요소를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-188">The following command executes the installer components in an assembly by using the `/AssemblyName` switch and a fully qualified name.</span></span>

```console
installutil /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="2b6db-189">다음 명령은 파일 이름으로 지정된 어셈블리와 강력한 이름으로 지정된 어셈블리에서 설치 관리자 구성 요소를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-189">The following command executes the installer components in an assembly specified by file name and in an assembly specified by strong name.</span></span> <span data-ttu-id="2b6db-190">파일 이름에서 지정한 모든 어셈블리는 `/AssemblyName` 옵션을 재정의할 수 없으므로 명령줄에서 강력한 이름으로 지정된 어셈블리보다 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-190">Note that all assemblies specified by file name must precede assemblies specified by strong name on the command line, because the `/AssemblyName` option cannot be overridden.</span></span>

```console
installutil myAssembly.exe /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="2b6db-191">다음 명령을 사용하여 어셈블리 `myAssembly.exe`에서 설치 제거 관리자 구성 요소를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-191">The following command executes the uninstaller components in the assembly `myAssembly.exe`.</span></span>

```console
installutil /u myAssembly.exe
```

<span data-ttu-id="2b6db-192">다음 명령은 어셈블리 `myAssembly1.exe` 및 `myAssembly2.exe`에서 제거 프로그램 구성 요소를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-192">The following command executes the uninstaller components in the assemblies `myAssembly1.exe` and `myAssembly2.exe`.</span></span>

```console
installutil myAssembly1.exe /u myAssembly2.exe
```

<span data-ttu-id="2b6db-193">명령줄에서 `/u` 옵션의 위치는 중요하지 않기 때문에 다음 명령과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-193">Because the position of the `/u` option on the command line is not important, this is equivalent to the following command.</span></span>

```console
installutil /u myAssembly1.exe myAssembly2.exe
```

<span data-ttu-id="2b6db-194">다음 명령을 사용하여 어셈블리 `myAssembly.exe`에서 설치 관리자를 실행하고 진행 정보가 `myLog.InstallLog`에 기록되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-194">The following command executes the installers in the assembly `myAssembly.exe` and specifies that progress information will be written to `myLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe
```

<span data-ttu-id="2b6db-195">다음 명령은 `myAssembly.exe` 어셈블리에서 설치 관리자를 실행하며 진행 정보를 `myLog.InstallLog`에 작성하도록 지정하며 설치 관리자의 사용자 지정 `/reg` 옵션을 통해 시스템 레지스트리로 업데이트하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-195">The following command executes the installers in the assembly `myAssembly.exe`, specifies that progress information should be written to `myLog.InstallLog`, and uses the installers' custom `/reg` option to specify that updates should be made to the system registry.</span></span>

```console
installutil /LogFile=myLog.InstallLog /reg=true myAssembly.exe
```

<span data-ttu-id="2b6db-196">다음 명령은 `myAssembly.exe` 어셈블리에서 설치 관리자를 실행하고 설치 관리자의 사용자 지정 `/email` 옵션을 사용하여 사용자의 전자 메일 주소를 지정하고 로그 파일에 대한 출력을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-196">The following command executes the installers in the assembly `myAssembly.exe`, uses the installer's custom `/email` option to specify the user's email address, and suppresses output to the log file.</span></span>

```console
installutil /LogFile= /email=admin@mycompany.com myAssembly.exe
```

<span data-ttu-id="2b6db-197">다음 명령은 `myAssembly.exe`에 대한 설치 진행률을 `myLog.InstallLog`에 쓰고, `myTestAssembly.exe`에 대한 설치 진행률을 `myTestLog.InstallLog`에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2b6db-197">The following command writes the installation progress for `myAssembly.exe` to `myLog.InstallLog` and writes the progress for `myTestAssembly.exe` to `myTestLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe /LogFile=myTestLog.InstallLog myTestAssembly.exe
```

## <a name="see-also"></a><span data-ttu-id="2b6db-198">참조</span><span class="sxs-lookup"><span data-stu-id="2b6db-198">See also</span></span>

- <xref:System.Configuration.Install>
- [<span data-ttu-id="2b6db-199">도구</span><span class="sxs-lookup"><span data-stu-id="2b6db-199">Tools</span></span>](index.md)
- [<span data-ttu-id="2b6db-200">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="2b6db-200">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
