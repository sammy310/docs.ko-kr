---
title: .NET Core 3.1의 새로운 기능
description: .NET Core 3.1에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: a9f47c2909375251460b45792822e491d56fb242
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342856"
---
# <a name="whats-new-in-net-core-31"></a>.NET Core 3.1의 새로운 기능

이 문서에서는 .NET Core 3.1의 새로운 기능을 설명합니다. 이 릴리스에는 작지만 중요한 수정 내용에 중점을 둔 .NET Core 3.0의 소소한 개선 사항이 포함되어 있습니다. .NET Core 3.1의 가장 중요한 기능은 [LTS(장기 지원)](#long-term-support) 릴리스라는 것입니다.

Visual Studio 2019을 사용하는 경우 .NET Core 3.1 프로젝트와 함께 작동하려면 [Visual Studio 2019 버전 16.4](https://visualstudio.microsoft.com/downloads/)를 업데이트해야 합니다. Visual Studio의 새로운 기능에 대한 자세한 내용은 [Visual Studio 블로그](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/)를 참조하세요.

또한 Mac용 Visual Studio는 Mac용 Visual Studio 8.4 미리 보기 채널에서 .NET Core 3.1을 지원 및 포함합니다. .NET Core 3.1을 사용하려면 미리 보기 채널에 옵트인해야 합니다.

릴리스에 대한 자세한 내용은 [.NET Core 3.1 공지](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)를 참조하세요.

- Windows, macOS 또는 Linux에서 [.NET Core 3.1을 다운로드하여 시작](https://dotnet.microsoft.com/download/dotnet-core/3.1)하세요.

## <a name="long-term-support"></a>장기 지원

.NET Core 3.1은 향후 3년 동안 Microsoft를 지원하는 LTS 릴리스입니다. 사용 중인 앱을 .NET Core 3.1로 이동하는 것이 좋습니다. 다른 주요 릴리스의 현재 수명 주기는 다음과 같습니다.

| Release | 참고 |
| ------- | ---- |
| .NET Core 3.0 | 2020년 3월 3일에 수명이 종료됩니다.     |
| .NET Core 2.2 | 2019년 12월 23일에 수명이 종료됩니다. |
| .NET Core 2.1 | 2021년 8월 21일에 수명이 종료됩니다.    |

자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.

## <a name="windows-forms"></a>Windows Forms

*Windows만 해당*

> [!WARNING]
> Windows Forms 관련 호환성이 손상되는 변경이 있습니다.

레거시 컨트롤은 Visual Studio Designer Toolbox에서 잠시 사용할 수 없었던 Windows Forms에 포함되었습니다. 이러한 항목은 .NET Framework 2.0에서 새 컨트롤로 바뀌었으며 .NET Core 3.1용 데스크톱 SDK에서 제거되었습니다.

| 제거된 컨트롤 | 권장된 대체 | 제거된 연결 API |
| --------------- | ----------------------- | ----------------------- |
| DataGrid        | <xref:System.Windows.Forms.DataGridView>      | DataGridCell<br/>DataGridRow<br/>DataGridTableCollection<br/>DataGridColumnCollection<br/>DataGridTableStyle<br/>DataGridColumnStyle<br/>DataGridLineStyle<br/>DataGridParentRowsLabel<br/>DataGridParentRowsLabelStyle<br/>DataGridBoolColumn<br/>DataGridTextBox<br/>GridColumnStylesCollection<br/>GridTableStylesCollection<br/>HitTestType |
| ToolBar         | <xref:System.Windows.Forms.ToolStrip>         | ToolBarAppearance |
| ToolBarButton   | <xref:System.Windows.Forms.ToolStripButton>   | ToolBarButtonClickEventArgs<br/>ToolBarButtonClickEventHandler<br/>ToolBarButtonStyle<br/>ToolBarTextAlign |
| ContextMenu     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | MenuItemCollection |
| MainMenu        | <xref:System.Windows.Forms.MenuStrip>         |  |
| MenuItem        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

애플리케이션을 .NET Core 3.1로 업데이트하고 대체 컨트롤로 이동하는 것이 좋습니다. 컨트롤을 바꾸는 것은 기본적으로 유형을 "찾고 대체"하는 간단한 프로세스입니다.

## <a name="ccli"></a>C++/CLI

*Windows만 해당*

C++/CLI("관리되는 C++"라고도 함) 프로젝트를 만들기 위한 지원이 추가되었습니다. 이러한 프로젝트에서 생성된 이진 파일은 .NET Core 3.0 이상 버전과 호환됩니다.

Visual Studio 2019 16.4에서 C++/CLI에 대한 지원을 추가하려면 [C++ 워크로드로 데스크톱 개발](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)을 설치합니다. 이 워크로드는 Visual Studio에 다음의 두 가지 템플릿을 추가합니다.

- CLR 클래스 라이브러리(.NET Core)
- CLR 빈 프로젝트(.NET Core)

## <a name="next-steps"></a>다음 단계

- [.NET Core 3.0 및 3.1 간의 호환성이 손상되는 변경을 검토합니다.](../compatibility/3.0-3.1.md)
- [Windows Forms 앱의 .NET Framework 및 .NET Core 3.0 간의 호환성이 손상되는 변경 검토](../porting/winforms-breaking-changes.md)
