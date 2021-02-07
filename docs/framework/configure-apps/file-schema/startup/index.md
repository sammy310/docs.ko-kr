---
description: '자세한 정보: 시작 설정 스키마'
title: 시작 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: 268b8d8dc2598add61435dd6b07031aa06831737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726093"
---
# <a name="startup-settings-schema"></a>시작 설정 스키마

시작 설정은 애플리케이션을 실행해야 하는 공용 언어 런타임의 버전을 지정합니다.  
  
|요소|설명|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다. 런타임 버전 1.1로 빌드된 응용 프로그램은 요소를 사용 해야 합니다 **\<supportedRuntime>** .|  
|[\<supportedRuntime>](supportedruntime-element.md)|애플리케이션이 지원하는 공용 언어 런타임 버전을 지정합니다.|  
|[\<startup>](startup-element.md)|**\<requiredRuntime>** 및 요소를 포함 **\<supportedRuntime>** 합니다.|  
  
## <a name="see-also"></a>참조

- [구성 파일 스키마](../index.md)
- [방법: .NET Framework 4 이상 버전을 지원하도록 앱 구성](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
