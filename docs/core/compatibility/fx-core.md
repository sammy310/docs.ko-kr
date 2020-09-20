---
title: 호환성이 손상되는 변경 사항 - .NET Framework에서 .NET Core로 변경
titleSuffix: ''
description: .NET Framework에서 .NET Core 1.0~3.1로의 호환성이 손상되는 변경을 나열합니다.
ms.date: 05/05/2020
ms.openlocfilehash: 5904a359813b6d07bd2a27d882ade4395efe3256
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656368"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>.NET Framework에서 .NET Core로 마이그레이션 시 호환성이 손상되는 변경 사항

.NET Framework에서 .NET Core 버전 1.0~3.1로 앱을 마이그레이션하는 경우 이 문서에 나열된 호환성이 손상되는 변경이 영향을 줄 수 있습니다. 주요 변경 사항은 범주별로 그룹화되며 해당 범주 내에서는 도입된 .NET Core 버전에 따라 그룹화됩니다.

> [!NOTE]
> 이 문서는 .NET Framework와 .NET Core 간 호환성이 손상되는 변경 사항의 전체 목록이 아닙니다. 가장 중요한 호환성이 손상되는 변경 사항은 이를 인식하는 대로 여기에 추가됩니다.

## <a name="core-net-libraries"></a>핵심 .NET 라이브러리

- [UseShellExecute의 기본값 변경](#change-in-default-value-of-useshellexecute)
- [FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [손상된 프로세스 상태 예외 처리는 지원되지 않음](#handling-corrupted-state-exceptions-is-not-supported)
- [UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음](#uribuilder-properties-no-longer-prepend-leading-characters)
- [Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***

## <a name="cryptography"></a>암호화

- [SignedCms.ComputeSignature의 부울 매개 변수를 적용](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="msbuild"></a>MSBuild

- [리소스 매니페스트 파일 이름 변경](#resource-manifest-file-name-change)

### <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="networking"></a>네트워킹

- [WebClient.CancelAsync가 항상 즉시 취소되지는 않음](#webclientcancelasync-doesnt-always-cancel-immediately)

### <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

## <a name="windows-forms"></a>Windows Forms

Windows Forms 지원이 버전 3.0의 .NET Core에 추가되었습니다. .NET Framework에서 .NET Core로 Windows Forms 앱을 마이그레이션하는 경우 여기에 나열된 주요 변경 사항이 앱에 영향을 줄 수 있습니다.

- [제거된 컨트롤](#removed-controls)
- [도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않음](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [Control.DefaultFont가 맑은 고딕 9pt로 변경됨](#default-control-font-changed-to-segoe-ui-9-pt)
- [FolderBrowserDialog의 현대화](#modernization-of-the-folderbrowserdialog)
- [일부 Windows Forms 형식에서 SerializableAttribute 제거됨](#serializableattribute-removed-from-some-windows-forms-types)
- [AllowUpdateChildControlIndexForTabControls 호환성 스위치가 지원되지 않음](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [DontSupportReentrantFilterMessage 호환성 스위치가 지원되지 않음](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [EnableVisualStyleValidation 호환성 스위치가 지원되지 않음](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [UseLegacyImages 호환성 스위치가 지원되지 않음](#uselegacyimages-compatibility-switch-not-supported)

### <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="see-also"></a>참조

- [.NET Core에서 항상 예외를 throw하는 API](unsupported-apis.md)
- [.NET Core에서 사용할 수 없는 .NET Framework 기술](../porting/net-framework-tech-unavailable.md)
