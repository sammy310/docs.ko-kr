---
title: <legacyCorruptedStateExceptionsPolicy> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78b670d8b23b5ecf274432d3758d07dae34dcfcf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607164"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy > 요소
공용 언어 런타임에서 액세스 위반 및 기타 손상 된 상태 예외를 catch 하는 관리 되는 코드를 허용 하는지 여부를 지정 합니다.  
  
 \<configuration>  
\<runtime>  
\<legacyCorruptedStateExceptionsPolicy>  
  
## <a name="syntax"></a>구문  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 응용 프로그램은 catch 지정 액세스 위반과 같은 손상 된 상태 예외입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|응용 프로그램은 catch 하지 않습니다 액세스 위반과 같은 손상 된 상태 예외입니다. 이 값이 기본값입니다.|  
|`true`|응용 프로그램을 포착 하는 액세스 위반과 같은 손상 된 상태 예외입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 3.5 및 이전 버전에서 공용 언어 런타임 손상 된 프로세스 상태에서 발생 한 예외를 catch 하는 관리 되는 코드를 허용 합니다. 액세스 위반이 발생은 이러한 유형의 예외는 예제입니다.  
  
 로 시작 합니다 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]관리 되는 코드에는 더 이상 이러한 유형의 예외 catch `catch` 블록입니다. 그러나 이러한 변경 내용을 재정의 하 고 두 가지 방법으로 손상 된 상태 예외 처리를 유지 관리할 수 있습니다.  
  
- 설정 된 `<legacyCorruptedStateExceptionsPolicy>` 요소의 `enabled` 특성을 `true`입니다. 이 구성 설정은 프로세스 전체에 적용된 되며 모든 메서드에 영향을 줍니다.  
  
 또는  
  
- 적용 된 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> 특성을 메서드에 예외를 포함 하는 `catch` 블록입니다.  
  
 이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램이 이전 동작으로 되돌려야 함을 지정 하는 방법의 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 모든 손상 된 상태 예외 오류를 catch 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
