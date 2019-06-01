---
title: <shadowCopyVerifyByTimestamp> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1815da141beb3dd1022fe1a74f872aa70b4ded43
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456351"
---
# <a name="shadowcopyverifybytimestamp-element"></a>\<shadowCopyVerifyByTimestamp> 요소
섀도 복사에서 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에 도입된 기본 시작 동작을 사용하는지 아니면 이전 .NET Framework 버전의 시작 동작으로 되돌아가는지를 지정합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<shadowCopyVerifyByTimestamp> 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> 어셈블리를 섀도 복사 하기 전에 어셈블리를 업데이트 되었는지 여부를 확인 하려면 시작 시 섀도 복사를 사용 하는 응용 프로그램 도메인 어셈블리 타임 스탬프를 비교 하는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|true|시작 시 섀도 복사 디렉터리에 마지막으로 복사 된 이후 업데이트 된 어셈블리만 복사 합니다. 이것은.NET Framework 4에 대 한 기본값입니다.|  
|False|시작 시 모든 파일을 복사 하는 것 이었습니다는 이전 버전의.NET Framework의 시작 동작으로 되돌아갑니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 4 부터는 어셈블리는 해당 타임 스탬프가 섀도 복사 디렉터리에 마지막으로 복사 된 이후 변경 된 것을 나타내는 경우에 섀도 복사 됩니다. 에 설명 된 대로 섀도 복사를 사용 하는 대부분의 응용 프로그램 시작 시간이 향상 됩니다 [어셈블리 섀도 복사](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)합니다. 어셈블리 업데이트의 높은 비율과 빈도를 갖는 응용 프로그램은 이 동작 변경이 도움이 되지 않을 수 있습니다. 이 경우 이 요소를 사용하여 이전 버전의 .NET Framework의 동작을 복원할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는.NET Framework 4에서 복사 하는 그림자의 기본 시작 동작을 사용 하지 않도록 설정 하 고 이전 버전의.NET Framework의 시작 동작으로 되돌리려면 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [어셈블리 섀도 복사](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
