---
title: 마이그레이션 지침
description: '자세히 알아보기: 마이그레이션 지침'
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 83c6af4d8eed396501aafc568de8e64d30ae7cfe
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104863"
---
# <a name="migration-guidance"></a>마이그레이션 지침

.NET Framework 4에서 Microsoft는 두 번째 주요 버전의 WF (Windows Workflow Foundation)를 출시 했습니다. [!INCLUDE[wf1](../../../includes/wf1-md.md)] 은 (는) WinFX에서 릴리스 되었으며 ( \* WF3 라고 함), 3.5 .NET Framework에서 향상 되었습니다. WF3는 .NET Framework 4의 일부 이기도 하지만 새 워크플로 기술 (W F 4의 형식 \* , 이라고 함)과 함께 존재 합니다. WF4 사용을 고려하는 경우 타이밍을 제어한다는 점을 먼저 인식해야 합니다.

- WF3는 .NET Framework 4의 완전히 지원 되는 부분입니다.

- WF3 응용 프로그램은 수정 없이 .NET Framework 4에서 실행 되 고 완벽 하 게 지원 됩니다.

- 새 WF3 응용 프로그램을 만들 수 있으며 Visual Studio 2012에서 기존 응용 프로그램을 편집할 수 있으며 완전히 지원 됩니다.

따라서 .NET Framework 4를 채택 하기로 결정 하는 것은 \* WF3 (w f 4)에서의 결정에 따라 이동 하도록 결정 됩니다. \* 이 항목에서는 WF3 및 WF4 작업에 대한 정보를 담은 WF 마이그레이션 지침의 링크를 제공합니다.

## <a name="wf-migration-white-papers-and-cookbooks"></a>WF 마이그레이션 백서 및 cookbook

 [WF 마이그레이션 개요](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Overview.docx)\
 WF3와 W F 4 간의 관계를 설명 하 고 .NET Framework 4에서 사용자 또는 워크플로 기술의 잠재적 사용자로 선택 된 항목을 설명 합니다.

 [WF 마이그레이션: WF3 개발에 대 한 모범 사례](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Best%20Practices.docx)\
 WF4로 쉽게 마이그레이션할 수 있도록 WF3 아티팩트를 디자인하는 방법을 설명합니다.

 [WF 지침: 규칙](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20Rules%20Guidance.docx)\
 규칙 관련 투자를 .NET Framework 4 솔루션으로 가져오는 방법을 설명 합니다.

 [WF 지침: 상태 시스템](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20State%20Machine%20Guidance.doc) State-Machine 활동이 없는 W F 4 제어 흐름 모델링에 대해 설명 합니다. 이 지침은 .NET Framework 4를 대상으로 하는 워크플로 프로젝트에만 적용 됩니다. 상태 시스템 워크플로는 .NET Framework 4.0.1에 플랫폼 업데이트 1 릴리스와 함께 추가 되었으며 .NET Framework 4.5의 일부로 포함 되었습니다. .NET Framework 4.0.1-4.0.3 및 .NET Framework 4.5의 상태 시스템 워크플로에 대 한 자세한 내용은 [Update 4.0.1 for Microsoft .NET Framework 4 Features](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) And [state machine 워크플로만](state-machine-workflows.md)항목을 참조 하세요.

 [WF Migration Cookbook: 사용자 지정 작업](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Custom%20Activities.docx)\
 WF4에서 WF3 사용자 지정 활동을 다시 디자인하기 위한 지침과 예를 제공합니다.

 [WF Migration Cookbook: 고급 사용자 지정 작업](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Advanced%20Custom%20Activities.docx)\
 WF3 큐를 사용하고 자식 활동을 WF4 사용자 지정 활동으로 예약하는 고급 WF3 사용자 지정 활동을 다시 디자인하기 위한 지침을 제공합니다.
%20 [WF Migration Cookbook: 워크플로](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflows.docx)\
 WF4에서 WF3 워크플로를 다시 디자인하기 위한 지침과 예를 제공합니다.

 [WF 마이그레이션 Cookbook: 워크플로 호스팅](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflow%20Hosting.docx)\
 WF3 호스팅 코드를 WF4 호스팅 코드로 다시 디자인하기 위한 지침을 제공합니다. 이 설명서의 목적은 WF3과 WF4 간의 주요 워크플로 호스팅 차이점을 설명하는 것입니다.

 [WF 마이그레이션 Cookbook: 워크플로 추적](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflow%20Tracking.docx)\
 WF3 추적 코드 및 구성을 해당하는 WF4 추적 코드 및 구성을 사용하여 다시 디자인하기 위한 지침을 제공합니다.

 [WF 지침: 워크플로 서비스](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20Workflow%20Services%20Guidance.docx)\
 일반적인 기본 제공 활동의 시나리오에서 WF3으로 만들어진 WCF(Windows Communication Foundation) 웹 서비스(일반적으로 워크플로 서비스라고 함)를 구현하는 워크플로를 WF4를 사용하도록 다시 디자인하기 위한 단계별 지침을 예제 중심으로 제공합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Activities.Statements.Interop>
