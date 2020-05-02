---
title: Windows Forms 관련 호환성이 손상되는 변경
description: .NET Core용 Windows Forms 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 01/08/2020
ms.openlocfilehash: 75d369c7fb999da81a50fe46716e125c3840eb7a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158439"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="30740-103">Windows Forms 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="30740-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="30740-104">Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30740-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="30740-105">이 문서에서는 Windows Forms의 주요 변경 사항이 .NET Core 버전이 도입된 순서대로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="30740-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="30740-106">.NET Framework 또는 이전 버전의 .NET Core(3.0 이상)에서 Windows Forms 앱을 업그레이드하는 경우 이 문서가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30740-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="30740-107">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30740-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="30740-108">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="30740-108">Breaking change</span></span> | <span data-ttu-id="30740-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="30740-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="30740-110">상태 표시줄 컨트롤 제거</span><span class="sxs-lookup"><span data-stu-id="30740-110">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="30740-111">5.0</span><span class="sxs-lookup"><span data-stu-id="30740-111">5.0</span></span> |
| [<span data-ttu-id="30740-112">WinForms 메서드는 이제 ArgumentException을 throw함</span><span class="sxs-lookup"><span data-stu-id="30740-112">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="30740-113">5.0</span><span class="sxs-lookup"><span data-stu-id="30740-113">5.0</span></span> |
| [<span data-ttu-id="30740-114">WinForms 메서드는 이제 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="30740-114">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="30740-115">5.0</span><span class="sxs-lookup"><span data-stu-id="30740-115">5.0</span></span> |
| [<span data-ttu-id="30740-116">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="30740-116">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="30740-117">3.1</span><span class="sxs-lookup"><span data-stu-id="30740-117">3.1</span></span> |
| [<span data-ttu-id="30740-118">도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-118">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="30740-119">3.1</span><span class="sxs-lookup"><span data-stu-id="30740-119">3.1</span></span> |
| [<span data-ttu-id="30740-120">Control.DefaultFont가 맑은 고딕 9pt로 변경됨</span><span class="sxs-lookup"><span data-stu-id="30740-120">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="30740-121">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-121">3.0</span></span> |
| [<span data-ttu-id="30740-122">FolderBrowserDialog의 현대화</span><span class="sxs-lookup"><span data-stu-id="30740-122">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="30740-123">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-123">3.0</span></span> |
| [<span data-ttu-id="30740-124">일부 Windows Forms 형식에서 SerializableAttribute 제거됨</span><span class="sxs-lookup"><span data-stu-id="30740-124">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="30740-125">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-125">3.0</span></span> |
| [<span data-ttu-id="30740-126">AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-126">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="30740-127">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-127">3.0</span></span> |
| [<span data-ttu-id="30740-128">DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-128">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="30740-129">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-129">3.0</span></span> |
| [<span data-ttu-id="30740-130">DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-130">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="30740-131">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-131">3.0</span></span> |
| [<span data-ttu-id="30740-132">DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-132">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="30740-133">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-133">3.0</span></span> |
| [<span data-ttu-id="30740-134">DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-134">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="30740-135">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-135">3.0</span></span> |
| [<span data-ttu-id="30740-136">EnableVisualStyleValidation 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-136">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="30740-137">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-137">3.0</span></span> |
| [<span data-ttu-id="30740-138">UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-138">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="30740-139">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-139">3.0</span></span> |
| [<span data-ttu-id="30740-140">UseLegacyImages 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="30740-140">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="30740-141">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-141">3.0</span></span> |
| [<span data-ttu-id="30740-142">AccessibleObject.RuntimeIDFirstItem에 대한 액세스 변경</span><span class="sxs-lookup"><span data-stu-id="30740-142">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="30740-143">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-143">3.0</span></span> |
| [<span data-ttu-id="30740-144">Windows Forms에서 중복된 API가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30740-144">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="30740-145">3.0</span><span class="sxs-lookup"><span data-stu-id="30740-145">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="30740-146">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="30740-146">.NET 5.0</span></span>

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="30740-147">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="30740-147">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="30740-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="30740-148">.NET Core 3.0</span></span>

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

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="30740-149">참조</span><span class="sxs-lookup"><span data-stu-id="30740-149">See also</span></span>

- [<span data-ttu-id="30740-150">.NET Core에 Windows Forms 앱 포팅</span><span class="sxs-lookup"><span data-stu-id="30740-150">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
