---
title: Windows Forms 관련 호환성이 손상되는 변경
description: .NET Core용 Windows Forms 관련 호환성이 손상되는 변경 목록입니다.
ms.date: 01/08/2020
ms.openlocfilehash: 7fba78382d011bc9d489924fa185a44e598c5a76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398012"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="851bb-103">Windows Forms 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="851bb-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="851bb-104">Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="851bb-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="851bb-105">이 문서에서는 Windows Forms의 주요 변경 사항이 .NET Core 버전이 도입된 순서대로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="851bb-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="851bb-106">.NET Framework 또는 이전 버전의 .NET Core(3.0 이상)에서 Windows Forms 앱을 업그레이드하는 경우 이 문서가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="851bb-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="851bb-107">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851bb-107">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="851bb-108">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="851bb-108">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="851bb-109">도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-109">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="851bb-110">Control.DefaultFont가 맑은 고딕 9pt로 변경됨</span><span class="sxs-lookup"><span data-stu-id="851bb-110">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="851bb-111">FolderBrowserDialog의 현대화</span><span class="sxs-lookup"><span data-stu-id="851bb-111">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="851bb-112">일부 Windows Forms 형식에서 SerializableAttribute 제거됨</span><span class="sxs-lookup"><span data-stu-id="851bb-112">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="851bb-113">AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-113">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-114">DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-114">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-115">DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-115">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-116">DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-116">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-117">DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-117">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-118">EnableVisualStyleValidation 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-118">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-119">UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-119">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-120">UseLegacyImages 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="851bb-120">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="851bb-121">AccessibleObject.RuntimeIDFirstItem에 대한 액세스 변경</span><span class="sxs-lookup"><span data-stu-id="851bb-121">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="851bb-122">Windows Forms에서 중복된 API가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="851bb-122">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

## <a name="net-core-31"></a><span data-ttu-id="851bb-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="851bb-123">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="851bb-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="851bb-124">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="851bb-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="851bb-125">See also</span></span>

- [<span data-ttu-id="851bb-126">.NET Core에 Windows Forms 앱 포팅</span><span class="sxs-lookup"><span data-stu-id="851bb-126">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
