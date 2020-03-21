---
title: <startup> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153735"
---
# <a name="startup-element"></a>\<시작> 요소

공통 언어 런타임 시작 정보를 지정합니다.

[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;**\<스타트업>**  

## <a name="syntax"></a>구문

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a>특성 및 요소

 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|attribute|Description|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|선택적 특성입니다.<br /><br /> .NET Framework 2.0 런타임 활성화 정책을 사용하도록 설정하거나 .NET Framework 4 활성화 정책을 사용할지 여부를 지정합니다.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>use레거시V2Runtime활성화정책 특성

|값|Description|
|-----------|-----------------|
|`true`|CLR 버전 2.0에서 해당 를 제한하는 대신 구성 파일에서 선택한 런타임에 레거시 런타임 활성화 기술(예: [CorBindToRuntimeEx 함수)을](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)바인딩하는 선택된 런타임에 대해 .NET Framework 2.0 런타임 활성화 정책을 활성화합니다. 따라서 CLR 버전 4 이상이 구성 파일에서 선택된 경우 이전 버전의 .NET Framework로 만든 혼합 모드 어셈블리가 선택한 CLR 버전으로 로드됩니다. 이 값을 설정하면 CLR 버전 1.1 또는 CLR 버전 2.0이 동일한 프로세스로 로드되지 못하게 되어 프로세스 내 기능을 나란히 사용하지 않도록 효과적으로 설정할 수 있습니다.|
|`false`|.NET Framework 4 이상에 대한 기본 활성화 정책을 사용하여 레거시 런타임 활성화 기술을 사용하여 CLR 버전 1.1 또는 2.0을 프로세스에 로드할 수 있습니다. 이 값을 설정하면 .NET Framework 4 이상으로 빌드되지 않는 한 혼합 모드 어셈블리가 .NET Framework 4 이상에 로드되지 않습니다. 이 값이 기본값입니다.|

### <a name="child-elements"></a>자식 요소

|요소|Description|
|-------------|-----------------|
|[\<필수런타임>](requiredruntime-element.md)|애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다. 런타임 버전 1.1 이상으로 빌드된 응용 프로그램은 ** \<지원되는 런타임>** 요소를 사용해야 합니다.|
|[\<지원런타임>](supportedruntime-element.md)|애플리케이션이 지원하는 공용 언어 런타임 버전을 지정합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|Description|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|

## <a name="remarks"></a>설명

 ** \<지원되는런타임>** 요소는 런타임의 버전 1.1 이상을 사용하여 빌드된 모든 응용 프로그램에서 사용해야 합니다. 런타임의 버전 1.0만 지원하도록 빌드된 응용 프로그램은 ** \<필수런타임>** 요소를 사용해야 합니다.

 Microsoft Internet Explorer에서 호스팅되는 응용 프로그램의 시작 코드는 ** \<시작>** 요소와 자식 요소를 무시합니다.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2Runtime활성화정책 특성

 이 특성은 응용 프로그램이 [CorBindToRuntimeEx 함수와](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)같은 레거시 활성화 경로를 사용하고 해당 경로가 이전 버전 대신 CLR의 버전 4를 활성화하도록 하거나 응용 프로그램이 .NET Framework 4로 빌드되었지만 이전 버전의 .NET Framework로 빌드된 혼합 모드 어셈블리에 종속된 경우 유용합니다. 이러한 시나리오에서는 특성을 `true`로 설정합니다.

> [!NOTE]
> 특성을 설정하여 `true` CLR 버전 1.1 또는 CLR 버전 2.0이 동일한 프로세스로 로드되는 것을 방지하고 프로세스 내 기능을 효과적으로 비활성화합니다(COM [Interop의 경우 나란히 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))참조).

## <a name="example"></a>예제

 다음 예제에서는 구성 파일에서 런타임 버전을 지정하는 방법을 보여 주며 있습니다.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>참고 항목

- [시작 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [방법: .NET Framework 4 이상 버전을 지원하도록 앱을 구성합니다.](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [COM Interop의 Side-By-Side 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [In-Process Side-by-Side 실행](../../../deployment/in-process-side-by-side-execution.md)
