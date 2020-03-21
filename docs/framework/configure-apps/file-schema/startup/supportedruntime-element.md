---
title: <supportedRuntime>구성 요소 - .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: e16eb098db4bce115a5f1e043829eb272c952860
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153700"
---
# <a name="supportedruntime-element"></a>\<지원되는런타임> 요소

응용 프로그램에서 지원하는 공통 언어 런타임 버전과 선택적으로 .NET Framework 버전을 지정합니다.  

[\<구성>](../configuration-element.md)  
&nbsp;&nbsp;[\<스타트업>](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<지원런타임>**  

## <a name="syntax"></a>구문

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>특성

|attribute|Description|
|---------------|-----------------|
|**version**|선택적 특성입니다.<br /><br /> 애플리케이션이 지원하는 공용 언어 런타임(CLR) 버전을 지정하는 문자열 값입니다. 특성의 유효한 `version` 값에 대 한 ["런타임 버전" 값](#version) 섹션을 참조 하십시오. **참고:**  .NET Framework 3.5를 통해 *"런타임 버전"* 값은 폼 *을 major합니다.* *사소한*. *빌드*. .NET Framework 4부터는 주 버전 과 부 버전 번호만 필요합니다(즉, "v4.0.30319" 대신 "v4.0"). 짧은 문자열이 권장됩니다.|
|**sku**|선택적 특성입니다.<br /><br /> 이 애플리케이션이 지원하는 .NET Framework 버전을 지정하는 SKU(Stock Keeping Unit)를 지정하는 문자열 값입니다.<br /><br /> .NET Framework 4.0을 시작할 때에는 `sku` 특성을 사용하는 것이 좋습니다.  존재한다면 앱이 대상으로 하는 .NET Framework의 버전을 나타냅니다.<br /><br /> sku 특성의 유효한 값은 ["sku id" 값](#sku) 섹션을 참조하십시오.|

## <a name="remarks"></a>설명

** \<지원되는Runtime>** 요소가 응용 프로그램 구성 파일에 없는 경우 응용 프로그램을 빌드하는 데 사용되는 런타임 버전이 사용됩니다.

** \<지원되는런타임>** 요소는 런타임의 버전 1.1 이상을 사용하여 빌드된 모든 응용 프로그램에서 사용해야 합니다. 런타임의 버전 1.0만 지원하도록 빌드된 응용 프로그램은 [ \<필수런타임>](../startup/requiredruntime-element.md) 요소를 사용해야 합니다.

> [!NOTE]
> [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 함수를 사용하여 구성 파일을 지정하는 경우 `<requiredRuntime>` 런타임의 모든 버전에 요소를 사용해야 합니다. `<supportedRuntime>` [CorBindToRuntimeByCfg를](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)사용할 때 요소는 무시됩니다.  
  
.NET Framework 1.1~3.5의 런타임 버전을 지원하는 앱의 경우 여러 버전의 런타임이 지원되면 첫 번째 요소는 우선 순위가 가장 높은 런타임 버전을 지정하고 마지막 요소는 우선 순위가 가장 낮은 버전을 지정해야 합니다. .NET Framework 4.0 이상 버전을 지원하는 앱의 `version` 경우 속성은 .NET Framework 4 및 이후 버전에 공통적인 `sku` CLR 버전을 나타내며, 특성은 앱이 대상으로 하는 단일 .NET Framework 버전을 나타냅니다.

특성이 `sku` 있는 **지원되는Runtime>요소가 구성 파일에 있고 설치된 .NET Framework 버전이 더 낮은 경우 지정된 지원되는 버전이 더 낮으면 응용 프로그램이 실행되지 않고 대신 지원되는 버전을 설치하라는 메시지가 \<** 표시됩니다. 그렇지 않으면 응용 프로그램이 설치된 모든 버전에서 실행하려고 시도하지만 해당 버전과 완전히 호환되지 않으면 예기치 않게 작동할 수 있습니다. .NET Framework 버전 간의 호환성 차이는 [.NET Framework의 응용 프로그램 호환성을](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)참조하십시오. 따라서 쉽게 오류 진단을 위해 응용 프로그램 구성 파일에 이 요소를 포함하는 것이 좋습니다. (새 프로젝트를 만들 때 Visual Studio에서 자동으로 생성된 구성 파일에는 이미 포함되어 있습니다.)
  
> [!NOTE]
> 응용 프로그램에서 [CorBindToRuntimeEx 함수와](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)같은 레거시 활성화 경로를 사용하고 해당 경로가 이전 버전 대신 CLR의 버전 4를 활성화하도록 하거나 응용 프로그램이 .NET Framework 4로 빌드되었지만 .NET Framework의 이전 버전으로 빌드된 혼합 모드 어셈블리에 종속되어 있는 경우 지원되는 런타임 목록에 .NET Framework 4를 지정하기에 충분하지 않습니다. 또한 구성 파일의 `useLegacyV2RuntimeActivationPolicy` `true` [ \<시작> 요소에서](../startup/startup-element.md) 속성을 로 설정해야 합니다. 그러나 이 특성을 `true` 설정하면 이전 버전의 .NET Framework로 빌드된 모든 구성 요소가 빌드된 런타임 대신 .NET Framework 4를 사용하여 실행됩니다.

실행할 수 있는 모든 .NET Framework 버전을 사용하여 애플리케이션을 테스트하는 것이 좋습니다.

<a name="version"></a>
## <a name="runtime-version-values"></a>"런타임 버전" 값
특성은 `runtime` 지정된 응용 프로그램에 필요한 공통 언어 런타임(CLR) 버전을 지정합니다. 모든 .NET 프레임워크 v4.x 버전은 `v4.0` CLR을 지정합니다. 다음 표에는 특성의 *런타임 버전* 값에 대한 유효한 값이 나열됩니다. `version`

|.NET Framework 버전|`version` 특성|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3.5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a>"sku ID" 값

특성은 `sku` TFM(대상 프레임워크 모니커)을 사용하여 앱이 대상으로 하고 실행하는 데 필요한 .NET Framework의 버전을 나타냅니다. 다음 표에는 .NET Framework 4부터 시작하여 특성에서 `sku` 지원하는 유효한 값이 나열됩니다.

|.NET Framework 버전|`sku` 특성|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, 플랫폼 업데이트 1|". 넷 프레임 워크, 버전 = v4.0.1"|
|4.0, Client Profile, 업데이트 1|". NETFramework, 버전= v4.0.1, 프로필=클라이언트"|
|4.0, 플랫폼 업데이트 2|". 넷 프레임 워크, 버전 = v4.0.2"|
|4.0, Client Profile, 업데이트 2|". NETFramework, 버전= v4.0.2, 프로필=클라이언트"|
|4.0, 플랫폼 업데이트 3|". 넷 프레임 워크, 버전 = v4.0.3"|
|4.0, Client Profile, 업데이트 3|". NETFramework, 버전= v4.0.3, 프로필=클라이언트"|
|4.5.|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". 넷 프레임 워크, 버전 = v4.6.2"|
|4.7|". 넷 프레임 워크, 버전 = v4.7"|
|4.7.1|". 넷 프레임 워크, 버전 = v4.7.1"|
|4.7.2|". 넷 프레임 워크, 버전 = v4.7.2"|
|4.8|". 넷 프레임 워크, 버전 = v4.8"|

## <a name="example"></a>예제

다음 예제에서는 구성 파일에 지원되는 런타임 버전을 지정하는 방법을 보여줍니다. 구성 파일은 앱이 .NET Framework 4.7을 대상으로 한다는 것을 나타냅니다.

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

- [시작 설정 스키마](../startup/index.md)
- [구성 파일 스키마](../index.md)
- [In-Process Side-by-Side 실행](../../../deployment/in-process-side-by-side-execution.md)
