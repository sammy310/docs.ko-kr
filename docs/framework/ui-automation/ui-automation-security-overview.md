---
title: UI 자동화 보안 개요
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: 70d24c3dcc531abcec6d4dce75b5f0b31757e0c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448777"
---
# <a name="ui-automation-security-overview"></a>UI 자동화 보안 개요

> [!NOTE]
> 이 설명서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 네임스페이스에 정의된 관리되는 <xref:System.Windows.Automation> 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.

이 개요에서는 Windows Vista의 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]에 대 한 보안 모델을 설명 합니다.

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>사용자 계정 컨트롤(User Account Control)

보안은 Windows Vista의 주요 초점은 사용자가 더 높은 권한이 필요한 응용 프로그램 및 서비스를 실행할 수 없도록 차단 되지 않고 표준 (비관리자) 사용자로 실행할 수 있는 기능입니다.

Windows Vista에서는 대부분의 응용 프로그램에 표준 또는 관리 토큰이 제공 됩니다. 애플리케이션을 관리 애플리케이션으로 식별할 수 없는 경우 기본적으로 표준 애플리케이션으로 시작됩니다. 관리로 식별 된 응용 프로그램을 시작할 수 있기 전에 Windows Vista에서 사용자에 게 관리자 권한으로 응용 프로그램을 실행 하는 데 동의 하는지 묻는 메시지를 표시 합니다. 관리자 자격 증명이 필요한 애플리케이션 또는 시스템 구성 요소가 실행 권한을 요청할 때까지 관리자가 표준 사용자로 실행되므로 사용자가 로컬 관리자 그룹의 멤버인 경우에도 동의 확인 프롬프트가 기본적으로 표시됩니다.

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>더 높은 권한이 필요한 작업

사용자가 관리자 권한이 필요한 작업을 수행 하려고 하면 Windows Vista에서 사용자에 게 동의를 요청 하는 대화 상자가 표시 됩니다. 이 대화 상자는 악성 소프트웨어가 사용자 입력을 시뮬레이션할 수 없도록 크로스 프로세스 통신으로부터 보호됩니다. 마찬가지로, 데스크톱 로그온 화면은 일반적으로 다른 프로세스에서 액세스할 수 없습니다.

UI 자동화 클라이언트는 더 높은 권한 수준에서 실행 중일 수도 있는 다른 프로세스와 통신해야 합니다. 클라이언트가 일반적으로 다른 프로세스에 표시되지 않는 시스템 대화 상자에 액세스해야 할 수도 있습니다. 따라서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트는 시스템에서 신뢰되어야 하며 특수 권한으로 실행되어야 합니다.

더 높은 권한 수준에서 실행 중인 애플리케이션과 통신할 수 있도록 신뢰되려면 애플리케이션에 서명해야 합니다.

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>매니페스트 파일

보호 된 시스템 UI에 대 한 액세스 권한을 얻으려면 다음과 같이 `requestedExecutionLevel` 태그에 `uiAccess` 특성을 포함 하는 매니페스트 파일을 사용 하 여 응용 프로그램을 빌드해야 합니다.

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

이 코드에서 `level` 특성의 값은 예제일 뿐입니다.

`uiAccess`은 기본적으로 "false"입니다. 즉, 특성을 생략 하거나 어셈블리에 대 한 매니페스트가 없는 경우 응용 프로그램은 보호 된 UI에 대 한 액세스 권한을 얻을 수 없습니다.
