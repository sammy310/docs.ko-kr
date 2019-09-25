---
title: 호환성이 손상되는 변경 사항, .NET Framework에서 .NET Core 3.0으로 - .NET Core
description: .NET Framework에서 .NET Core 3.0으로 Windows Forms 및 Windows Presentation Foundation에 대한 호환성이 손상되는 주요 변경을 나열합니다.
ms.date: 09/10/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c658c5bce7a2554bba83f2779a73d9d6af01a342
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151527"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a>.NET Framework에서 .NET Core 3.0으로 마이그레이션 시 호환성이 손상되는 주요 변경

> [!IMPORTANT]
> 이 문서는 작성 중입니다. 이것은 .NET Core 호환성이 손상되는 변경 사항의 완전한 목록이 아닙니다. .NET Core 호환성이 손상되는 변경 사항에 대한 자세한 내용은 GitHub의 dotnet/docs 리포지토리에 있는 개별 [호환성이 손상되는 변경 문제](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)에서 검토할 수 있습니다. 

Windows Forms 또는 Windows Presentation Foundation 애플리케이션을 .NET Framework에서 .NET Core 3.0으로 마이그레이션하는 경우 다음 항목에서 앱에 영향을 줄 수 있는 주요 변경 내용을 검토하세요.

## <a name="windows-forms"></a>Windows Forms

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
