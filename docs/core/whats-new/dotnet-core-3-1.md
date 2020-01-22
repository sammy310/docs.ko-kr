---
title: .NET Core 3.1의 새로운 기능
description: .NET Core 3.1에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: eba3d21cfc787c5d388de31f988b835522118151
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936920"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="adffa-103">.NET Core 3.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="adffa-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="adffa-104">이 문서에서는 .NET Core 3.1의 새로운 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="adffa-105">이 릴리스에는 작지만 중요한 수정 내용에 중점을 둔 .NET Core 3.0의 소소한 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="adffa-106">.NET Core 3.1의 가장 중요한 기능은 [LTS(장기 지원)](#long-term-support) 릴리스라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="adffa-107">Visual Studio 2019을 사용하는 경우 .NET Core 3.1 프로젝트와 함께 작동하려면 [Visual Studio 2019 버전 16.4](https://visualstudio.microsoft.com/downloads/)를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="adffa-108">Visual Studio의 새로운 기능에 대한 자세한 내용은 [Visual Studio 블로그](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adffa-108">For more information on what is new in Visual Studio, see the [Visual Studio Blog](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/).</span></span>

<span data-ttu-id="adffa-109">또한 Mac용 Visual Studio는 Mac용 Visual Studio 8.4 미리 보기 채널에서 .NET Core 3.1을 지원 및 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-109">Visual Studio for Mac also supports and includes .NET Core 3.1, in the Visual Studio for Mac 8.4 Preview channel.</span></span> <span data-ttu-id="adffa-110">.NET Core 3.1을 사용하려면 미리 보기 채널에 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-110">You'll need to opt into the Preview channel to use .NET Core 3.1.</span></span>

<span data-ttu-id="adffa-111">릴리스에 대한 자세한 내용은 [.NET Core 3.1 공지](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adffa-111">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="adffa-112">Windows, macOS 또는 Linux에서 [.NET Core 3.1을 다운로드하여 시작](https://dotnet.microsoft.com/download/dotnet-core/3.1)하세요.</span><span class="sxs-lookup"><span data-stu-id="adffa-112">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="adffa-113">장기 지원</span><span class="sxs-lookup"><span data-stu-id="adffa-113">Long-term support</span></span>

<span data-ttu-id="adffa-114">.NET Core 3.1은 향후 3년 동안 Microsoft를 지원하는 LTS 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-114">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="adffa-115">사용 중인 앱을 .NET Core 3.1로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-115">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="adffa-116">다른 주요 릴리스의 현재 수명 주기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-116">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="adffa-117">Release</span><span class="sxs-lookup"><span data-stu-id="adffa-117">Release</span></span> | <span data-ttu-id="adffa-118">참고</span><span class="sxs-lookup"><span data-stu-id="adffa-118">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="adffa-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="adffa-119">.NET Core 3.0</span></span> | <span data-ttu-id="adffa-120">2020년 3월 3일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-120">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="adffa-121">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="adffa-121">.NET Core 2.2</span></span> | <span data-ttu-id="adffa-122">2019년 12월 23일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-122">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="adffa-123">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="adffa-123">.NET Core 2.1</span></span> | <span data-ttu-id="adffa-124">2021년 8월 21일에 수명이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-124">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="adffa-125">자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adffa-125">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="adffa-126">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="adffa-126">Windows Forms</span></span>

<span data-ttu-id="adffa-127">*Windows만 해당*</span><span class="sxs-lookup"><span data-stu-id="adffa-127">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="adffa-128">Windows Forms 관련 호환성이 손상되는 변경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-128">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="adffa-129">레거시 컨트롤은 Visual Studio Designer Toolbox에서 잠시 사용할 수 없었던 Windows Forms에 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-129">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="adffa-130">이러한 항목은 .NET Framework 2.0에서 새 컨트롤로 바뀌었으며</span><span class="sxs-lookup"><span data-stu-id="adffa-130">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="adffa-131">.NET Core 3.1용 데스크톱 SDK에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-131">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="adffa-132">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="adffa-132">Removed control</span></span> | <span data-ttu-id="adffa-133">권장된 대체</span><span class="sxs-lookup"><span data-stu-id="adffa-133">Recommended replacement</span></span> | <span data-ttu-id="adffa-134">제거된 연결 API</span><span class="sxs-lookup"><span data-stu-id="adffa-134">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="adffa-135">DataGrid</span><span class="sxs-lookup"><span data-stu-id="adffa-135">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="adffa-136">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="adffa-136">DataGridCell</span></span><br/><span data-ttu-id="adffa-137">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="adffa-137">DataGridRow</span></span><br/><span data-ttu-id="adffa-138">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="adffa-138">DataGridTableCollection</span></span><br/><span data-ttu-id="adffa-139">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="adffa-139">DataGridColumnCollection</span></span><br/><span data-ttu-id="adffa-140">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="adffa-140">DataGridTableStyle</span></span><br/><span data-ttu-id="adffa-141">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="adffa-141">DataGridColumnStyle</span></span><br/><span data-ttu-id="adffa-142">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="adffa-142">DataGridLineStyle</span></span><br/><span data-ttu-id="adffa-143">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="adffa-143">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="adffa-144">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="adffa-144">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="adffa-145">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="adffa-145">DataGridBoolColumn</span></span><br/><span data-ttu-id="adffa-146">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="adffa-146">DataGridTextBox</span></span><br/><span data-ttu-id="adffa-147">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="adffa-147">GridColumnStylesCollection</span></span><br/><span data-ttu-id="adffa-148">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="adffa-148">GridTableStylesCollection</span></span><br/><span data-ttu-id="adffa-149">HitTestType</span><span class="sxs-lookup"><span data-stu-id="adffa-149">HitTestType</span></span> |
| <span data-ttu-id="adffa-150">ToolBar</span><span class="sxs-lookup"><span data-stu-id="adffa-150">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="adffa-151">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="adffa-151">ToolBarAppearance</span></span> |
| <span data-ttu-id="adffa-152">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="adffa-152">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="adffa-153">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="adffa-153">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="adffa-154">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="adffa-154">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="adffa-155">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="adffa-155">ToolBarButtonStyle</span></span><br/><span data-ttu-id="adffa-156">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="adffa-156">ToolBarTextAlign</span></span> |
| <span data-ttu-id="adffa-157">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="adffa-157">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="adffa-158">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="adffa-158">MenuItemCollection</span></span> |
| <span data-ttu-id="adffa-159">MainMenu</span><span class="sxs-lookup"><span data-stu-id="adffa-159">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="adffa-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="adffa-160">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="adffa-161">애플리케이션을 .NET Core 3.1로 업데이트하고 대체 컨트롤로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-161">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="adffa-162">컨트롤을 바꾸는 것은 기본적으로 유형을 "찾고 대체"하는 간단한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-162">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="adffa-163">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="adffa-163">C++/CLI</span></span>

<span data-ttu-id="adffa-164">*Windows만 해당*</span><span class="sxs-lookup"><span data-stu-id="adffa-164">*Windows only*</span></span>

<span data-ttu-id="adffa-165">C++/CLI("관리되는 C++"라고도 함) 프로젝트를 만들기 위한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-165">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="adffa-166">이러한 프로젝트에서 생성된 이진 파일은 .NET Core 3.0 이상 버전과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-166">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="adffa-167">Visual Studio 2019 16.4에서 C++/CLI에 대한 지원을 추가하려면 [C++ 워크로드로 데스크톱 개발](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-167">To add support for C++/CLI in Visual Studio 2019 16.4, install the [Desktop development with C++ workload](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="adffa-168">이 워크로드는 Visual Studio에 다음의 두 가지 템플릿을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-168">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="adffa-169">CLR 클래스 라이브러리(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="adffa-169">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="adffa-170">CLR 빈 프로젝트(.NET Core)</span><span class="sxs-lookup"><span data-stu-id="adffa-170">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="adffa-171">다음 단계</span><span class="sxs-lookup"><span data-stu-id="adffa-171">Next steps</span></span>

- [<span data-ttu-id="adffa-172">.NET Core 3.0 및 3.1 간의 호환성이 손상되는 변경을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-172">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="adffa-173">Windows Forms 앱용 .NET Core 3.1의 주요 변경 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="adffa-173">Review the breaking changes between in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
