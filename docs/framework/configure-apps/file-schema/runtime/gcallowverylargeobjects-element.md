---
title: <gcAllowVeryLargeObjects> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2988b054030df23ae8ccd8840f83c239f0401321
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607258"
---
# <a name="gcallowverylargeobjects-element"></a>\<gcAllowVeryLargeObjects > 요소
64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<gcAllowVeryLargeObjects > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 64 비트 플랫폼에서 총 크기가 2GB 보다 큰 배열을 사용 되는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|총 크기가 2GB 보다 큰 배열 사용 되지 않습니다. 이 값이 기본값입니다.|  
|`true`|총 크기가 2GB 보다 큰 배열 64 비트 플랫폼에서 사용할 수 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소를 사용 하 여 응용 프로그램 구성 파일의 크기가 2GB 보다 큰 배열을 사용 하도록 설정 하지만 개체 크기 또는 배열 크기에 대 한 다른도 변경 되지 않습니다.  
  
- 배열에 있는 요소의 최대 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>합니다.  
  
- 임의의 단일 차원에 있는 최대 색인 2,147,483,591 바이트 배열 및 싱글바이트 구조의 배열에 대 한 (0x7FFFFFC7) 및 다른 유형의 2,146,435,071 (0X7FEFFFFF).  
  
- 문자열 및 기타 비 배열 개체에 대 한 최대 크기 변경 되지 않습니다.  
  
> [!CAUTION]
>  이 기능을 사용 하기 전에 응용 프로그램 크기가 2GB 보다 작은 모든 배열은 가정 하는 안전 하지 않은 코드에 포함 되지 않습니다 확인 합니다. 예를 들어, 배열 2GB를 초과 하지 것입니다 가정 하에서 작성 된 경우 버퍼 배열을 사용 하는 안전 하지 않은 코드 버퍼 오버런에 취약할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램에 대해이 기능을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
