---
description: '다음에 대 한 자세한 정보: <supportedRuntime> 요소'
title: <supportedRuntime> 구성 요소-.NET
ms.date: 04/02/2019
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 04c2b3fec591e1b99757085afdddf26c529591b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754500"
---
# <a name="supportedruntime-element"></a>\<supportedRuntime> 요소

응용 프로그램에서 지 원하는 공용 언어 런타임 버전과 선택적으로 .NET Framework 버전을 지정 합니다.  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a>구문

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>특성

|attribute|설명|
|---------------|-----------------|
|**version**|선택적 특성입니다.<br /><br /> 애플리케이션이 지원하는 공용 언어 런타임(CLR) 버전을 지정하는 문자열 값입니다. 특성의 유효한 값 `version` 은 ["런타임 버전" 값](#version) 섹션을 참조 하세요. **참고:**  .NET Framework 3.5를 통해 "*런타임 버전*" 값은 *major* 형식을 사용 합니다. *부*. *빌드*. .NET Framework 4부터 주 버전 및 부 버전 번호만 필요 합니다 (즉, "v 4.0.30319" 대신 "v 4.0"). 짧은 문자열이 권장됩니다.|
|**sku**|선택적 특성입니다.<br /><br /> 이 애플리케이션이 지원하는 .NET Framework 버전을 지정하는 SKU(Stock Keeping Unit)를 지정하는 문자열 값입니다.<br /><br /> .NET Framework 4.0을 시작할 때에는 `sku` 특성을 사용하는 것이 좋습니다.  존재한다면 앱이 대상으로 하는 .NET Framework의 버전을 나타냅니다.<br /><br /> Sku 특성의 유효한 값은 ["sku id" 값](#sku) 섹션을 참조 하세요.|

## <a name="remarks"></a>설명

**\<supportedRuntime>** 응용 프로그램 구성 파일에 요소가 없는 경우 응용 프로그램을 빌드하는 데 사용 되는 런타임 버전이 사용 됩니다.

**\<supportedRuntime>** 버전 1.1 이상을 사용 하 여 빌드된 모든 응용 프로그램에서 요소를 사용 해야 합니다. 런타임 버전 1.0만 지원 하도록 빌드된 응용 프로그램은 요소를 사용 해야 합니다 [\<requiredRuntime>](requiredruntime-element.md) .

> [!NOTE]
> [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 함수를 사용 하 여 구성 파일을 지정 하는 경우 `<requiredRuntime>` 모든 버전의 런타임에 대해 요소를 사용 해야 합니다. `<supportedRuntime>` [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)를 사용 하는 경우 요소는 무시 됩니다.  
  
.NET Framework 1.1~3.5의 런타임 버전을 지원하는 앱의 경우 여러 버전의 런타임이 지원되면 첫 번째 요소는 우선 순위가 가장 높은 런타임 버전을 지정하고 마지막 요소는 우선 순위가 가장 낮은 버전을 지정해야 합니다. .NET Framework 4.0 이상 버전을 지 원하는 앱의 경우 특성은 `version` .NET Framework 4 이상 버전에 공통 된 CLR 버전을 나타내며, `sku` 특성은 앱이 대상으로 하는 단일 .NET Framework 버전을 나타냅니다.

**\<supportedRuntime>** 특성이 있는 요소가 `sku` 구성 파일에 있고 설치 된 .NET Framework 버전이 지원 되는 지정 된 버전 보다 낮으면 응용 프로그램이 실행 되지 않고, 지원 되는 버전을 설치 하 라는 메시지가 표시 됩니다. 그렇지 않으면 응용 프로그램이 설치 된 모든 버전에서 실행을 시도 하지만 해당 버전과 완전히 호환 되지 않으면 예기치 않게 동작할 수 있습니다. .NET Framework 버전 간의 호환성 차이점 [은 .NET Framework의 응용 프로그램 호환성](../../../migration-guide/application-compatibility.md)을 참조 하세요. 따라서 보다 쉬운 오류 진단을 위해이 요소를 응용 프로그램 구성 파일에 포함 하는 것이 좋습니다. (새 프로젝트를 만들 때 자동으로 생성 된 구성 파일에는 Visual Studio가 이미 포함 되어 있습니다.)
  
> [!NOTE]
> 응용 프로그램에서 [CorBindToRuntimeEx 함수와](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)같은 레거시 활성화 경로를 사용 하 고 이러한 경로를 사용 하 여 이전 버전 대신 CLR의 버전 4를 활성화 하는 경우 또는 응용 프로그램이 .NET Framework 4로 빌드되고 이전 버전의 .NET Framework를 사용 하 여 빌드된 혼합 모드 어셈블리에 대 한 종속성이 있는 경우 지원 되는 런타임 목록에서 .NET Framework 4를 지정 하는 것 만으로는 충분 하지 않습니다. 또한 구성 파일의 [ \<startup> 요소](startup-element.md) 에서 특성을로 설정 해야 합니다 `useLegacyV2RuntimeActivationPolicy` `true` . 그러나이 특성을로 설정 하면 `true` 이전 버전의 .NET Framework 빌드된 모든 구성 요소가를 사용 하 여 빌드된 런타임 대신 .NET Framework 4를 사용 하 여 실행 됩니다.

실행할 수 있는 모든 .NET Framework 버전을 사용하여 애플리케이션을 테스트하는 것이 좋습니다.

<a name="version"></a>

## <a name="runtime-version-values"></a>"런타임 버전" 값

`runtime`특성은 지정 된 응용 프로그램에 필요한 CLR (공용 언어 런타임) 버전을 지정 합니다. 모든 .NET Framework (v4. x 버전은 CLR을 지정 합니다. `v4.0` 다음 표에서는 특성의 *런타임 버전* 값에 대 한 유효한 값을 보여 줍니다 `version` .

|.NET Framework 버전|`version` 특성|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3.5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a> "sku id" 값

`sku`특성은 TFM (대상 프레임 워크 모니커)를 사용 하 여 앱이 대상으로 하 고 실행 해야 하는 .NET Framework 버전을 표시 합니다. 다음 표에서는 `sku` .NET Framework 4부터 시작 하 여 특성에서 지원 되는 유효한 값을 보여 줍니다.

|.NET Framework 버전|`sku` 특성|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, 플랫폼 업데이트 1|". NETFramework, Version = v 4.0.1 "|
|4.0, Client Profile, 업데이트 1|". NETFramework, Version = v 4.0.1, Profile = Client "|
|4.0, 플랫폼 업데이트 2|". NETFramework, Version = v 4.0.2 "|
|4.0, Client Profile, 업데이트 2|". NETFramework, Version = v 4.0.2, Profile = Client "|
|4.0, 플랫폼 업데이트 3|". NETFramework, Version = v 4.0.3 "|
|4.0, Client Profile, 업데이트 3|". NETFramework, Version = v 4.0.3, Profile = Client "|
|4.5.|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework, Version = v 4.6.2 "|
|4.7|". NETFramework, Version = v 4.7 "|
|4.7.1|". NETFramework, Version = v 4.7.1 "|
|4.7.2|". NETFramework, Version = v 4.7.2 "|
|4.8|". NETFramework, Version = v 4.8 "|

## <a name="example"></a>예제

다음 예제에서는 구성 파일에 지원되는 런타임 버전을 지정하는 방법을 보여줍니다. 구성 파일은 앱이 .NET Framework 4.7를 대상으로 함을 나타냅니다.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 애플리케이션 구성 파일에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [시작 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [In-Process Side-by-Side 실행](../../../deployment/in-process-side-by-side-execution.md)
