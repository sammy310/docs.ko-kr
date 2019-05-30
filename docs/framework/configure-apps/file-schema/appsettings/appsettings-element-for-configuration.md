---
title: <configuration>에 대한 <appSettings> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: e8f85be2efe972fc45230855d18649a89f2fbd61
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300814"
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings > 요소에 대 한 \<구성 >

사용자 지정 응용 프로그램 설정을 포함합니다. .NET Framework에서 제공 하는 미리 정의 된 구성 섹션입니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp; **\<appSettings>**

## <a name="syntax"></a>구문

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **file**  | 선택적 특성입니다.<br><br>사용자 지정 응용 프로그램 구성 설정이 포함 된 외부 파일에 상대 경로 지정 합니다. 지정한 파일에 지정 된 설정의 동일한 종류에는  **\<추가 >** 를  **\<제거 >** , 및  **\<지우기 >** 요소와 해당 요소와 동일한 키/값 쌍 형식을 사용 합니다.<br><br>지정 된 경로 기본 구성 파일에 상대적입니다. Windows Forms 응용 프로그램의 경우 이진 폴더입니다 (같은 */bin/debug*), 응용 프로그램 구성 파일의 위치가 아닌 합니다. Web Forms 응용 프로그램에 대 한 경로가 응용 프로그램 루트에 상대적인 위치를 *web.config* 파일이.<br><br>에서는 런타임에 지정된 된 파일을 찾을 수 없는 경우 특성을 무시 하는 note 합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [ **\<구성 >** 요소](~/docs/framework/configure-apps/file-schema/configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [ **\<add>** ](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | 사용자 지정 응용 프로그램 설정을 추가합니다. |
| [ **\<clear>** ](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | 모든 이전에 정의 된 응용 프로그램 설정을 지웁니다. |
| [ **\<remove>** ](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | 이전에 정의 된 응용 프로그램 설정을 제거합니다. |

## <a name="remarks"></a>설명

합니다  **\<appSettings >** 데이터베이스 연결 문자열, 파일 경로, XML 웹 서비스 Url 또는 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 구성 정보를 저장 하는 요소는 응용 프로그램입니다. 에 지정 된 키/값 쌍을  **\<appSettings >** 사용 하 여 코드에 액세스 하는 요소는 <xref:System.Configuration.ConfigurationSettings> 클래스입니다.

사용할 수는 **파일** 특성을  **\<appSettings >** 요소의 *Web.config* 및 응용 프로그램 구성 파일입니다. 이 특성에 지정 된 설정을 재정의 또는 추가 설정을 제공 하는 구성 파일을 지정 합니다  **\<appSettings >** 요소입니다. 합니다 **파일** 특성은 사용자가 응용 프로그램 구성 파일에 지정 된 프로젝트 설정 재정의 하려고 할 때와 같은 원본 제어 팀 개발 시나리오에서 사용할 수 있습니다.

지정 된 구성 파일을 **파일** 특성의 루트 노드에 있어야 합니다.  **\<appSettings >** 대신  **\<구성 >** .

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

## <a name="configuration-file"></a>구성 파일

응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
