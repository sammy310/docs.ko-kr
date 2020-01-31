---
title: .NET Core 3.1의 새로운 기능
description: .NET Core 3.1에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 0905cbebb2d966570be4ac3aefb40f4377b97061
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742581"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="f7825-103">.NET Core 3.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f7825-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="f7825-104">이 문서에서는 .NET Core 3.1의 새로운 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="f7825-105">이 릴리스에는 작지만 중요한 수정 내용에 중점을 둔 .NET Core 3.0의 소소한 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="f7825-106">.NET Core 3.1의 가장 중요한 기능은 [LTS(장기 지원)](#long-term-support) 릴리스라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="f7825-107">Visual Studio 2019을 사용하는 경우 .NET Core 3.1 프로젝트와 함께 작동하려면 [Visual Studio 2019 버전 16.4](https://visualstudio.microsoft.com/downloads/)를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="f7825-108">Visual Studio의 새로운 기능에 대한 자세한 내용은 [Visual Studio 2019 버전 16.4의 새로운 기능](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7825-108">For more information on what's new in Visual Studio, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="f7825-109">또한 Mac용 Visual Studio는 Mac용 Visual Studio 8.4에서 .NET Core 3.1을 지원 및 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="f7825-110">릴리스에 대한 자세한 내용은 [.NET Core 3.1 공지](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7825-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="f7825-111">Windows, macOS 또는 Linux에서 [.NET Core 3.1을 다운로드하여 시작](https://dotnet.microsoft.com/download/dotnet-core/3.1)하세요.</span><span class="sxs-lookup"><span data-stu-id="f7825-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="f7825-112">장기 지원</span><span class="sxs-lookup"><span data-stu-id="f7825-112">Long-term support</span></span>

<span data-ttu-id="f7825-113">.NET Core 3.1은 향후 3년 동안 Microsoft를 지원하는 LTS 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="f7825-114">사용 중인 앱을 .NET Core 3.1로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="f7825-115">다른 주요 릴리스의 현재 수명 주기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="f7825-116">Release</span><span class="sxs-lookup"><span data-stu-id="f7825-116">Release</span></span> | <span data-ttu-id="f7825-117">참고</span><span class="sxs-lookup"><span data-stu-id="f7825-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="f7825-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f7825-118">.NET Core 3.0</span></span> | <span data-ttu-id="f7825-119">2020년 3월 3일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="f7825-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="f7825-120">.NET Core 2.2</span></span> | <span data-ttu-id="f7825-121">2019년 12월 23일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="f7825-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f7825-122">.NET Core 2.1</span></span> | <span data-ttu-id="f7825-123">2021년 8월 21일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="f7825-124">자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7825-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="f7825-125">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f7825-125">Windows Forms</span></span>

<span data-ttu-id="f7825-126">*Windows만 해당*</span><span class="sxs-lookup"><span data-stu-id="f7825-126">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="f7825-127">Windows Forms 관련 호환성이 손상되는 변경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-127">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="f7825-128">레거시 컨트롤은 Visual Studio Designer Toolbox에서 잠시 사용할 수 없었던 Windows Forms에 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-128">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="f7825-129">이러한 항목은 .NET Framework 2.0에서 새 컨트롤로 바뀌었으며</span><span class="sxs-lookup"><span data-stu-id="f7825-129">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="f7825-130">.NET Core 3.1용 데스크톱 SDK에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-130">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="f7825-131">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f7825-131">Removed control</span></span> | <span data-ttu-id="f7825-132">권장된 대체</span><span class="sxs-lookup"><span data-stu-id="f7825-132">Recommended replacement</span></span> | <span data-ttu-id="f7825-133">제거된 연결 API</span><span class="sxs-lookup"><span data-stu-id="f7825-133">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="f7825-134">DataGrid</span><span class="sxs-lookup"><span data-stu-id="f7825-134">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="f7825-135">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="f7825-135">DataGridCell</span></span><br/><span data-ttu-id="f7825-136">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="f7825-136">DataGridRow</span></span><br/><span data-ttu-id="f7825-137">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="f7825-137">DataGridTableCollection</span></span><br/><span data-ttu-id="f7825-138">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="f7825-138">DataGridColumnCollection</span></span><br/><span data-ttu-id="f7825-139">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="f7825-139">DataGridTableStyle</span></span><br/><span data-ttu-id="f7825-140">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="f7825-140">DataGridColumnStyle</span></span><br/><span data-ttu-id="f7825-141">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="f7825-141">DataGridLineStyle</span></span><br/><span data-ttu-id="f7825-142">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="f7825-142">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="f7825-143">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="f7825-143">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="f7825-144">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="f7825-144">DataGridBoolColumn</span></span><br/><span data-ttu-id="f7825-145">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="f7825-145">DataGridTextBox</span></span><br/><span data-ttu-id="f7825-146">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="f7825-146">GridColumnStylesCollection</span></span><br/><span data-ttu-id="f7825-147">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="f7825-147">GridTableStylesCollection</span></span><br/><span data-ttu-id="f7825-148">HitTestType</span><span class="sxs-lookup"><span data-stu-id="f7825-148">HitTestType</span></span> |
| <span data-ttu-id="f7825-149">ToolBar</span><span class="sxs-lookup"><span data-stu-id="f7825-149">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="f7825-150">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="f7825-150">ToolBarAppearance</span></span> |
| <span data-ttu-id="f7825-151">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="f7825-151">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="f7825-152">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="f7825-152">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="f7825-153">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="f7825-153">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="f7825-154">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="f7825-154">ToolBarButtonStyle</span></span><br/><span data-ttu-id="f7825-155">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="f7825-155">ToolBarTextAlign</span></span> |
| <span data-ttu-id="f7825-156">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="f7825-156">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="f7825-157">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="f7825-157">MenuItemCollection</span></span> |
| <span data-ttu-id="f7825-158">MainMenu</span><span class="sxs-lookup"><span data-stu-id="f7825-158">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="f7825-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="f7825-159">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="f7825-160">애플리케이션을 .NET Core 3.1로 업데이트하고 대체 컨트롤로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-160">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="f7825-161">컨트롤을 바꾸는 것은 기본적으로 유형을 "찾고 대체"하는 간단한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-161">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="f7825-162">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="f7825-162">C++/CLI</span></span>

<span data-ttu-id="f7825-163">*Windows만 해당*</span><span class="sxs-lookup"><span data-stu-id="f7825-163">*Windows only*</span></span>

<span data-ttu-id="f7825-164">C++/CLI("관리되는 C++"라고도 함) 프로젝트를 만들기 위한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-164">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="f7825-165">이러한 프로젝트에서 생성된 이진 파일은 .NET Core 3.0 이상 버전과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-165">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="f7825-166">Visual Studio 2019 버전 16.4에서 C++/CLI에 대한 지원을 추가하려면 [C++ 워크로드로 데스크톱 개발](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-166">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="f7825-167">이 워크로드는 Visual Studio에 다음의 두 가지 템플릿을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-167">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="f7825-168">CLR 클래스 라이브러리(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="f7825-168">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="f7825-169">CLR 빈 프로젝트(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="f7825-169">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7825-170">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f7825-170">Next steps</span></span>

- [<span data-ttu-id="f7825-171">.NET Core 3.0 및 3.1 간의 호환성이 손상되는 변경을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-171">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="f7825-172">Windows Forms 앱용 .NET Core 3.1의 주요 변경 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f7825-172">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
