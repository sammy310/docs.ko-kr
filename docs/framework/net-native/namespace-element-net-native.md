---
title: <Namespace>요소(.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
ms.openlocfilehash: 06d88a7b0f95c7c1dbe98818b847c92e08a57a19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180962"
---
# <a name="namespace-element-net-native"></a>\<네임스페이스> 요소(.NET 네이티브)
지정된 네임스페이스의 모든 형식에 런타임 리플렉션 정책을 적용합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<Namespace Name="namespace_name"
           Activate="policy_type"
           Browse="policy_type"  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
           DataContractSerializer="policy_setting"  
           DataContractJsonSerializer="policy_setting"  
           XmlSerializer="policy_setting"  
           MarshalObject="policy_setting"  
           MarshalDelegate="policy_setting"  
           MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|특성 유형|Description|  
|---------------|--------------------|-----------------|  
|`Name`|일반|필수 특성입니다. 네임스페이스의 이름을 지정합니다.|  
|`Activate`|반사|선택적 특성입니다. 인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.|  
|`Browse`|반사|선택적 특성입니다. 프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.|  
|`Dynamic`|반사|선택적 특성입니다. 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.|  
|`Serialize`|직렬화|선택적 특성입니다. Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.|  
|`DataContractSerializer`|직렬화|선택적 특성입니다. <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.|  
|`DataContractJsonSerializer`|직렬화|선택적 특성입니다. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.|  
|`XmlSerializer`|직렬화|선택적 특성입니다. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.|  
|`MarshalObject`|Interop|선택적 특성입니다. Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalDelegate`|Interop|선택적 특성입니다. 네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.|  
|`MarshalStructure`|Interop|선택적 특성입니다. 구조체를 네이티브 코드로 마샬링하는 정책을 제어합니다.|  
  
## <a name="name-attribute"></a>Name 특성  
  
|값|Description|  
|-----------|-----------------|  
|*namespace_name*|네임스페이스 이름입니다. \<네임스페이스> 요소가 [ \<응용 프로그램>, ](application-element-net-native.md) [ \<라이브러리>](library-element-net-native.md)또는 [ \<어셈블리>](assembly-element-net-native.md) 요소의 자식인 경우 *namespace_name* 정규화된 네임스페이스 이름이어야 합니다. \<Namespace> 요소가 다른 \<Namespace> 요소의 자식이면 *namespace_name*은 상대 네임스페이스 이름이어야 합니다.|  
  
## <a name="all-other-attributes"></a>기타 모든 특성  
  
|값|Description|  
|-----------|-----------------|  
|*policy_setting*|네임스페이스의 모든 형식에 대해 이 정책 형식에 적용할 설정입니다. 가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다. 자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`<Namespace>`|부모 네임스페이스의 모든 형식에 런타임 리플렉션 정책을 적용합니다.|  
|[\<유형>](type-element-net-native.md)|형식에 리플렉션 정책을 적용합니다.|  
|[\<타이핑>](typeinstantiation-element-net-native.md)|생성된 제네릭 형식에 리플렉션 정책을 적용합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<응용 프로그램>](application-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다. [ \<응용 프로그램>](application-element-net-native.md) 요소에는 [ \<어셈블리>](assembly-element-net-native.md) 요소가 0개, 하나 이상 있을 수 있습니다.|  
|[\<어셈블리>](assembly-element-net-native.md)|지정된 어셈블리의 모든 형식에 런타임 리플렉션 정책을 적용합니다.|  
|[\<도서관>](library-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다. [ \<라이브러리>](library-element-net-native.md) 요소에는 [ \<어셈블리 요소가](assembly-element-net-native.md) 0개 또는 하나>수 있습니다.|  
|`<Namespace>`|부모 네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.|  
  
## <a name="remarks"></a>설명  
 `Activate`, `Browse`, `Dynamic` 및 `Serialize` 특성은 모두 선택적 항목입니다. 아무 특성도 없으면 `<Namespace>` 요소는 자식 요소의 컨테이너로만 사용됩니다. 특성이 있으면 `<Namespace>` 요소가 지정된 네임스페이스의 모든 형식에 대해 런타임 리플렉션 정책을 적용합니다.  
  
 어셈블리>요소의 자식인 `<Namespace>` 경우 요소는 [ \<어셈블리>](assembly-element-net-native.md) 요소에 의해 정의된 런타임 반사 정책을 재정의합니다. [ \<](assembly-element-net-native.md)  
  
## <a name="see-also"></a>참고 항목

- [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)
- [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md)
- [런타임 지시문 요소](runtime-directive-elements.md)
