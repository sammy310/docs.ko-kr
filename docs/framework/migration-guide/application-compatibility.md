---
title: 런타임 및 대상 다시 지정 변경 내용 - .NET Framework
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: c46f781d495b87a4f24e77935df7c4814c8567ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73196704"
---
# <a name="application-compatibility-in-the-net-framework"></a>.NET Framework의 애플리케이션 호환성

호환성은 각 .NET 릴리스의 중요한 목표입니다. 호환성이 있으면 각 버전이 누적되므로 이전 버전이 계속 작동합니다. 반면, 예를 들어 성능 향상, 보안 문제 해결 또는 버그 수정을 위해 이전 기능이 변경되면 이후 버전에서 실행되는 기존 코드 또는 기존 애플리케이션에서 호환성 문제가 발생할 수 있습니다.

각 앱은 다음을 통해 .NET Framework의 특정 버전을 대상으로 합니다.

- Visual Studio에서 대상 프레임워크 정의
- 프로젝트 파일에서 대상 프레임워크 지정
- 소스 코드에 <xref:System.Runtime.Versioning.TargetFrameworkAttribute> 적용

한 버전의 .NET Framework에서 다른 버전으로 마이그레이션할 때는 다음과 같은 두 가지 변경 유형을 고려해야 합니다.

- [런타임 변경 내용](#runtime-changes)
- [대상 다시 지정 변경 내용](#retargeting-changes)

## <a name="runtime-changes"></a>런타임 변경 내용

런타임 문제는 새 런타임이 컴퓨터에서 발생하고 앱의 동작이 변경되는 경우 발생하는 문제입니다. 대상으로 지정된 버전보다 더 새로운 버전에서 실행될 경우 .NET Framework는 *quirked* 동작을 사용하여 대상으로 지정된 이전 버전을 모방합니다. 앱은 최신 버전에서 실행되지만 이전 버전에서 실행되는 것처럼 작동합니다. .NET Framework 버전 간의 대부분의 호환성 문제는 이 특수 모델을 통해 완화됩니다. 예를 들어 .NET Framework 4.0에 대해 이진이 컴파일되었지만 .NET Framework 4.5 이상이 설정된 컴퓨터에서 실행되는 경우 .NET Framework 4.0 호환 모드에서 실행됩니다. 즉, 최신 버전의 많은 변경 내용은 이진에 영향을 주지 않습니다.

애플리케이션의 대상이 되는 .NET Framework 버전은 코드가 실행되는 애플리케이션 도메인의 항목 어셈블리의 대상 버전에 따라 결정됩니다. 해당 애플리케이션 도메인에 로드된 모든 추가 어셈블리는 이 버전을 대상으로 합니다. 예를 들어, 실행 파일의 경우, 실행 파일의 대상 버전은 해당 애플리케이션 도메인의 모든 어셈블리가 실행되는 호환 모드입니다.

사용자 환경에 적용되는 런타임 변경 내용 목록을 보려면 현재 대상으로 하는 .NET Framework 버전을 선택하고 마이그레이션할 버전을 선택합니다.

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a>대상 다시 지정 변경 내용

대상 다시 지정 변경 내용은 새 버전을 대상으로 하는 어셈블리를 다시 컴파일할 때 발생하는 변경 내용입니다. 새 버전으로 대상을 지정하면 어셈블리는 이전 기능에 대한 잠재적인 호환성 문제뿐 아니라 새로운 기능을 선택합니다.

사용자 환경에 적용되는 대상 다시 지정 변경 내용 목록을 보려면 현재 대상으로 하는 .NET Framework 버전을 선택하고 마이그레이션할 버전을 선택합니다.

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a>영향 분류

런타임 및 대상 다시 지정 변경 내용을 설명하는 주제(예: [4.7.2에서 4.8로 마이그레이션에 대한 대상 다시 지정 변경 내용](retargeting/4.7.2-4.8.md))에서 개별 항목은 다음과 같이 예상되는 영향별로 분류됩니다.

**Major**\
다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다.

**Minor**\
소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.

**특별한 경우**\
일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.

**투명**\
앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다. 이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.

## <a name="see-also"></a>참고 항목

- [버전 및 종속성](versions-and-dependencies.md)
- [새로운 기능](../whats-new/index.md)
- [사용되지 않는 기능](../whats-new/whats-obsolete.md)
