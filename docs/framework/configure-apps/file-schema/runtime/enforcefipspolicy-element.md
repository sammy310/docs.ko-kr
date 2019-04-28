---
title: <enforceFIPSPolicy> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1aa958e15449949a1b7ca740198fff71295b2ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704965"
---
# <a name="enforcefipspolicy-element"></a>\<enforceFIPSPolicy > 요소
암호화 알고리즘이 FIPS(Federal Information Processing Standards)를 준수해야 하는 컴퓨터 구성 요구 사항을 적용할지를 지정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<enforceFIPSPolicy > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> 암호화 알고리즘이 FIPS와 호환 되도록 컴퓨터 구성 요구 사항의 적용을 사용할 것인지를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|컴퓨터가 암호화 알고리즘을 fips 준수를 요구 하도록을 구성 하는 경우 해당 요구 사항을 적용 됩니다. 클래스 생성자를 FIPS와 호환 되지 않는 알고리즘을 구현 하는 경우 또는 `Create` 메서드는 클래스에 대 한 해당 컴퓨터에서 실행 될 때 예외를 throw 합니다. 이 값이 기본값입니다.|  
|`false`|응용 프로그램에서 사용 되는 암호화 알고리즘 컴퓨터 구성에 관계 없이 FIPS와 호환 되도록 필요 하지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 2.0부터 컴퓨터의 구성에 따라 암호화 알고리즘을 구현 하는 클래스의 생성 제어 됩니다. 컴퓨터 알고리즘을 FIPS를 준수를 요구 하도록 구성 된 FIPS와 호환 되지 않는 알고리즘을 구현 하는 클래스를 해당 클래스의 인스턴스를 만들려고 시도 예외가 throw 됩니다. 생성자가 throw를 <xref:System.InvalidOperationException> 예외 및 `Create` 메서드는 throw를 <xref:System.Reflection.TargetInvocationException> 내부 예외 <xref:System.InvalidOperationException> 예외입니다.  
  
 구성 파일에는 CLR (공용 언어 런타임)에서 사용 하지 않으려면이 요소를 사용 수는 구성이 필요 FIPS 준수 하는 컴퓨터에서 응용 프로그램을 실행 하는 경우 FIPS와 호환 되지 않는 알고리즘을 사용 하는 응용 프로그램 FIPS 준수를 적용 합니다. 이 요소에 도입 된 [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)]합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 CLR FIPS 준수를 적용 하지 못하도록 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [암호화 모델](../../../../../docs/standard/security/cryptography-model.md)
