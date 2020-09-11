---
title: 호환성이 손상되는 변경 사항 - .NET Framework에서 .NET Core로 변경
titleSuffix: ''
description: .NET Framework에서 .NET Core로의 호환성이 손상되는 변경 사항을 나열합니다.
ms.date: 05/05/2020
ms.openlocfilehash: e9fa37dba89bbd6c4829614c27cb66206069fa9b
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414459"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="783e0-103">.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="783e0-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="783e0-104">.NET Framework에서 .NET Core로 마이그레이션하는 경우, 다음 문서에 표시된 호환성이 손상되는 변경 사항이 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="783e0-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="783e0-105">주요 변경 사항은 범주별로 그룹화되며 해당 범주 내에서는 도입된 .NET Core 버전에 따라 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="783e0-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core in which they were introduced.</span></span>

> [!NOTE]
> <span data-ttu-id="783e0-106">이 문서는 .NET Framework와 .NET Core 간 호환성이 손상되는 변경 사항의 전체 목록이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="783e0-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="783e0-107">가장 중요한 호환성이 손상되는 변경 사항은 이를 인식하는 대로 여기에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="783e0-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="core-net-libraries"></a><span data-ttu-id="783e0-108">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="783e0-108">Core .NET libraries</span></span>

- [<span data-ttu-id="783e0-109">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="783e0-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)
- [<span data-ttu-id="783e0-110">FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="783e0-110">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [<span data-ttu-id="783e0-111">손상된 프로세스 상태 예외 처리는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-111">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported)
- [<span data-ttu-id="783e0-112">UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-112">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters)
- [<span data-ttu-id="783e0-113">Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="783e0-113">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start)

### <a name="net-core-21"></a><span data-ttu-id="783e0-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="783e0-114">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a><span data-ttu-id="783e0-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="783e0-115">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***

## <a name="cryptography"></a><span data-ttu-id="783e0-116">암호화</span><span class="sxs-lookup"><span data-stu-id="783e0-116">Cryptography</span></span>

- [<span data-ttu-id="783e0-117">SignedCms.ComputeSignature의 부울 매개 변수를 적용</span><span class="sxs-lookup"><span data-stu-id="783e0-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a><span data-ttu-id="783e0-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="783e0-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="msbuild"></a><span data-ttu-id="783e0-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="783e0-119">MSBuild</span></span>

- [<span data-ttu-id="783e0-120">리소스 매니페스트 파일 이름 변경</span><span class="sxs-lookup"><span data-stu-id="783e0-120">Resource manifest file name change</span></span>](#resource-manifest-file-name-change)

### <a name="net-core-30"></a><span data-ttu-id="783e0-121">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="783e0-121">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="networking"></a><span data-ttu-id="783e0-122">네트워킹</span><span class="sxs-lookup"><span data-stu-id="783e0-122">Networking</span></span>

- [<span data-ttu-id="783e0-123">WebClient.CancelAsync가 항상 즉시 취소되지는 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-123">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately)
- [<span data-ttu-id="783e0-124">이제 쿠키 경로 처리가 RFC 6265를 준수함</span><span class="sxs-lookup"><span data-stu-id="783e0-124">Cookie Path handling now conforms to RFC 6265</span></span>](#cookie-path-handling-now-conforms-to-rfc-6265)

### <a name="net-core-20"></a><span data-ttu-id="783e0-125">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="783e0-125">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

### <a name="net-50"></a><span data-ttu-id="783e0-126">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="783e0-126">.NET 5.0</span></span>

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="783e0-127">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="783e0-127">Windows Forms</span></span>

<span data-ttu-id="783e0-128">Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="783e0-128">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="783e0-129">.NET Framework에서 .NET Core로 Windows Forms 앱을 마이그레이션하는 경우 여기에 나열된 주요 변경 사항이 앱에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="783e0-129">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="783e0-130">제거된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="783e0-130">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="783e0-131">도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-131">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="783e0-132">Control.DefaultFont가 맑은 고딕 9pt로 변경됨</span><span class="sxs-lookup"><span data-stu-id="783e0-132">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="783e0-133">FolderBrowserDialog의 현대화</span><span class="sxs-lookup"><span data-stu-id="783e0-133">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="783e0-134">일부 Windows Forms 형식에서 SerializableAttribute 제거됨</span><span class="sxs-lookup"><span data-stu-id="783e0-134">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="783e0-135">AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-135">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="783e0-136">DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-136">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="783e0-137">DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-137">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="783e0-138">DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-138">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="783e0-139">DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-139">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="783e0-140">EnableVisualStyleValidation 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-140">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="783e0-141">UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-141">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="783e0-142">UseLegacyImages 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="783e0-142">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)

### <a name="net-core-31"></a><span data-ttu-id="783e0-143">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="783e0-143">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="783e0-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="783e0-144">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="783e0-145">참조</span><span class="sxs-lookup"><span data-stu-id="783e0-145">See also</span></span>

- [<span data-ttu-id="783e0-146">.NET Core에서 항상 예외를 throw하는 API</span><span class="sxs-lookup"><span data-stu-id="783e0-146">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="783e0-147">.NET Core에서 사용할 수 없는 .NET Framework 기술</span><span class="sxs-lookup"><span data-stu-id="783e0-147">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
