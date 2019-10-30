---
title: <PreferComInsteadOfManagedRemoting> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 47c568a8d6e89a195414552b3db5953ee61d1e55
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116010"
---
# <a name="prefercominsteadofmanagedremoting-element"></a>\<PreferComInsteadOfManagedRemoting > 요소
런타임이 응용 프로그램 도메인 경계를 넘어 모든 호출에 대해 원격 대신 COM interop을 사용할지 여부를 지정 합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting >**  
  
## <a name="syntax"></a>구문  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 응용 프로그램 도메인 경계를 넘어 원격이 아닌 COM interop 사용 하는지 여부를 나타냅니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임은 응용 프로그램 도메인 경계에서 원격 기능을 사용 합니다. 기본값입니다.|  
|`true`|런타임은 응용 프로그램 도메인 경계에 걸쳐 COM interop를 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>주의  
 `enabled` 특성을 `true`로 설정 하면 런타임은 다음과 같이 동작 합니다.  
  
- 런타임은 [iunknown](https://go.microsoft.com/fwlink/?LinkId=148003) 인터페이스가 COM 인터페이스를 통해 도메인에 들어가면 [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대해 [iunknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) 를 호출 하지 않습니다. 대신, 개체 주위에서 RCW ( [런타임 호출 가능 래퍼](../../../../standard/native-interop/runtime-callable-wrapper.md) )를 생성 합니다.  
  
- 런타임은이 도메인에서 만들어진 ccw ( [COM 호출 가능 래퍼](../../../../standard/native-interop/com-callable-wrapper.md) )에 대 한 [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대 한 `QueryInterface` 호출을 받을 때 E_NOINTERFACE를 반환 합니다.  
  
 이러한 두 동작은 응용 프로그램 도메인 경계에서 관리 되는 개체 간의 COM 인터페이스에 대 한 모든 호출이 원격 대신 COM 및 COM interop을 사용 하도록 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 런타임이 격리 경계를 넘어 COM interop를 사용 하도록 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
