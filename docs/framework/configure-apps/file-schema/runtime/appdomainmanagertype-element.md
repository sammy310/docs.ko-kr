---
title: <appDomainManagerType> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154430"
---
# <a name="appdomainmanagertype-element"></a>\<appDomainManagerType> 요소
기본 애플리케이션 도메인용 애플리케이션 도메인 관리자로 사용되는 유형을 지정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<앱도메인관리자유형>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`value`|필수 특성입니다. 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 역할을 하는 네임스페이스를 포함 하 여 형식의 이름을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램 도메인 관리자의 형식을 지정하려면 이 요소와 [ \<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) 요소를 모두 지정해야 합니다. 이러한 요소 중 하나를 지정하지 않으면 다른 요소는 무시됩니다.  
  
 기본 응용 프로그램 도메인이 <xref:System.TypeLoadException> 로드될 때 [ \<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) 요소에 의해 지정된 어셈블리에 지정된 형식이 없는 경우 throw됩니다. 프로세스가 시작되지 않습니다.  
  
 기본 응용 프로그램 도메인에 대한 응용 프로그램 도메인 관리자 유형을 지정하면 기본 응용 프로그램 도메인에서 만든 다른 응용 프로그램 도메인은 응용 프로그램 도메인 관리자 유형을 상속합니다. <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> 및 속성을 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 사용하여 새 응용 프로그램 도메인에 대해 다른 응용 프로그램 도메인 관리자 유형을 지정합니다.  
  
 응용 프로그램 도메인 관리자 유형을 지정하려면 응용 프로그램에 대한 완전한 신뢰가 있어야 합니다. (예를 들어, 데스크톱에서 실행 중인 애플리케이션에 완전 신뢰) 애플리케이션에 완전 신뢰가 없는 경우는 <xref:System.TypeLoadException> throw 됩니다.  
  
 형식 및 네임스페이스의 형식은 속성에 사용되는 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 형식과 동일합니다.  
  
 이 구성 요소는 .NET Framework 4 이상에서만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 `MyMgr` 프로그램 `AdMgrExample` 도메인 관리자가 어셈블리의 형식임을 지정 하는 방법을 보여 주면 됩니다.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<app도메인관리자어셈블리> 요소](appdomainmanagerassembly-element.md)
- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [SetAppDomainManagerType 메서드](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
