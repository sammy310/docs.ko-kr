---
title: <Crst_DisableSpinWait> 요소
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 45052d99bb297ac39d058fa405fe57a7c991f738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151352"
---
# <a name="crst_disablespinwait-element"></a>\<Crst_DisableSpinWait> 요소

경합이 있을 때 임계 영역에 대해 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|**사용**|경합이 있을 때 임계 영역에 대 한 회전 대기를 사용 하지 않도록 설정할지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|Value|설명|  
|-----------|-----------------|  
|1|임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다.|  
|0|임계 영역을 가져올 수 없을 때 스핀 대기를 사용 하지 않도록 설정 합니다. 이것은 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|다양 한 런타임 구성 설정에 대 한 정보를 포함 합니다.|  
  
## <a name="example"></a>예제  

다음 예제에서는 경합이 있을 때 임계 영역에서 스핀 대기를 사용 하지 않도록 설정 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
