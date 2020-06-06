---
title: 앱 설정 스키마
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: 0a3363b35a6fc8bd27753eb034f8a1e95feb5292
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215422"
---
# <a name="app-settings-schema"></a>앱 설정 스키마

파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| 요소 | Description |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | **\<add>** **\<clear>** **\<remove>** 응용 프로그램 설정을 제어 하는, 및 태그를 포함 합니다. 선택적 **파일** 특성이 있습니다. |
| [**\<add>**](add-element-for-appsettings.md) | 설정을 정의합니다. 의 자식 **\<appSettings>** 입니다. **키** 및 **값** 특성이 필요합니다. |
| [**\<clear>**](clear-element-for-appsettings.md) | 모든 설정을 지웁니다. 의 자식 **\<appSettings>** 입니다. 특성이 없습니다. |
| [**\<remove>**](remove-element-for-appsettings.md) | 설정을 제거합니다. 의 자식 **\<appSettings>** 입니다. **키** 특성이 필요합니다. |

## <a name="appsettings-element"></a>\<appSettings> 요소

이 요소 **\<add>** 는 **\<clear>** **\<remove>** 응용 프로그램 설정을 제어 하는, 및 태그를 포함 합니다. **파일**에 대한 선택적 특성을 정의합니다.

## <a name="add-element"></a>\<add> 요소

애플리케이션 설정 컬렉션에 사용자 지정 애플리케이션 설정을 이름/값 쌍으로 추가합니다. **키** 및 **값**에 대한 특성을 정의합니다.

## <a name="clear-element"></a>\<clear> 요소

상속 된 사용자 지정 응용 프로그램 설정에 대 한 모든 참조를 제거 하 고 **\<add>** 요소 다음에 나오는 요소에 의해 추가 된 참조만 허용 합니다 **\<clear>** . 특성 없음을 정의합니다.

## <a name="remove-element"></a>\<remove> 요소

상속된 사용자 지정 애플리케이션 설정에 대한 참조를 애플리케이션 설정 컬렉션에서 제거합니다. **키**에 대한 특성을 정의합니다.

## <a name="example"></a>예제

다음 예제에서는 사용자 지정 애플리케이션 설정을 정의하는 외부 애플리케이션 설정 파일(*custom.config*)을 보여 줍니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 애플리케이션 설정을 지정하는 애플리케이션 구성 파일을 보여 줍니다.

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a>참고 항목

- [애플리케이션 설정 개요](../../../winforms/advanced/application-settings-overview.md)
- [애플리케이션 설정 아키텍처](../../../winforms/advanced/application-settings-architecture.md)
