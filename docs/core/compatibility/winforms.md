---
title: Windows Forms 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5용 Windows Forms의 호환성이 손상되는 변경 목록입니다.
ms.date: 09/08/2020
ms.openlocfilehash: 2311faab026bf1dfde348e231937eff73ec46172
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804865"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="4f17d-103">Windows Forms 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="4f17d-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="4f17d-104">Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f17d-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="4f17d-105">이 문서에서는 Windows Forms의 호환성이 손상되는 변경을 .NET 버전(해당 변경이 도입된 버전)을 기준으로 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4f17d-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="4f17d-106">.NET Framework 또는 이전 버전의 .NET Core(3.0 이상)에서 Windows Forms 앱을 업그레이드하는 경우 이 문서가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f17d-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="4f17d-107">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f17d-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="4f17d-108">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="4f17d-108">Breaking change</span></span> | <span data-ttu-id="4f17d-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="4f17d-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="4f17d-110">DataGridView에서 더 이상 사용자 지정 셀 스타일의 글꼴을 다시 설정하지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-110">DataGridView no longer resets fonts for customized cell styles</span></span>](#datagridview-no-longer-resets-fonts-for-customized-cell-styles) | <span data-ttu-id="4f17d-111">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-111">5.0</span></span> |
| [<span data-ttu-id="4f17d-112">WPF 및 WinForms 앱에 대해 OutputType이 WinExe로 설정됨</span><span class="sxs-lookup"><span data-stu-id="4f17d-112">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="4f17d-113">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-113">5.0</span></span> |
| [<span data-ttu-id="4f17d-114">DataGridView 관련 API가 이제 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="4f17d-114">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="4f17d-115">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-115">5.0</span></span> |
| [<span data-ttu-id="4f17d-116">WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함</span><span class="sxs-lookup"><span data-stu-id="4f17d-116">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="4f17d-117">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-117">5.0</span></span> |
| [<span data-ttu-id="4f17d-118">상태 표시줄 컨트롤 제거</span><span class="sxs-lookup"><span data-stu-id="4f17d-118">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="4f17d-119">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-119">5.0</span></span> |
| [<span data-ttu-id="4f17d-120">WinForms 메서드는 이제 ArgumentException을 throw함</span><span class="sxs-lookup"><span data-stu-id="4f17d-120">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="4f17d-121">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-121">5.0</span></span> |
| [<span data-ttu-id="4f17d-122">WinForms 메서드는 이제 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="4f17d-122">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="4f17d-123">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-123">5.0</span></span> |
| [<span data-ttu-id="4f17d-124">WinForms 속성은 이제 ArgumentOutOfRangeException을 throw함</span><span class="sxs-lookup"><span data-stu-id="4f17d-124">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="4f17d-125">5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-125">5.0</span></span> |
| [<span data-ttu-id="4f17d-126">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4f17d-126">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="4f17d-127">3.1</span><span class="sxs-lookup"><span data-stu-id="4f17d-127">3.1</span></span> |
| [<span data-ttu-id="4f17d-128">도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-128">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="4f17d-129">3.1</span><span class="sxs-lookup"><span data-stu-id="4f17d-129">3.1</span></span> |
| [<span data-ttu-id="4f17d-130">Control.DefaultFont가 맑은 고딕 9pt로 변경됨</span><span class="sxs-lookup"><span data-stu-id="4f17d-130">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="4f17d-131">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-131">3.0</span></span> |
| [<span data-ttu-id="4f17d-132">FolderBrowserDialog의 현대화</span><span class="sxs-lookup"><span data-stu-id="4f17d-132">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="4f17d-133">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-133">3.0</span></span> |
| [<span data-ttu-id="4f17d-134">일부 Windows Forms 형식에서 SerializableAttribute 제거됨</span><span class="sxs-lookup"><span data-stu-id="4f17d-134">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="4f17d-135">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-135">3.0</span></span> |
| [<span data-ttu-id="4f17d-136">AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-136">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-137">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-137">3.0</span></span> |
| [<span data-ttu-id="4f17d-138">DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-138">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-139">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-139">3.0</span></span> |
| [<span data-ttu-id="4f17d-140">DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-140">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-141">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-141">3.0</span></span> |
| [<span data-ttu-id="4f17d-142">DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-142">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-143">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-143">3.0</span></span> |
| [<span data-ttu-id="4f17d-144">DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-144">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-145">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-145">3.0</span></span> |
| [<span data-ttu-id="4f17d-146">EnableVisualStyleValidation 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-146">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-147">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-147">3.0</span></span> |
| [<span data-ttu-id="4f17d-148">UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-148">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-149">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-149">3.0</span></span> |
| [<span data-ttu-id="4f17d-150">UseLegacyImages 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f17d-150">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="4f17d-151">3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-151">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="4f17d-152">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-152">.NET 5.0</span></span>

[!INCLUDE [datagridview-doesnt-reset-custom-font-settings](../../../includes/core-changes/windowsforms/5.0/datagridview-doesnt-reset-custom-font-settings.md)]

***

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="4f17d-153">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="4f17d-153">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="4f17d-154">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4f17d-154">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="4f17d-155">참조</span><span class="sxs-lookup"><span data-stu-id="4f17d-155">See also</span></span>

- [<span data-ttu-id="4f17d-156">.NET Core에 Windows Forms 앱 포팅</span><span class="sxs-lookup"><span data-stu-id="4f17d-156">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
