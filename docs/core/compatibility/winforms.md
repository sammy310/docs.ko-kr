---
title: Windows Forms 관련 호환성이 손상되는 변경
description: .NET Core 3.0 및 3.1용 Windows Forms의 호환성이 손상되는 변경을 나열합니다.
ms.date: 09/08/2020
ms.openlocfilehash: b944f7eea89b61f41feb8eef99e949c2d6017960
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726433"
---
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a><span data-ttu-id="1e5e5-103">.NET Core 3.0 및 3.1용 Windows Forms의 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="1e5e5-103">Breaking changes in Windows Forms for .NET Core 3.0 and 3.1</span></span>

<span data-ttu-id="1e5e5-104">Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e5e5-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="1e5e5-105">이 문서에서는 Windows Forms의 호환성이 손상되는 변경을 .NET 버전(해당 변경이 도입된 버전)을 기준으로 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="1e5e5-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="1e5e5-106">.NET Framework 또는 이전 버전의 .NET Core(3.0 이상)에서 Windows Forms 앱을 업그레이드하는 경우 이 문서가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e5e5-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="1e5e5-107">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e5e5-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="1e5e5-108">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1e5e5-108">Breaking change</span></span> | <span data-ttu-id="1e5e5-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1e5e5-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="1e5e5-110">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1e5e5-110">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="1e5e5-111">3.1</span><span class="sxs-lookup"><span data-stu-id="1e5e5-111">3.1</span></span> |
| [<span data-ttu-id="1e5e5-112">도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-112">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="1e5e5-113">3.1</span><span class="sxs-lookup"><span data-stu-id="1e5e5-113">3.1</span></span> |
| [<span data-ttu-id="1e5e5-114">Control.DefaultFont가 맑은 고딕 9pt로 변경됨</span><span class="sxs-lookup"><span data-stu-id="1e5e5-114">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="1e5e5-115">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-115">3.0</span></span> |
| [<span data-ttu-id="1e5e5-116">FolderBrowserDialog의 현대화</span><span class="sxs-lookup"><span data-stu-id="1e5e5-116">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="1e5e5-117">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-117">3.0</span></span> |
| [<span data-ttu-id="1e5e5-118">일부 Windows Forms 형식에서 SerializableAttribute 제거됨</span><span class="sxs-lookup"><span data-stu-id="1e5e5-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="1e5e5-119">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-119">3.0</span></span> |
| [<span data-ttu-id="1e5e5-120">AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-120">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-121">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-121">3.0</span></span> |
| [<span data-ttu-id="1e5e5-122">DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-122">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-123">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-123">3.0</span></span> |
| [<span data-ttu-id="1e5e5-124">DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-124">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-125">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-125">3.0</span></span> |
| [<span data-ttu-id="1e5e5-126">DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-126">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-127">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-127">3.0</span></span> |
| [<span data-ttu-id="1e5e5-128">DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-128">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-129">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-129">3.0</span></span> |
| [<span data-ttu-id="1e5e5-130">EnableVisualStyleValidation 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-130">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-131">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-131">3.0</span></span> |
| [<span data-ttu-id="1e5e5-132">UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-132">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-133">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-133">3.0</span></span> |
| [<span data-ttu-id="1e5e5-134">UseLegacyImages 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="1e5e5-134">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="1e5e5-135">3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-135">3.0</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="1e5e5-136">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1e5e5-136">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

<span data-ttu-id="1e5e5-137">\*\*_</span><span class="sxs-lookup"><span data-stu-id="1e5e5-137">\*\*_</span></span>

## <a name="net-core-30"></a><span data-ttu-id="1e5e5-138">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1e5e5-138">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

_*_

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

_*_

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

<span data-ttu-id="1e5e5-139">_\*\*</span><span class="sxs-lookup"><span data-stu-id="1e5e5-139">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="1e5e5-140">참조</span><span class="sxs-lookup"><span data-stu-id="1e5e5-140">See also</span></span>

- [<span data-ttu-id="1e5e5-141">.NET Core에 Windows Forms 앱 포팅</span><span class="sxs-lookup"><span data-stu-id="1e5e5-141">Port a Windows Forms app to .NET Core</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
