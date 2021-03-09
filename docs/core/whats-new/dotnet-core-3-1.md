---
title: .NET Core 3.1의 새로운 기능
description: .NET Core 3.1에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 8d086c5c595197894e01a347f82b2c6341263fc5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104967"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="870b0-103">.NET Core 3.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="870b0-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="870b0-104">이 문서에서는 .NET Core 3.1의 새로운 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="870b0-105">이 릴리스에는 작지만 중요한 수정 내용에 중점을 둔 .NET Core 3.0의 소소한 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="870b0-106">.NET Core 3.1의 가장 중요한 기능은 [LTS(장기 지원)](#long-term-support) 릴리스라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="870b0-107">Visual Studio 2019를 사용하는 경우 .NET Core 3.1 프로젝트와 함께 작동하려면 [Visual Studio 2019 버전 16.4 이상](https://visualstudio.microsoft.com/downloads/)으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4 or later](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="870b0-108">Visual Studio 버전 16.4의 새로운 기능에 대한 내용은 [Visual Studio 2019 버전 16.4의 새로운 기능](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="870b0-108">For information on what's new in Visual Studio version 16.4, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="870b0-109">또한 Mac용 Visual Studio는 Mac용 Visual Studio 8.4에서 .NET Core 3.1을 지원 및 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="870b0-110">릴리스에 대한 자세한 내용은 [.NET Core 3.1 공지](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="870b0-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="870b0-111">Windows, macOS 또는 Linux에서 [.NET Core 3.1을 다운로드하여 시작](https://dotnet.microsoft.com/download/dotnet/3.1)하세요.</span><span class="sxs-lookup"><span data-stu-id="870b0-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="870b0-112">장기 지원</span><span class="sxs-lookup"><span data-stu-id="870b0-112">Long-term support</span></span>

<span data-ttu-id="870b0-113">.NET Core 3.1은 향후 3년 동안 Microsoft를 지원하는 LTS 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="870b0-114">사용 중인 앱을 .NET Core 3.1로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="870b0-115">다른 주요 릴리스의 현재 수명 주기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="870b0-116">Release</span><span class="sxs-lookup"><span data-stu-id="870b0-116">Release</span></span> | <span data-ttu-id="870b0-117">참고</span><span class="sxs-lookup"><span data-stu-id="870b0-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="870b0-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="870b0-118">.NET Core 3.0</span></span> | <span data-ttu-id="870b0-119">2020년 3월 3일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="870b0-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="870b0-120">.NET Core 2.2</span></span> | <span data-ttu-id="870b0-121">2019년 12월 23일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="870b0-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="870b0-122">.NET Core 2.1</span></span> | <span data-ttu-id="870b0-123">2021년 8월 21일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="870b0-124">자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="870b0-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="macos-apphost-and-notarization"></a><span data-ttu-id="870b0-125">macOS appHost 및 공증</span><span class="sxs-lookup"><span data-stu-id="870b0-125">macOS appHost and notarization</span></span>

<span data-ttu-id="870b0-126">‘macOS만 해당’ </span><span class="sxs-lookup"><span data-stu-id="870b0-126">*macOS only*</span></span>

<span data-ttu-id="870b0-127">공증된 macOS용 .NET Core SDK 3.1부터, appHost 설정이 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-127">Starting with the notarized .NET Core SDK 3.1 for macOS, the appHost setting is disabled by default.</span></span> <span data-ttu-id="870b0-128">자세한 내용은 [macOS Catalina 공증과 이것이 .NET Core 다운로드 및 프로젝트에 미치는 영향](../install/macos-notarization-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="870b0-128">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="870b0-129">appHost 설정이 사용하도록 설정된 경우, 빌드 또는 게시할 때 .NET Core가 네이티브 Mach-O 실행 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-129">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="870b0-130">앱을 `dotnet run` 명령을 사용하여 소스 코드에서 실행하거나 Mach-O 실행 파일을 직접 시작하면 앱이 appHost 컨텍스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-130">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="870b0-131">사용자가 appHost 없이 [프레임워크 종속](../deploying/index.md#publish-framework-dependent) 앱을 시작할 수 있는 유일한 방법은 `dotnet <filename.dll>` 명령을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-131">Without the appHost, the only way a user can start a [framework-dependent](../deploying/index.md#publish-framework-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="870b0-132">appHost는 앱을 [자체 포함](../deploying/index.md#publish-self-contained) 방식으로 게시하면 항상 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="870b0-133">appHost는 다음과 같이 프로젝트 수준에서 구성하거나 `-p:UseAppHost` 매개 변수를 사용하여 특정 `dotnet` 명령에 대해 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-133">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="870b0-134">프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="870b0-134">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="870b0-135">명령줄 매개 변수</span><span class="sxs-lookup"><span data-stu-id="870b0-135">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="870b0-136">`UseAppHost` 설정에 대한 자세한 내용은 [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost)(Microsoft.NET.Sdk의 MSBuild 속성)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="870b0-136">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="870b0-137">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="870b0-137">Windows Forms</span></span>

<span data-ttu-id="870b0-138">*Windows만 해당*</span><span class="sxs-lookup"><span data-stu-id="870b0-138">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="870b0-139">Windows Forms 관련 호환성이 손상되는 변경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-139">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="870b0-140">레거시 컨트롤은 Visual Studio Designer Toolbox에서 잠시 사용할 수 없었던 Windows Forms에 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-140">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="870b0-141">이러한 항목은 .NET Framework 2.0에서 새 컨트롤로 바뀌었으며</span><span class="sxs-lookup"><span data-stu-id="870b0-141">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="870b0-142">.NET Core 3.1용 데스크톱 SDK에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-142">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="870b0-143">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="870b0-143">Removed control</span></span> | <span data-ttu-id="870b0-144">권장된 대체</span><span class="sxs-lookup"><span data-stu-id="870b0-144">Recommended replacement</span></span> | <span data-ttu-id="870b0-145">제거된 연결 API</span><span class="sxs-lookup"><span data-stu-id="870b0-145">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="870b0-146">DataGrid</span><span class="sxs-lookup"><span data-stu-id="870b0-146">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="870b0-147">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="870b0-147">DataGridCell</span></span><br/><span data-ttu-id="870b0-148">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="870b0-148">DataGridRow</span></span><br/><span data-ttu-id="870b0-149">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="870b0-149">DataGridTableCollection</span></span><br/><span data-ttu-id="870b0-150">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="870b0-150">DataGridColumnCollection</span></span><br/><span data-ttu-id="870b0-151">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="870b0-151">DataGridTableStyle</span></span><br/><span data-ttu-id="870b0-152">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="870b0-152">DataGridColumnStyle</span></span><br/><span data-ttu-id="870b0-153">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="870b0-153">DataGridLineStyle</span></span><br/><span data-ttu-id="870b0-154">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="870b0-154">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="870b0-155">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="870b0-155">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="870b0-156">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="870b0-156">DataGridBoolColumn</span></span><br/><span data-ttu-id="870b0-157">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="870b0-157">DataGridTextBox</span></span><br/><span data-ttu-id="870b0-158">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="870b0-158">GridColumnStylesCollection</span></span><br/><span data-ttu-id="870b0-159">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="870b0-159">GridTableStylesCollection</span></span><br/><span data-ttu-id="870b0-160">HitTestType</span><span class="sxs-lookup"><span data-stu-id="870b0-160">HitTestType</span></span> |
| <span data-ttu-id="870b0-161">ToolBar</span><span class="sxs-lookup"><span data-stu-id="870b0-161">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="870b0-162">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="870b0-162">ToolBarAppearance</span></span> |
| <span data-ttu-id="870b0-163">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="870b0-163">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="870b0-164">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="870b0-164">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="870b0-165">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="870b0-165">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="870b0-166">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="870b0-166">ToolBarButtonStyle</span></span><br/><span data-ttu-id="870b0-167">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="870b0-167">ToolBarTextAlign</span></span> |
| <span data-ttu-id="870b0-168">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="870b0-168">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="870b0-169">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="870b0-169">MenuItemCollection</span></span> |
| <span data-ttu-id="870b0-170">MainMenu</span><span class="sxs-lookup"><span data-stu-id="870b0-170">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="870b0-171">MenuItem</span><span class="sxs-lookup"><span data-stu-id="870b0-171">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="870b0-172">애플리케이션을 .NET Core 3.1로 업데이트하고 대체 컨트롤로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-172">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="870b0-173">컨트롤을 바꾸는 것은 기본적으로 유형을 "찾고 대체"하는 간단한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-173">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="870b0-174">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="870b0-174">C++/CLI</span></span>

<span data-ttu-id="870b0-175">*Windows만 해당*</span><span class="sxs-lookup"><span data-stu-id="870b0-175">*Windows only*</span></span>

<span data-ttu-id="870b0-176">C++/CLI("관리되는 C++"라고도 함) 프로젝트를 만들기 위한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-176">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="870b0-177">이러한 프로젝트에서 생성된 이진 파일은 .NET Core 3.0 이상 버전과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-177">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="870b0-178">Visual Studio 2019 버전 16.4에서 C++/CLI에 대한 지원을 추가하려면 [C++ 워크로드로 데스크톱 개발](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-178">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="870b0-179">이 워크로드는 Visual Studio에 다음의 두 가지 템플릿을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-179">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="870b0-180">CLR 클래스 라이브러리(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="870b0-180">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="870b0-181">CLR 빈 프로젝트(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="870b0-181">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="870b0-182">다음 단계</span><span class="sxs-lookup"><span data-stu-id="870b0-182">Next steps</span></span>

- [<span data-ttu-id="870b0-183">.NET Core 3.0 및 3.1 간의 호환성이 손상되는 변경을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-183">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.1.md)
- [<span data-ttu-id="870b0-184">Windows Forms 앱용 .NET Core 3.1의 주요 변경 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="870b0-184">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
