---
title: <gcAllowVeryLargeObjects> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154129"
---
# <a name="gcallowverylargeobjects-element"></a>\<gcAllowVery큰개체> 요소
64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVery큰개체>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 총 크기가 2GB를 초과하는 배열이 64비트 플랫폼에서 활성화되는지 여부를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|총 크기가 2GB를 초과하는 배열은 사용할 수 없습니다. 이것이 기본값입니다.|  
|`true`|총 크기가 2GB를 초과하는 배열은 64비트 플랫폼에서 사용할 수 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램 구성 파일에서 이 요소를 사용하면 크기가 2GB보다 크지만 개체 크기 또는 배열 크기에 대한 다른 제한은 변경되지 않는 배열을 사용할 수 있습니다.  
  
- 배열의 최대 요소 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
- 단일 차원의 최대 인덱스는 단일 바이트 구조의 바이트 배열 및 배열에 대한 2,147,483,591(0x7FFFFFC7) 및 다른 형식의 경우 2,146,435,071(0X7FFFFFFF)입니다.  
  
- 문자열 및 기타 비배열 개체의 최대 크기는 변경되지 않습니다.  
  
> [!CAUTION]
> 이 기능을 활성화하기 전에 모든 배열의 크기가 2GB보다 작다고 가정하는 안전하지 않은 코드가 응용 프로그램에 포함되어 있지 않은지 확인합니다. 예를 들어 배열을 버퍼로 사용하는 안전하지 않은 코드는 배열이 2GB를 초과하지 않는다는 가정하에 작성된 경우 버퍼 오버런에 취약할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램에 대해 이 기능을 사용하도록 설정하는 방법을 보여 주습니다.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a>다음에서 지원:

.NET 프레임워크 4.5 이상 버전

## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
