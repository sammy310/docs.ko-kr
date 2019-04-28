---
title: 시작 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
  - startup settings schema
  - schema startup settings
  - 'configuration schema [.NET Framework], startup settings'
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
---
# <a name="startup-settings-schema"></a>시작 설정 스키마

시작 설정은 애플리케이션을 실행해야 하는 공용 언어 런타임의 버전을 지정합니다.  
  
|요소|설명|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다. 런타임 버전 1.1로 빌드된 응용 프로그램은 **\<supportedRuntime>** 요소를 사용해야 합니다.|  
|[\<supportedRuntime>](supportedruntime-element.md)|응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.|  
|[\<startup>](startup-element.md)|**\<requiredRuntime>** 및 **\<supportedRuntime>** 요소가 포함되어 있습니다.|  
  
## <a name="see-also"></a>참고자료

- [구성 파일 스키마](../index.md)
- [방법: .NET Framework 4 이상 버전을 지원하도록 앱 구성](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
