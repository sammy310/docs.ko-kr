---
title: <Type>요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
ms.openlocfilehash: 4e88b49b82513079ddcf6f0bafe02d44235a406a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73091849"
---
# <a name="type-element-net-native"></a>\<Type>요소 (.NET 네이티브)

클래스 또는 구조체와 같은 특정 형식에 런타임 정책을 적용합니다.

## <a name="syntax"></a>구문

```xml
<Type Name="type_name"
      Activate="policy_type"
      Browse="policy_type"
      Dynamic="policy_type"
      Serialize="policy_type"
      DataContractSerializer="policy_setting"
      DataContractJsonSerializer="policy_setting"
      XmlSerializer="policy_setting"
      MarshalObject="policy_setting"
      MarshalDelegate="policy_setting"
      MarshalStructure="policy_setting" />
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|attribute|특성 유형|Description|
|---------------|--------------------|-----------------|
|`Name`|일반|필수 특성입니다. 형식 이름을 지정합니다.|
|`Activate`|반사|선택적 특성입니다. 인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.|
|`Browse`|반사|선택적 특성입니다. 프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.|
|`Dynamic`|반사|선택적 특성입니다. 동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.|
|`Serialize`|Serialization|선택적 특성입니다. Newtonsoft JSON 직렬 변환기 등의 라이브러리를 통해 형식 인스턴스를 직렬화 및 역직렬화할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.|
|`DataContractSerializer`|Serialization|선택적 특성입니다. <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.|
|`DataContractJsonSerializer`|Serialization|선택적 특성입니다. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.|
|`XmlSerializer`|Serialization|선택적 특성입니다. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.|
|`MarshalObject`|Interop|선택적 특성입니다. Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.|
|`MarshalDelegate`|Interop|선택적 특성입니다. 네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.|
|`MarshalStructure`|Interop|선택적 특성입니다. 값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.|

## <a name="name-attribute"></a>Name 특성

|값|Description|
|-----------|-----------------|
|*type_name*|형식 이름입니다. 이 `<Type>` 요소가 [\<Namespace>](namespace-element-net-native.md) 요소 또는 다른 요소의 자식인 경우 `<Type>` 네임 스페이스 없이 형식의 이름을 포함할 수 *type_name* . 그러지 않으면 *type_name*은 정규화된 형식 이름을 포함해야 합니다.|

## <a name="all-other-attributes"></a>기타 모든 특성

|값|Description|
|-----------|-----------------|
|*policy_setting*|이 정책 형식에 적용할 설정입니다. 가능한 값은 `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다. 자세한 내용은 [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)을 참조하세요.|

### <a name="child-elements"></a>자식 요소

|요소|Description|
|-------------|-----------------|
|[\<AttributeImplies>](attributeimplies-element-net-native.md)|포함 형식이 특성이면 해당 특성이 적용되는 코드 요소에 대해 런타임 정책을 정의합니다.|
|[\<Event>](event-element-net-native.md)|이 형식에 속하는 이벤트에 리플렉션 정책을 적용합니다.|
|[\<Field>](field-element-net-native.md)|이 형식에 속하는 필드에 리플렉션 정책을 적용합니다.|
|[\<GenericParameter>](genericparameter-element-net-native.md)|제네릭 형식의 매개 변수 형식에 정책을 적용합니다.|
|[\<ImpliesType>](impliestype-element-net-native.md)|포함 `<Type>` 요소가 나타내는 형식에 정책이 적용된 경우 형식에 해당 정책을 적용합니다.|
|[\<Method>](method-element-net-native.md)|이 형식에 속하는 메서드에 리플렉션 정책을 적용합니다.|
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|이 형식에 속하는 생성된 제네릭 메서드에 리플렉션 정책을 적용합니다.|
|[\<Property>](property-element-net-native.md)|이 형식에 속하는 속성에 리플렉션 정책을 적용합니다.|
|[\<Subtypes>](subtypes-element-net-native.md)|포함 형식에서 상속된 모든 클래스에 런타임 정책을 적용합니다.|
|`<Type>`|중첩된 형식에 리플렉션 정책을 적용합니다.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|생성된 제네릭 형식에 리플렉션 정책을 적용합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|Description|
|-------------|-----------------|
|[\<Application>](application-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버에 대한 컨테이너로 사용됩니다.|
|[\<Assembly>](assembly-element-net-native.md)|지정된 어셈블리의 모든 형식에 리플렉션 정책을 적용합니다.|
|[\<Library>](library-element-net-native.md)|런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.|
|[\<Namespace>](namespace-element-net-native.md)|네임스페이스의 모든 형식에 리플렉션 정책을 적용합니다.|
|`<Type>`|형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.|

## <a name="remarks"></a>설명

리플렉션, serialization 및 interop 특성은 모두 선택 사항입니다. 이러한 특성이 없으면 `<Type>` 요소는 하위 형식이 개별 멤버의 정책을 정의하는 컨테이너로 사용됩니다.

`<Type>`요소가 [\<Assembly>](assembly-element-net-native.md) ,, 또는 요소의 자식인 경우 [\<Namespace>](namespace-element-net-native.md) `<Type>` [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 부모 요소에 의해 정의 된 정책 설정을 재정의 합니다.

제네릭 형식의 `<Type>` 요소는 자체 정책이 없는 모든 인스턴스화에 해당 정책을 적용합니다. 생성 된 제네릭 형식의 정책은 요소에 의해 정의 됩니다 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .

제네릭 형식의 경우 해당 이름은 억음 악센트 기호(\`)와 제네릭 매개 변수의 수가 차례로 붙는 형식으로 데코레이팅됩니다. 예를 들어 `Name` 클래스 `<Type>` 요소의 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 특성은 ``Name="System.Collections.Generic.List`1"``로 표시됩니다.

## <a name="example"></a>예제

다음 예제에서는 리플렉션을 사용하여 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 클래스의 필드, 속성 및 메서드에 대한 정보를 표시합니다. 예제의 변수는 `b` <xref:Windows.UI.Xaml.Controls.TextBlock> 컨트롤입니다. 이 예제에서는 형식 정보만 검색하므로 메타데이터 사용 가능 여부는 `Browse` 정책 설정에 의해 제어됩니다.

 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]

 클래스의 메타 데이터는 <xref:System.Collections.Generic.List%601> .NET 네이티브 도구 체인에 의해 자동으로 포함 되지 않기 때문에이 예제에서는 런타임에 요청 된 멤버 정보를 표시 하지 못합니다. 필요한 메타데이터를 제공하려면 다음 `<Type>` 요소를 런타임 지시문 파일에 추가합니다. 여기서는 부모 [<Namespace\>](namespace-element-net-native.md) 요소를 제공했으므로 `<Type>` 요소에 정규화된 형식 이름을 제공하지 않아도 됩니다.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="*Application*" Dynamic="Required All" />
      <Namespace Name ="System.Collections.Generic" >
        <Type Name="List`1" Browse="Required All" />
     </Namespace>
   </Application>
</Directives>
```

## <a name="example"></a>예제
 다음 예제에서는 리플렉션을 사용하여 <xref:System.Reflection.PropertyInfo> 속성을 나타내는 <xref:System.String.Chars%2A?displayProperty=nameWithType> 개체를 검색합니다. 그런 다음 <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드를 사용하여 문자열에서 7번째 문자의 값을 검색하고 문자열의 모든 문자를 표시합니다. 예제의 변수는 `b` <xref:Windows.UI.Xaml.Controls.TextBlock> 컨트롤입니다.

 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]

 개체에 대 한 메타 데이터 <xref:System.String> 를 사용할 수 없기 때문에 메서드를 호출 하면 <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> <xref:System.NullReferenceException> 런타임에 .NET 네이티브 도구 체인을 사용 하 여 컴파일할 때 예외가 throw 됩니다. 예외를 방지하고 필요한 메타데이터를 제공하려면 다음 `<Type>` 요소를 런타임 지시문 파일에 추가합니다.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Assembly Name="*Application*" Dynamic="Required All" />
    <Type Name="System.String" Dynamic="Required Public"/> -->
  </Application>
</Directives>
```

## <a name="see-also"></a>참고 항목

- [런타임 지시문(rd.xml) 구성 파일 참조](runtime-directives-rd-xml-configuration-file-reference.md)
- [런타임 지시문 요소](runtime-directive-elements.md)
- [런타임 지시문 정책 설정](runtime-directive-policy-settings.md)
