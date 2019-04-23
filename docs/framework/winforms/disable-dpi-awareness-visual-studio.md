---
title: Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정
description: HDPI 모니터에 대 한 Windows Forms 디자이너의 제한 사항 및 DPI를 인식 하지 못하는 프로세스로 Visual Studio를 실행 하는 방법에 설명 합니다.
ms.date: 04/05/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.custom: seoapril2019
ms.openlocfilehash: e52debea382033417afe0bd47f899af1666192bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181385"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a>Visual Studio에서 인식 되는 DPI를 사용 하지 않도록 설정

Visual Studio는 dpi 인식 응용 프로그램에 자동으로 표시 배율을 즉 인치당입니다. 응용 프로그램에서 DPI에서 인식 되지 않으면 알 경우 운영 체제에 비트맵으로 응용 프로그램을 확장 합니다. 이 동작은 DPI 가상화를 라고도 합니다. 응용 프로그램이 여전히 100% 배율 조정 또는 96dpi에서 실행 되 고 있는지 것으로 생각 합니다.

이 문서에서는 HDPI 모니터에 대 한 Windows Forms 디자이너의 제한 사항 및 DPI를 인식 하지 못하는 프로세스로 Visual Studio를 실행 하는 방법을 설명 합니다.

## <a name="windows-forms-designer-on-hdpi-monitors"></a>HDPI 모니터에 Windows Forms 디자이너

합니다 **Windows Forms 디자이너** Visual Studio에 없는 확장 지원 합니다. 이 인해 표시 문제에서 몇 가지 형태를 열면 합니다 **Windows Forms 디자이너** hdpi 모니터 인치당 높은에서. 예를 들어 다음 그림에 나와 있는 것 처럼 중복 컨트롤 나타날 수 있습니다.

![HDPI 모니터에서 Windows Forms 디자이너](./media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

양식을 열 때 합니다 **Windows Forms 디자이너** HDPI 모니터에서 Visual Studio에서 Visual Studio 디자이너의 맨 위에 있는 노란색 표시줄 정보를 표시 합니다.

![DPI를 인식 하지 못하는 모드에서 다시 시작 하려면 Visual Studio의 정보 표시줄](./media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

메시지 읽고 **기본 디스플레이에 크기 조정 (192dpi) 200%로 설정 됩니다. 디자이너 창에서 렌더링 문제를 발생할 수 있습니다이 있습니다.**

> [!NOTE]
> 이 정보 표시줄은 Visual Studio 2017 버전 15.8에서에서 도입 되었습니다.

디자이너에서 작동 하지 않는 경우 폼의 레이아웃을 조정할 필요가 없습니다 정보 표시줄을 무시 하 고 다른 형식의 디자이너 또는 코드 편집기에서 작업을 계속할 수 있습니다. (할 수도 있습니다 [알림 사용 안 함](#disable-notifications) 표시할 정보 가로 막대형 계속 되지 않도록 합니다.) 만 **Windows Forms 디자이너** 영향을 받습니다. 작업할 필요가 없는 경우는 **Windows Forms 디자이너**, 다음 섹션에서는 도움이 [문제를 해결](#to-resolve-the-display-problem)합니다.

## <a name="to-resolve-the-display-problem"></a>표시 문제를 해결 하려면

표시 문제를 해결 하는 방법은 세 가지가 있습니다.

1. [DPI를 인식 하지 못하는 프로세스로 Visual Studio를 다시 시작](#restart-visual-studio-as-a-dpi-unaware-process)
2. [레지스트리 항목을 추가 합니다.](#add-a-registry-entry)
3. [디스플레이 설정을 100%로 크기 조정 설정](#set-your-display-scaling-setting-to-100)

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a>DPI를 인식 하지 못하는 프로세스로 Visual Studio를 다시 시작

DPI를 인식 하지 못하는 프로세스로 노란색 정보 모음에서 옵션을 선택 하면 Visual Studio를 다시 시작할 수 있습니다. 이 기본 방법은 문제를 해결 합니다.

Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 되 면 디자이너 레이아웃 문제가 해결 되 면 있지만 글꼴 희미하게 보일 수 있습니다. Visual Studio는 DPI를 인식 하지 못하는 프로세스로 실행 될 때 다른 노란색 정보 메시지를 표시 **Visual Studio DPI를 인식 하지 못하는 프로세스로 실행 됩니다. WPF 및 XAML 디자이너를 제대로 표시 되지 않을 수 있습니다.** 정보 표시줄 하는 옵션도 제공 **DPI 인식 프로세스로 Visual Studio를 다시 시작**합니다.

> [!NOTE]
> - DPI를 인식 하지 못하는 프로세스로 다시 시작 하는 옵션을 선택 하면 Visual Studio 도구 창 도킹 되지 않았는지 있었습니다, 해당 도구 창의 위치 변경 될 수 있습니다.
> - 있는 경우 또는 Visual Basic 기본 프로필을 사용 하는 경우는 **만들어질 때 새 프로젝트 저장** 옵션의 선택을 취소 **도구** > **옵션**  >  **프로젝트 및 솔루션**, DPI를 인식 하지 못하는 프로세스로 다시 시작 될 때 Visual Studio 프로젝트를 다시 열 수 없습니다. 아래에서 선택 하 여 프로젝트를 열 수는 있지만 **파일** > **최근 프로젝트 및 솔루션**합니다.

작업 완료 되 면 DPI 인식 프로세스로 Visual Studio를 다시 시작 해야 합니다 **Windows Forms 디자이너**합니다. DPI를 인식 하지 못하는 프로세스로 실행 중인 경우 글꼴 흐리게 수 및와 같은 문제를 다른 디자이너에 표시 될 수 있습니다 합니다 **XAML 디자이너**합니다. 닫고 DPI를 인식 하지 못하는 모드에서 실행 되는 경우에 Visual Studio를 다시 열 경우 됩니다 DPI 인식 다시 합니다. 클릭할 수도 있습니다는 **DPI 인식 프로세스로 Visual Studio를 다시 시작** 정보 표시줄에 대 한 옵션입니다.

### <a name="add-a-registry-entry"></a>레지스트리 항목을 추가 합니다.

레지스트리를 수정 하 여 DPI를 인식 하지 못하는으로 Visual Studio를 표시할 수 있습니다. 열기 **레지스트리 편집기** 항목을 추가 합니다 **실행 NT\CurrentVersion\AppCompatFlags\Layers** 하위 키:

**항목**: 여부를 사용 중인 Visual Studio 2017 또는 2019에 따라 다음이 값 중 하나를 사용 합니다.

- C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe
- C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe

> [!NOTE]
> Visual studio Professional 또는 Enterprise edition을 사용 하는 경우 교체 **커뮤니티** 사용 하 여 **Professional** 또는 **Enterprise** 항목의 합니다. 또한 필요에 따라 드라이브 문자를 대체 합니다.

**Type**: REG_SZ

**값**: DPIUNAWARE

> [!NOTE]
> Visual Studio는 레지스트리 항목을 제거할 때까지 DPI를 인식 하지 못하는 모드로 유지 됩니다.

### <a name="set-your-display-scaling-setting-to-100"></a>디스플레이 설정을 100%로 크기 조정 설정

Windows 10에서 100%로 설정 크기 조정 하 여 표시를 설정 하려면 다음을 입력 **설정 표시** 작업 표시줄을 선택 하 고 검색 상자에에서 **표시 설정 변경**합니다. 에 **설정을** 창에서 **텍스트, 앱 및 기타 항목의 크기를 변경** 에 **100%** 합니다.

100%로 크기 조정 디스플레이 설정 적절 하지 않을, 있으므로 사용자 인터페이스를 사용할 수 있으려면 너무 작습니다.

## <a name="disable-notifications"></a>알림 사용 안 함

Visual Studio에서 문제를 크기 조정의 DPI 알릴 필요가 선택할 수 있습니다. 예를 들어 디자이너에서 작업 하지 않는 경우 알림을 사용 하지 않도록 설정 하려는 경우.

알림 사용 안 함, 선택 **도구** > **옵션** 열려는 합니다 **옵션** 대화 합니다. 그런 다음, 선택 **Windows Forms 디자이너** > **일반**, 설정 **DPI 크기 조정 알림** 에 **False**합니다.

![Visual Studio에서 알림 옵션을 확장 하는 DPI](./media/disable-dpi-awareness-visual-studio/notifications-option.png)

나중에 다시 크기 조정 알림을 사용 하도록 설정 하려는 경우 속성을 설정 **True**합니다.

## <a name="troubleshoot"></a>문제 해결

DPI 인식 전환 Visual Studio에서 예상 대로 작동 하지 않는 경우 확인 해야 합니다 `dpiAwareness` 값을 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image 파일 실행 Options\devenv.exe**  레지스트리 편집기에서 하위 키입니다. 있는 경우 값을 삭제 합니다.

## <a name="see-also"></a>참고자료

- [Windows Forms의 자동 크기 조정](automatic-scaling-in-windows-forms.md)
