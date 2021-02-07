---
description: '자세히 알아보기: <Directives> 요소 (.NET 네이티브)'
title: <Directives> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 7aa3bf3718f32d55ba8189c65705868c6fb399ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662912"
---
# <a name="directives-element-net-native"></a>\<Directives> 요소 (.NET 네이티브)

.NET 네이티브에 대 한 모든 런타임 지시문 파일의 루트 요소입니다.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a>구문  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|`xmlns`|XML 네임스페이스입니다. 해당 값은 항상 `http://schemas.microsoft.com/netfx/2013/01/metadata` 입니다.|  
  
## <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버의 컨테이너로 사용됩니다.|  
|[\<Library>](library-element-net-native.md)|런타임에 자식 형식 및 형식 멤버에 메타데이터가 필요한 어셈블리를 정의합니다.|  
  
## <a name="remarks"></a>설명  

 각 런타임 지시문 파일은 `<Directives>` 요소를 하나만 포함할 수 있습니다.  
  
 `<Directives>`요소는 0 개 또는 한 개의 [\<Application>](application-element-net-native.md) 요소와 0 개 이상의 요소를 포함할 수 있습니다 [\<Library>](library-element-net-native.md) .  
  
## <a name="see-also"></a>참고 항목

- [런타임 지시문(rd.xml) 구성 파일 참조](runtime-directives-rd-xml-configuration-file-reference.md)
- [런타임 지시문 요소](runtime-directive-elements.md)
