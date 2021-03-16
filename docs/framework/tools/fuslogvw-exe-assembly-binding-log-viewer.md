---
title: Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)
description: Fuslogvw.exe 즉, 어셈블리 바인딩 로그 뷰어를 사용합니다. 이 뷰어는 .NET에서 런타임에 어셈블리를 찾을 수 없는 이유를 진단하는 데 도움이 되는 어셈블리 바인딩 세부 정보를 보여줍니다.
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: d9c028507c19ef8599e58b38dcdf15af2ede1dee
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259280"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a><span data-ttu-id="74f93-104">Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)</span><span class="sxs-lookup"><span data-stu-id="74f93-104">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>

<span data-ttu-id="74f93-105">어셈블리 바인딩 로그 뷰어는 어셈블리 바인딩에 대한 자세한 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-105">The Assembly Binding Log Viewer displays details for assembly binds.</span></span> <span data-ttu-id="74f93-106">이 정보를 검토하면 .NET Framework에서 런타임에 어셈블리를 찾지 못하는 이유를 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-106">This information helps you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span> <span data-ttu-id="74f93-107">이러한 오류는 일반적으로 어셈블리가 잘못된 위치에 배포되었거나 네이티브 이미지가 더 이상 유효하지 않거나 버전 번호 또는 문화권이 일치하지 않기 때문에 일어납니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-107">These failures are usually the result of an assembly deployed to the wrong location, a native image that is no longer valid, or a mismatch in version numbers or cultures.</span></span> <span data-ttu-id="74f93-108">공용 언어 런타임의 어셈블리 찾기 오류는 일반적으로 애플리케이션에서 <xref:System.TypeLoadException>으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-108">The common language runtime's failure to locate an assembly typically shows up as a <xref:System.TypeLoadException> in your application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f93-109">Fuslogvw.exe는 관리자 권한으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-109">You must run fuslogvw.exe with administrator privileges.</span></span>

<span data-ttu-id="74f93-110">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="74f93-111">도구를 실행하려면 관리자 자격 증명으로 [개발자용 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-111">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell) with administrator credentials.</span></span>

<span data-ttu-id="74f93-112">명령 프롬프트에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-112">At the command prompt, enter the following command:</span></span>

```console
fuslogvw
```

<span data-ttu-id="74f93-113">뷰어에서는 실패한 각 어셈블리 바인딩의 엔트리를 표시하고</span><span class="sxs-lookup"><span data-stu-id="74f93-113">The viewer displays an entry for each failed assembly bind.</span></span> <span data-ttu-id="74f93-114">각 오류에 대해 뷰어에서 다음을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-114">For each failure, the viewer describes:</span></span>

- <span data-ttu-id="74f93-115">바인딩을 시작한 애플리케이션의 이름</span><span class="sxs-lookup"><span data-stu-id="74f93-115">the application that initiated the bind</span></span>
- <span data-ttu-id="74f93-116">바인딩이 대상으로 하는 어셈블리(이름, 버전, 문화권 및 공개 키 포함)</span><span class="sxs-lookup"><span data-stu-id="74f93-116">the assembly the bind is for, including name, version, culture and public key</span></span>
- <span data-ttu-id="74f93-117">오류의 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="74f93-117">the date and time of the failure</span></span>

## <a name="how-to"></a><span data-ttu-id="74f93-118">사용법</span><span class="sxs-lookup"><span data-stu-id="74f93-118">How to...</span></span>

- [<span data-ttu-id="74f93-119">로그 위치 보기 변경</span><span class="sxs-lookup"><span data-stu-id="74f93-119">Change the log location view</span></span>](#change-the-log-location-view)
- [<span data-ttu-id="74f93-120">특정 오류 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="74f93-120">View details about a specific failure</span></span>](#view-details-about-a-specific-failure)
- [<span data-ttu-id="74f93-121">항목 삭제</span><span class="sxs-lookup"><span data-stu-id="74f93-121">Delete entries</span></span>](#delete-entries)
- [<span data-ttu-id="74f93-122">사용자 인터페이스 새로 고침</span><span class="sxs-lookup"><span data-stu-id="74f93-122">Refresh the user interface</span></span>](#refresh-the-user-interface)
- [<span data-ttu-id="74f93-123">로그 설정 변경</span><span class="sxs-lookup"><span data-stu-id="74f93-123">Change the log settings</span></span>](#change-the-log-settings)
- [<span data-ttu-id="74f93-124">정보 대화 상자 보기</span><span class="sxs-lookup"><span data-stu-id="74f93-124">View the About dialog</span></span>](#view-the-about-dialog)

### <a name="change-the-log-location-view"></a><span data-ttu-id="74f93-125">로그 위치 보기 변경</span><span class="sxs-lookup"><span data-stu-id="74f93-125">Change the log location view</span></span>

1. <span data-ttu-id="74f93-126">**기본값** 옵션 단추를 선택하여 모든 애플리케이션 종류에 대한 바인딩 실패를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-126">Select the **Default** option button to view bind failures for all application types.</span></span> <span data-ttu-id="74f93-127">기본적으로 로그 항목은 디스크의 사용자별 디렉터리에서 wininet 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-127">By default, log entries are stored in per-user directories on disk in the wininet cache.</span></span>

2. <span data-ttu-id="74f93-128">**사용자 지정** 옵션 단추를 선택하여 사용자 지정 디렉터리의 바인딩 오류를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-128">Select the **Custom** option button to view bind failures in a custom directory that you specify.</span></span> <span data-ttu-id="74f93-129">유효한 디렉터리 이름을 위해 **로그 설정** 대화 상자에서 사용자 지정 로그 위치를 설정하여 런타임에 로그를 저장할 사용자 지정 위치를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-129">You must specify the custom location where you want the runtime to store the logs by setting the custom log location in the **Log Settings** dialog to a valid directory name.</span></span> <span data-ttu-id="74f93-130">이 디렉터리는 런타임에 생성되는 파일만 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-130">This directory should be clean, and only contain files that the runtime generates.</span></span> <span data-ttu-id="74f93-131">실패하여 로그를 남길 수 있는 실행 파일이 들어 있으면 도구에서 실행 파일과 같은 이름으로 디렉터리를 만들려고 시도하므로 실패한 경우 로그를 남길 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-131">If it contains an executable that generates a failure to be logged, the failure will not be logged because the tool tries to create a directory with the same name as the executable.</span></span> <span data-ttu-id="74f93-132">또한 로그 위치에서 실행 파일을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-132">In addition, an attempt to run an executable from the log location will fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74f93-133">사용자 지정 바인딩 위치보다 기본 바인딩 위치를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-133">The default bind location is preferable to the custom bind location.</span></span> <span data-ttu-id="74f93-134">런타임은 기본 바인딩 위치를 wininet 캐시에 저장하기 때문에 자동으로 이 위치를 비웁니다. 그러나 사용자 지정 바인딩 위치를 지정하는 경우에는 사용자가 직접 비워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-134">The runtime stores the default bind location in the wininet cache, and therefore automatically cleans it out. If you specify a custom bind location, you are responsible for cleaning it out.</span></span>

### <a name="view-details-about-a-specific-failure"></a><span data-ttu-id="74f93-135">특정 오류 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="74f93-135">View details about a specific failure</span></span>

1. <span data-ttu-id="74f93-136">뷰어에서 원하는 엔트리의 애플리케이션 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-136">Select the application name of the desired entry in the viewer.</span></span>

2. <span data-ttu-id="74f93-137">**로그 보기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-137">Click the **View Log** button.</span></span> <span data-ttu-id="74f93-138">또는 선택한 엔트리를 두 번 클릭할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-138">Alternately, you can double-click the selected entry.</span></span>

    <span data-ttu-id="74f93-139">다음과 같이 선택한 바인딩 오류에 대한 자세한 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-139">The tool displays the following details about the selected bind failure:</span></span>

    - <span data-ttu-id="74f93-140">"파일을 찾을 수 없습니다." 또는 "버전이 일치하지 않습니다." 등 바인딩이 실패한 특정 원인</span><span class="sxs-lookup"><span data-stu-id="74f93-140">The specific reason the bind failed, such as "file not found" or "version mismatch".</span></span>

    - <span data-ttu-id="74f93-141">이름, 애플리케이션의 루트 디렉터리(AppBase) 및 개인 검색 경로(있는 경우)의 설명 등을 포함하여 바인딩을 시작한 애플리케이션에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="74f93-141">Information about the application that initiated the bind, including its name, the application's root directory (AppBase), and a description of the private search path, if there is one.</span></span>

    - <span data-ttu-id="74f93-142">도구에서 찾고 있는 어셈블리의 ID</span><span class="sxs-lookup"><span data-stu-id="74f93-142">The identity of the assembly the tool is looking for.</span></span>

    - <span data-ttu-id="74f93-143">적용된 애플리케이션, 게시자 또는 관리자 버전 정책 설명</span><span class="sxs-lookup"><span data-stu-id="74f93-143">A description of any Application, Publisher, or Administrator version policies that have been applied.</span></span>

    - <span data-ttu-id="74f93-144">[전역 어셈블리 캐시](../app-domains/gac.md)에 어셈블리가 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="74f93-144">Whether the assembly was found in the [global assembly cache](../app-domains/gac.md).</span></span>

    - <span data-ttu-id="74f93-145">검색하는 모든 URL 목록</span><span class="sxs-lookup"><span data-stu-id="74f93-145">A list of all probing URLs.</span></span>

<span data-ttu-id="74f93-146">다음 샘플 로그 엔트리는 실패한 어셈블리 바인딩에 대한 자세한 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-146">The following sample log entry shows detailed information about a failed assembly bind.</span></span>

```output
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe
--- A detailed error log follows.

=== Pre-bind state information ===
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
 (Fully-specified)
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\
LOG: Initial PrivatePath = NULL
LOG: Dynamic Base = NULL
LOG: Cache Base = NULL
LOG: AppName = NULL
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
===

LOG: Processing DEVPATH.
LOG: DEVPATH is not set. Falling through to regular bind.
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.
LOG: All probing URLs attempted and failed.
```

### <a name="delete-entries"></a><span data-ttu-id="74f93-147">항목 삭제</span><span class="sxs-lookup"><span data-stu-id="74f93-147">Delete entries</span></span>

<span data-ttu-id="74f93-148">로그에서 단일 항목을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="74f93-148">To delete a single entry from the log:</span></span>

1. <span data-ttu-id="74f93-149">뷰어에서 엔트리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-149">Select an entry in the viewer.</span></span>

2. <span data-ttu-id="74f93-150">**항목 삭제** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-150">Click the **Delete Entry** button.</span></span>

<span data-ttu-id="74f93-151">로그에서 모든 항목을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="74f93-151">To delete all entries from the log:</span></span>

- <span data-ttu-id="74f93-152">**모두 삭제** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-152">Click the **Delete All** button.</span></span>

### <a name="refresh-the-user-interface"></a><span data-ttu-id="74f93-153">사용자 인터페이스 새로 고침</span><span class="sxs-lookup"><span data-stu-id="74f93-153">Refresh the user interface</span></span>

- <span data-ttu-id="74f93-154">**새로 고침** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-154">Click the **Refresh** button.</span></span> <span data-ttu-id="74f93-155">뷰어는 실행 중인 동안에는 새 로그 엔트리를 자동으로 검색하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-155">The viewer does not automatically detect new log entries while it is running.</span></span> <span data-ttu-id="74f93-156">새 항목을 표시하려면 **새로 고침** 단추를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-156">You must use the **Refresh** button to display them.</span></span>

### <a name="change-the-log-settings"></a><span data-ttu-id="74f93-157">로그 설정 변경</span><span class="sxs-lookup"><span data-stu-id="74f93-157">Change the log settings</span></span>

<span data-ttu-id="74f93-158">**설정** 단추를 클릭하여 **로그 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-158">Click the **Settings** button to open the **Log Settings** dialog.</span></span>

### <a name="view-the-about-dialog"></a><span data-ttu-id="74f93-159">정보 대화 상자 보기</span><span class="sxs-lookup"><span data-stu-id="74f93-159">View the About dialog</span></span>

<span data-ttu-id="74f93-160">**정보** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-160">Click the **About** button.</span></span>

## <a name="binding-logs-for-native-images"></a><span data-ttu-id="74f93-161">네이티브 이미지에 대한 바인딩 로그</span><span class="sxs-lookup"><span data-stu-id="74f93-161">Binding logs for native images</span></span>

<span data-ttu-id="74f93-162">기본적으로 Fuslogvw.exe는 일반 어셈블리 바인딩 요청을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-162">By default, Fuslogvw.exe logs normal assembly bind requests.</span></span> <span data-ttu-id="74f93-163">또는 [Ngen.exe(네이티브 이미지 생성기)](ngen-exe-native-image-generator.md)를 사용하여 생성된 네이티브 이미지에 대한 어셈블리 바인딩을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-163">Alternatively, you can log assembly binds for native images that were created using the [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md).</span></span>

### <a name="log-assembly-binds-for-native-images"></a><span data-ttu-id="74f93-164">네이티브 이미지에 대한 어셈블리 바인딩 기록</span><span class="sxs-lookup"><span data-stu-id="74f93-164">Log assembly binds for native images</span></span>

- <span data-ttu-id="74f93-165">**로그 범주** 그룹에서 **네이티브 이미지** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-165">In the **Log Categories** group, select the **Native Images** option button.</span></span>

<span data-ttu-id="74f93-166">다음 로그에서는 애플리케이션에 대한 네이티브 이미지가 생성되었을 때 종속성이 존재하지 않아 발생한 실패를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-166">The following log shows a failure caused by a dependency that did not exist when the native image was created for the application.</span></span> <span data-ttu-id="74f93-167">런타임에서의 종속성과 Ngen.exe가 실행될 때의 종속성이 다른 경우 네이티브 이미지에 대한 바인딩을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-167">If the dependencies at run time differ from the dependencies when Ngen.exe is run, binding to a native image is not allowed.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\App.exe
--- A detailed error log follows.

LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\App.exe.
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.
WRN: No matching native image found.
LOG: Bind to native image assembly did not succeed. Use IL image.
```

<span data-ttu-id="74f93-168">다음 로그에서는 애플리케이션이 실행되었을 때의 컴퓨터 보안 설정이 네이티브 이미지가 생성되었을 때의 보안 설정과 달라 발생하는 네이티브 이미지 바인딩 실패를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-168">The following log shows a native image binding failure that occurred because the security settings on the computer when the application was run were different from the security settings at the time the native image was created.</span></span>

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***

The operation failed.
Bind result: hr = 0x80004005. Unspecified error

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\Application101622.exe
--- A detailed error log follows.

LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\Application101622.exe.
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Dependency evaluation succeeded.
LOG: Validation of dependencies succeeded.
LOG: Start loading all the dependencies into load context.
LOG: Loading of dependencies succeeded.
LOG: Bind to native image succeeded.
Native image has correct version information.
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.
Discarding native image.
```

## <a name="the-log-settings-dialog"></a><span data-ttu-id="74f93-169">로그 설정 대화 상자</span><span class="sxs-lookup"><span data-stu-id="74f93-169">The Log Settings dialog</span></span>

<span data-ttu-id="74f93-170">**로그 설정** 대화 상자를 사용하여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-170">You can use the **Log Settings** dialog to perform the following actions.</span></span>

### <a name="to-disable-logging"></a><span data-ttu-id="74f93-171">로깅을 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="74f93-171">To disable logging</span></span>

- <span data-ttu-id="74f93-172">**로그 사용 안 함** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-172">Select the **Log disabled** option button.</span></span>  <span data-ttu-id="74f93-173">이 옵션은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-173">Note that this option is selected by default.</span></span>

### <a name="to-log-assembly-binds-in-exceptions"></a><span data-ttu-id="74f93-174">예외에 어셈블리 바인딩을 기록하려면</span><span class="sxs-lookup"><span data-stu-id="74f93-174">To log assembly binds in exceptions</span></span>

- <span data-ttu-id="74f93-175">**예외 텍스트로 기록** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-175">Select the **Log in exception text** option button.</span></span> <span data-ttu-id="74f93-176">덜 자세한 fusion 로그 정보만 예외 텍스트로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-176">Only the least detailed fusion log information is logged in exception text.</span></span> <span data-ttu-id="74f93-177">전체 정보를 보려면 다른 설정 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-177">To view full information, use one of the other settings.</span></span>

  <span data-ttu-id="74f93-178">도메인 중립적으로 로드되는 어셈블리에 대한 중요 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74f93-178">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

### <a name="to-log-assembly-bind-failures"></a><span data-ttu-id="74f93-179">어셈블리 바인딩 실패를 기록하려면</span><span class="sxs-lookup"><span data-stu-id="74f93-179">To log assembly bind failures</span></span>

- <span data-ttu-id="74f93-180">**디스크에 바인드 실패 기록** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-180">Select the **Log bind failures to disk** option button.</span></span>

  <span data-ttu-id="74f93-181">도메인 중립적으로 로드되는 어셈블리에 대한 중요 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74f93-181">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

### <a name="to-log-all-assembly-binds"></a><span data-ttu-id="74f93-182">모든 어셈블리 바인딩을 기록하려면</span><span class="sxs-lookup"><span data-stu-id="74f93-182">To log all assembly binds</span></span>

- <span data-ttu-id="74f93-183">**디스크에 모든 바인드 기록** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-183">Select the **Log all binds to disk** option button.</span></span>

  <span data-ttu-id="74f93-184">도메인 중립적으로 로드되는 어셈블리에 대한 중요 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74f93-184">See the Important note regarding assemblies that are loaded as domain neutral.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f93-185">예를 들어 <xref:System.AppDomainSetup.LoaderOptimization%2A> 속성을 <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> 또는 <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>로 설정하여 어셈블리가 도메인 중립적으로 로드되는 경우 로깅을 설정하면 경우에 따라 메모리가 누수될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-185">When an assembly is loaded as domain neutral, for example by setting the <xref:System.AppDomainSetup.LoaderOptimization%2A> property to <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> or <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, turning on logging might leak memory in some cases.</span></span> <span data-ttu-id="74f93-186">도메인 중립 모듈이 애플리케이션 도메인에 로드되었을 때 로그 엔트리가 만들어지고 나중에 애플리케이션 도메인이 언로드되면 이러한 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-186">This can happen if a log entry is made when a domain-neutral module is loaded into an application domain, and later the application domain is unloaded.</span></span> <span data-ttu-id="74f93-187">프로세스가 끝날 때까지는 로그 엔트리가 해제되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-187">The log entry might not be released until the process ends.</span></span> <span data-ttu-id="74f93-188">로깅이 자동으로 설정되는 디버거도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-188">Some debuggers automatically turn on logging.</span></span>

### <a name="to-enable-a-custom-log-path"></a><span data-ttu-id="74f93-189">사용자 지정 로그 경로를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="74f93-189">To enable a custom log path</span></span>

1. <span data-ttu-id="74f93-190">**사용자 지정 로그 경로 사용** 옵션 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-190">Select the **Enable custom log path** option button.</span></span>

2. <span data-ttu-id="74f93-191">**사용자 지정 로그 경로** 텍스트 상자에 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-191">Enter the path into the **Custom log path** text box.</span></span>

> [!NOTE]
> <span data-ttu-id="74f93-192">[어셈블리 바인딩 로그 뷰어(Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md)에서는 IE(Internet Explorer) 캐시를 사용하여 바인딩 로그를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-192">The [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) uses the Internet Explorer (IE) cache to store its binding log.</span></span> <span data-ttu-id="74f93-193">가끔 나타나는 IE 캐시 손상으로 인해 [어셈블리 바인딩 로그 뷰어(Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md)에서는 보기 창에 새 바인딩 로그를 표시하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-193">Due to occasional corruption in the IE cache, the [Assembly Binding Log Viewer (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) can sometimes stop showing new binding logs in the viewing window.</span></span> <span data-ttu-id="74f93-194">이 손상으로 인해 .NET 바인딩 인프라(fusion)는 바인딩 로그에 쓰거나 바인딩 로그에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-194">As a result of this corruption, the .NET binding infrastructure (fusion) cannot write to or read from the binding log.</span></span> <span data-ttu-id="74f93-195">사용자 지정 로그 경로를 사용하는 경우에는 이 문제가 발생하지 않습니다.  손상을 해결하고 fusion이 바인딩 로그를 다시 표시하도록 하려면 IE 옵션 대화 상자 내에서 임시 인터넷 파일을 삭제하여 IE 캐시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-195">(This issue is not encountered if you use a custom log path.)  To fix the corruption and allow fusion to show binding logs again, clear the IE cache by deleting temporary internet files from within the IE Internet Options dialog.</span></span>
>
> <span data-ttu-id="74f93-196">관리되지 않는 애플리케이션에서 `IHostAssemblyManager` 및 `IHostAssemblyStore` 인터페이스를 구현하여 공용 언어 런타임을 호스팅하는 경우 로그 엔트리를 wininet 캐시에 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-196">If your unmanaged application hosts the common language runtime by implementing the `IHostAssemblyManager` and `IHostAssemblyStore` interfaces, log entries can't be stored in the wininet cache.</span></span> <span data-ttu-id="74f93-197">이러한 인터페이스를 구현하는 사용자 지정 호스트에 대한 로그 엔트리를 보려면 대체 로그 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-197">To view log entries for custom hosts that implement these interfaces, you must specify an alternate log path.</span></span>

### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a><span data-ttu-id="74f93-198">Windows 앱 컨테이너에서 실행되는 앱에 대해 로깅을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="74f93-198">To enable logging for apps running in the Windows app container</span></span>

1. <span data-ttu-id="74f93-199">이전 절차에서 설명한 대로, 사용자 지정 로그 경로를 활성화시킵니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-199">Enable a custom log path, as described in the previous procedure.</span></span> <span data-ttu-id="74f93-200">기본적으로, Windows 앱 컨테이너에서 실행되는 응용 프로그램은 하드 디스크에 대한 액세스가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-200">By default, apps that are running in the Windows app container have limited access to the hard disk.</span></span> <span data-ttu-id="74f93-201">지정한 디렉터리는 응용 프로그램 컨테이너에 있는 모든 응용 프로그램에 대한 읽기/쓰기 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-201">The directory you specify will have read/write access for all apps in the app container.</span></span>

2. <span data-ttu-id="74f93-202">**로깅 몰입 활성화** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-202">Select the **Enable immersive logging** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74f93-203">Windows 8 이상에서만 상자가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="74f93-203">This box is enabled only on Windows 8 or later.</span></span>

## <a name="see-also"></a><span data-ttu-id="74f93-204">참조</span><span class="sxs-lookup"><span data-stu-id="74f93-204">See also</span></span>

- <xref:System.TypeLoadException>
- [<span data-ttu-id="74f93-205">도구</span><span class="sxs-lookup"><span data-stu-id="74f93-205">Tools</span></span>](index.md)
- [<span data-ttu-id="74f93-206">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="74f93-206">Global Assembly Cache</span></span>](../app-domains/gac.md)
- [<span data-ttu-id="74f93-207">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="74f93-207">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="74f93-208">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="74f93-208">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
