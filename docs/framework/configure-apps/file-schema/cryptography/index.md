---
title: 암호화 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088000"
---
# <a name="cryptography-settings-schema"></a>암호화 설정 스키마
암호 설정 스키마에는 암호화 알고리즘을 구현하는 클래스에 알고리즘 이름을 매핑하는 방법을 지정하는 요소가 포함되어 있습니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|요소|Description|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|요소의 이름에 매핑되는 암호화 클래스의 목록을 포함 **\<nameEntry>** 합니다.|  
|[**\<cryptoClass**>](cryptoclass-element.md)|요소의 이름에 매핑되는 암호화 클래스를 포함 **\<nameEntry>** 합니다.|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|암호화 설정이 포함되어 있습니다.|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|이름에 대한 클래스의 매핑이 포함되어 있습니다.|  
|[**\<mscorlib>** 암호화 설정에 대 한 요소](mscorlib-element-for-cryptography-settings.md)|요소를 포함 **\<cryptographySettings>** 합니다.|  
|[**\<nameEntry>**](nameentry-element.md)|클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.|  
|[**\<oidEntry>**](oidentry-element.md)|ASN.1 OID(개체 식별자)를 이름에 매핑합니다.|  
|[**\<oidMap>**](oidmap-element.md)|클래스에 대한 ASN.1 OID 매핑이 포함되어 있습니다.|  
  
## <a name="see-also"></a>참조

- [구성 파일 스키마](../index.md)
- [암호화 서비스](../../../../standard/security/cryptographic-services.md)
