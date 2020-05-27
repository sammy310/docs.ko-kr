---
ms.openlocfilehash: 11c04441dcec260f0bfb90f6ed2b919b1545b382
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721389"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>FolderBrowserDialog의 현대화

이 <xref:System.Windows.Forms.FolderBrowserDialog> 컨트롤은 .NET Core 용 Windows Forms 애플리케이션에서 변경되었습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서 Windows Forms는 <xref:System.Windows.Forms.FolderBrowserDialog> 컨트롤에 대해 다음 대화 상자를 사용합니다.

![.NET Framework의 FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

.NET Core 3.0에서는 Windows Forms가 Windows Vista에서 도입된 최신 COM 기반 컨트롤을 사용합니다.

![.NET Core의 FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

대화 상자가 자동으로 업그레이드됩니다.

원래 대화 상자를 유지하려는 경우 다음 코드 조각에 나와 있듯이 대화 상자를 표시하기 전에 <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> 속성을 `false`로 설정합니다.

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

#### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
