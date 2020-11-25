---
title: 마이그레이션 지침
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: b9b90aedc06fb4a4564596d61aa0ac2dc4c6143f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733596"
---
# <a name="migration-guidance"></a>마이그레이션 지침

.NET Framework 4에서 Microsoft는 두 번째 주요 버전의 WF (Windows Workflow Foundation)를 출시 하 고 있습니다. [!INCLUDE[wf1](../../../includes/wf1-md.md)] 은 (는) WinFX에서 릴리스 되었으며 ( \* WF3 라고 함), 3.5 .NET Framework에서 향상 되었습니다. WF3는 .NET Framework 4의 일부 이기도 하지만 새 워크플로 기술 (W F 4의 형식 \* , 이라고 함)과 함께 존재 합니다. WF4 사용을 고려하는 경우 타이밍을 제어한다는 점을 먼저 인식해야 합니다.

- WF3는 .NET Framework 4의 완전히 지원 되는 부분입니다.

- WF3 응용 프로그램은 수정 없이 .NET Framework 4에서 실행 되며 완전히 지원 됩니다.

- 새 WF3 응용 프로그램을 만들 수 있으며 Visual Studio 2012에서 기존 응용 프로그램을 편집할 수 있으며 완전히 지원 됩니다.

 따라서 .NET Framework 4를 채택 하는 결정은 \* WF3 ()에서 w f 4 ()로 이동 하는 결정에서 분리 됩니다. \* 이 항목에서는 WF3 및 WF4 작업에 대한 정보를 담은 WF 마이그레이션 지침의 링크를 제공합니다.

## <a name="wf-migration-white-papers-and-cookbooks"></a>WF 마이그레이션 백서 및 cookbook

 [WF 마이그레이션 개요](/previous-versions/appfabric/ff383417(v=azure.10)) 항목에서는 WF3와 w f 4 및 마이그레이션 전략 간의 관계에 대 한 광범위 한 개요를 제공 합니다. 관련 항목에서는 특정 항목을 자세히 다룹니다.

 [WF 마이그레이션 개요](/previous-versions/appfabric/ff383417(v=azure.10)) WF3와 W F 4 간의 관계를 설명 하 고 .NET Framework 4에서 사용자 또는 워크플로 기술의 잠재적 사용자로 선택 된 항목을 설명 합니다.

 [WF 마이그레이션: WF3 개발에 대 한 모범 사례](/previous-versions/appfabric/ff383417(v=azure.10)) W F 4로 쉽게 마이그레이션할 수 있도록 WF3 아티팩트를 디자인 하는 방법에 대해 설명 합니다.

 [WF 지침: 규칙](/previous-versions/appfabric/ff383417(v=azure.10)) 규칙 관련 투자를 .NET Framework 4 솔루션으로 가져오는 방법을 설명 합니다.

 [WF 지침: 상태 시스템](/previous-versions/appfabric/ff383417(v=azure.10)) State-Machine 활동이 없는 W F 4 제어 흐름 모델링에 대해 설명 합니다.

 이 지침은 .NET Framework 4를 대상으로 하는 워크플로 프로젝트에만 적용됩니다. 상태 시스템 워크플로는 .NET Framework 4.0.1에 플랫폼 업데이트 1 릴리스와 함께 추가 되었으며 .NET Framework 4.5의 일부로 포함 되었습니다. .NET Framework 4.0.1-4.0.3 및 .NET Framework 4.5의 상태 시스템 워크플로에 대 한 자세한 내용은 [Update 4.0.1 for Microsoft .NET Framework 4 Features](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) And [state machine 워크플로만](state-machine-workflows.md)항목을 참조 하세요.

 [WF Migration Cookbook: 사용자 지정 작업](/previous-versions/appfabric/ff383417(v=azure.10)) W F 4에서 WF3 사용자 지정 작업을 다시 디자인 하기 위한 예제와 지침을 제공 합니다.

 [WF Migration Cookbook: 고급 사용자 지정 작업](/previous-versions/appfabric/ff383417(v=azure.10)) WF3 큐를 사용 하 고 자식 활동을 WF3 사용자 지정 활동으로 예약 하는 고급 사용자 지정 활동을 다시 디자인 하는 지침을 제공 합니다.

 [WF Migration Cookbook: 워크플로](/previous-versions/appfabric/ff383417(v=azure.10)) W F 4에서 WF3 워크플로를 다시 디자인 하는 방법에 대 한 예제와 지침을 제공 합니다.

 [WF 마이그레이션 Cookbook: 워크플로 호스팅](/previous-versions/appfabric/ff383417(v=azure.10)) WF3 호스팅 코드를 W F 4 호스팅 코드로 다시 디자인 하기 위한 지침을 제공 합니다. 이 설명서의 목적은 WF3과 WF4 간의 주요 워크플로 호스팅 차이점을 설명하는 것입니다.

 [WF 마이그레이션 Cookbook: 워크플로 추적](/previous-versions/appfabric/ff383417(v=azure.10)) 동일한 W F 4 추적 코드 및 구성을 사용 하 여 WF3 추적 코드 및 구성을 다시 디자인 하기 위한 지침을 제공 합니다.

 [WF 지침: 워크플로 서비스](/previous-versions/appfabric/ff383417(v=azure.10)) 기본 제공 활동에 대 한 일반적인 시나리오에 대해 W F 4를 사용 하기 위해 WF3에서 만든 WCF (Windows Communication Foundation) 웹 서비스 (일반적으로 워크플로 서비스 라고 함)를 구현 하는 워크플로를 다시 디자인 하는 방법에 대 한 예제 기반의 단계별 지침을 제공 합니다.

## <a name="see-also"></a>참조

- <xref:System.Activities.Statements.Interop>
