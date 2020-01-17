---
title: JSON과 XML 간의 매핑
ms.date: 03/30/2017
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
ms.openlocfilehash: 0dbe37a07024ae70e574b92582715d2d2ef52e5c
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212079"
---
# <a name="mapping-between-json-and-xml"></a>JSON과 XML 간의 매핑
<xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>에서 생성된 판독기 및 작성기는 JSON(JavaScript Object Notation) 콘텐츠를 통해 XML API를 제공합니다. JSON은 JavaScript 개체 리터럴의 하위 집합을 사용하여 데이터를 인코딩합니다. 이 팩터리에서 생성 하는 판독기와 작성기는 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> 또는 <xref:System.ServiceModel.WebHttpBinding>를 사용 하 여 WCF (Windows Communication Foundation) 응용 프로그램에서 JSON 콘텐츠를 보내거나 받는 경우에도 사용 됩니다.

JSON 판독기는 JSON 콘텐츠를 사용하여 초기화될 때 텍스트 XML 판독기가 XML의 인스턴스에 대해 수행하는 방식과 같은 방식으로 동작합니다. JSON 작성기는 텍스트 XML 판독기에서 특정 XML 인스턴스를 생성하는 호출 시퀀스가 제공될 때 JSON 콘텐츠를 작성합니다. 고급 시나리오에서 사용할 XML의 이 인스턴스와 JSON 콘텐츠 간 매핑은 이 항목에서 설명합니다.

내부적으로 JSON은 WCF에서 처리 될 때 XML infoset으로 표시 됩니다. 일반적으로 매핑은 논리적인 표현일 뿐이므로 이러한 내부 표현에 관여할 필요가 없습니다. JSON은 실제로 메모리의 XML로 변환되거나 XML에서 JSON으로 변환되지 않습니다. 매핑이란 XML API를 사용하여 JSON 콘텐츠에 액세스하는 것을 의미합니다.

WCF에서 JSON을 사용 하는 경우 일반적인 시나리오는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> 동작이 나 적절 한 경우 <xref:System.ServiceModel.Description.WebHttpBehavior> 동작에 의해 자동으로 연결 되는 것입니다. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 JSON과 XML infoset 간 매핑을 이해하고 직접 JSON을 처리하는 역할을 합니다. XML이 다음 매핑을 따른다는 이해를 바탕으로 XML 판독기나 작성기에 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용할 수 있습니다.

고급 시나리오에서 다음 매핑에 직접 액세스해야 할 수 있습니다. 이러한 경우는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하지 않고 사용자 지정 방식으로 JSON을 직렬화 및 역직렬화하거나 JSON이 포함된 메시지의 <xref:System.ServiceModel.Channels.Message> 형식을 직접 처리할 때 발생합니다. JSON-XML 매핑은 메시지 로깅에도 사용됩니다. WCF의 메시지 로깅 기능을 사용 하는 경우 JSON 메시지는 다음 섹션에 설명 된 매핑에 따라 XML로 기록 됩니다.

매핑에 대한 개념을 명확히 하기 위해 다음 예제가 JSON 문서에 포함되어 있습니다.

```json
{"product":"pencil","price":12}
```

앞에서 언급한 판독기 중 하나를 사용하여 이 JSON 문서를 읽으려면 다음 XML 문서를 읽을 때와 동일한 <xref:System.Xml.XmlDictionaryReader> 호출 시퀀스를 사용합니다.

```xml
<root type="object">
    <product type="string">pencil</product>
    <price type="number">12</price>
</root>
```

또한이 예제의 JSON 메시지를 WCF에서 수신 하 고 기록 하는 경우 앞의 로그에 XML 조각이 표시 됩니다.

## <a name="mapping-between-json-and-the-xml-infoset"></a>JSON과 XML Infoset 간의 매핑

공식적으로는 [RFC 4627](https://www.ietf.org/rfc/rfc4627.txt) (완화 된 특정 제한 및 추가 된 특정 제한 제외)과 Xml [정보 집합](https://www.w3.org/TR/2004/REC-xml-infoset-20040204/)에 설명 된 대로 XML infoset (텍스트 xml이 아님)에 설명 된 대로 JSON 간에 매핑이 진행 됩니다. [대괄호]의 *정보 항목* 및 필드 정의는이 항목을 참조 하세요.

빈 JSON 문서는 빈 XML 문서에 매핑되고 빈 XML 문서는 빈 JSON 문서에 매핑됩니다. XML과 JSON 간 매핑에서 문서 뒤의 공백과 후행 공백은 허용 되지 않습니다.

매핑은 DII(문서 정보 항목) 또는 EII(요소 정보 항목)와 JSON 사이에서 정의됩니다. EII 또는 DII의 [document element] 속성을 루트 JSON 요소라고도 합니다. 문서 조각(여러 루트 요소가 있는 XML)은 이 매핑에서 지원되지 않습니다.

예제: 다음 문서를 참조하십시오.

```xml
<?xml version="1.0"?>
<root type="number">42</root>
```

다음 요소를 참조하십시오.

```xml
<root type="number">42</root>
```

모두 JSON에 대한 매핑이 있습니다. <`root`> 요소는 두 경우 모두 루트 JSON 요소입니다.

또한 DII의 경우 다음 사항을 고려해야 합니다.

- [children] 목록의 일부 항목이 없어야 합니다. JSON에서 매핑된 XML을 읽을 때는 이 사실에 의존하지 마십시오.

- [children] 목록에는 주석 정보 항목이 없습니다.

- [children] 목록에는 DTD 정보 항목이 없습니다.

- [Children] 목록에는 PI (개인 정보) 정보 항목이 포함 되지 않습니다 (`<?xml…>` 선언은 PI 정보 항목으로 간주 되지 않음).

- [notations] 집합이 비어 있습니다.

- [unparsed entities] 집합이 비어 있습니다.

예제: [children]에 PI 및 주석이 있기 때문에 다음 문서에는 JSON에 대한 매핑이 없습니다.

```xml
<?xml version="1.0"?>
<!--comment--><?pi?>
<root type="number">42</root>
```

루트 JSON 요소에 대한 EII에는 다음과 같은 특징이 있습니다.

- [local name]에는 값 "root"가 있습니다.

- [namespace name]에는 값이 없습니다.

- [prefix]에는 값이 없습니다.

- [children]에는 나중에 설명될 내부 요소를 나타내는 EII나 나중에 설명될 문자 정보 항목을 나타내는 CII 중 하나만 포함되거나 이 두 가지 모두 포함되지 않을 수 있습니다.

- [attributes]에는 다음과 같은 선택적 AII(특성 정보 항목)가 포함될 수 있습니다.

- 아래에 설명된 JSON 형식 특성("type"). 이 특성은 매핑된 XML에서 JSON 형식(문자열, 숫자, 부울, 개체, 배열 또는 null)을 유지하는 데 사용됩니다.

- 추가로 설명 된 대로 데이터 계약 이름 특성 ("\_\_형식")입니다. 이 특성은 JSON 형식 특성도 있고 해당 [normalized value]가 "object"인 경우에만 표시될 수 있습니다. 이 특성은 파생 형식이 serialize되고 기본 형식이 필요한 다형 사례처럼 `DataContractJsonSerializer`에서 데이터 계약 형식 정보를 유지하는 데 사용됩니다. `DataContractJsonSerializer`로 작업하지 않는 경우 대부분 이 특성이 무시됩니다.

- [범위 내 네임 스페이스]에는 infoset 사양에 의해 지정 된 `http://www.w3.org/XML/1998/namespace` "xml"의 바인딩이 포함 되어 있습니다.

- [children], [attributes] 및 [in-scope namespaces]에는 앞에서 지정한 것 이외의 항목이 없어야 하고, [namespace attributes]에는 멤버가 없어야 하지만 JSON에서 매핑된 XML을 읽을 때는 이러한 사항을 고려하지 마십시오.

예제: [namespace attributes]가 비어 있지 않기 때문에 다음 문서에는 JSON에 대한 매핑이 없습니다.

```xml
<?xml version="1.0"?>
<root xmlns:a="myattributevalue">42</root>
```

JSON 형식 특성에 대한 AII에는 다음과 같은 특징이 있습니다.

- [namespace name]에는 값이 없습니다.
- [prefix]에는 값이 없습니다.
- [local name]은 "type"입니다.
- [normalized value]는 다음 단원에서 설명하는 사용 가능한 형식 값 중 하나입니다.
- [specified]는 `true`입니다.
- [attribute type]에는 값이 없습니다.
- [references]에는 값이 없습니다.

데이터 계약 이름 특성에 대한 AII에는 다음과 같은 특징이 있습니다.

- [namespace name]에는 값이 없습니다.
- [prefix]에는 값이 없습니다.
- [local name]은 "\_\_형식" (두 개의 밑줄, "type")입니다.
- [normalized value]는 올바른 유니코드 문자열입니다. JSON에 대한 이 문자열의 매핑은 다음 단원에서 설명합니다.
- [specified]는 `true`입니다.
- [attribute type]에는 값이 없습니다.
- [references]에는 값이 없습니다.

루트 JSON 요소 내에 포함된 내부 요소 또는 기타 내부 요소에는 다음과 같은 특징이 있습니다.

- [local name]에는 추가로 설명 된 대로 값이 있을 수 있습니다.
- [namespace name], [prefix], [children], [attributes], [namespace attributes] 및 [in-scope namespaces]는 루트 JSON 요소와 동일한 규칙을 따릅니다.

루트 JSON 요소와 내부 요소에서 JSON 형식 특성은 JSON에 대한 매핑 및 가능한 [children]과 [children]의 해석을 정의합니다. 특성의 [정규화 된 값]은 대/소문자를 구분 하며 소문자 여야 하 고 공백을 포함할 수 없습니다.

|JSON 형식 특성 AII의 [정규화 된 값]|허용되는 해당 EII의 [children]|JSON에 매핑|
|---------------------------------------------------------|---------------------------------------------------|---------------------|
|`string`(또는 JSON 형식 AII 없음)<br /><br /> `string`이거나 JSON 형식 AII이 없으면 똑같이 `string`이 기본값으로 지정됩니다.<br /><br /> 따라서 `<root> string1</root>`는 JSON `string` "string1"에 매핑됩니다.|0 개 이상의 CIIs|JSON `string`(JSON RFC, 섹션 2.5). 각 `char`은 CII의 [character code]에 해당하는 문자입니다. CII가 없을 경우에는 빈 JSON `string`에 매핑됩니다.<br /><br /> 예제: 다음 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="string">42</root>`<br /><br /> JSON 조각은 "42"입니다.<br /><br /> XML과 JSON 간 매핑에서 이스케이프해야 하는 문자는 이스케이프된 문자에 매핑되고 그 외 다른 모든 문자는 이스케이프되지 않은 문자에 매핑됩니다. "/" 문자는 특수 합니다. ("\\/"로 작성 되지 않은 경우에도 이스케이프 됩니다.)<br /><br /> 예제: 다음 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> JSON 조각은 "\\" da\\/ta\\""입니다.<br /><br /> JSON과 XML 간 매핑에서 이스케이프된 문자와 이스케이프되지 않은 문자는 해당 [character code]에 올바르게 매핑됩니다.<br /><br /> 예제: JSON 조각 "\u0041BC"는 다음 XML 요소에 매핑됩니다.<br /><br /> `<root type="string">ABC</root>`<br /><br /> 문자열은 XML에 매핑되지 않는 공백 (JSON RFC의 섹션 2에 있는 ' ws ')으로 묶을 수 있습니다.<br /><br /> 예제: JSON 조각           "ABC"(첫 번째 큰따옴표 앞에 공백이 있음)는 다음 XML 요소에 매핑됩니다.<br /><br /> `<root type="string">ABC</root>`<br /><br /> XML의 모든 공백은 JSON의 공백에 매핑됩니다.<br /><br /> 예제: 다음 XML 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="string">  A BC      </root>`<br /><br /> JSON 조각은 " A BC "입니다.|
|`number`|1개 이상의 CII|JSON `number` (JSON RFC, 섹션 2.4)은 공백으로 둘러싸인 것일 수 있습니다. 숫자/공백 조합의 각 문자는 CII의 [character code]에 해당 하는 문자입니다.<br /><br /> 예제: 다음 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="number">    42</root>`<br /><br /> JSON 조각은    42입니다<br /><br /> (공백은 유지 됩니다.)|
|`boolean`|4 또는 5 CIIs (`true` 또는 `false`에 해당)는 추가 공백 CIIs이 될 수 있습니다.|문자열 "true"에 해당하는 CII 시퀀스는 리터럴 `true`에 매핑되고 문자열 "false"에 해당하는 CII 시퀀스는 리터럴 `false`에 매핑됩니다. 주변 공백은 유지 됩니다.<br /><br /> 예제: 다음 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="boolean"> false</root>`<br /><br /> JSON 조각은 `false`입니다.|
|`null`|아무 것도 사용할 수 없습니다.|리터럴 `null`입니다. JSON과 XML 간 매핑에서 `null`는 XML로 매핑되지 않는 공백 (섹션 2의 ' ws ')으로 둘러싸여 있을 수 있습니다.<br /><br /> 예제: 다음 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="null"/>`<br /><br /> 또는<br /><br /> `<root type="null"></root>`<br /><br /> :<br /><br /> 두 경우 모두 JSON 조각은 `Null`입니다.|
|`object`|0개 이상의 EII.|JSON RFC 섹션 2.2의 `begin-object`(왼쪽 중괄호)입니다. 이 값 다음에는 아래에서 설명하는 것처럼 각 EII에 대한 멤버 레코드가 옵니다. EII가 두 개 이상 있을 경우 멤버 레코드 사이에 값 구분 기호(쉼표)가 있습니다. 그 다음에 끝 개체(오른쪽 중괄호)가 옵니다.<br /><br /> 예제: 다음 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="object">`<br /><br /> `<type1 type="string">aaa\</type1>`<br /><br /> `<type2 type="string">bbb\</type2>`<br /><br /> `</root >`<br /><br /> JSON 조각은 `{"type1":"aaa","type2":"bbb"}`입니다.<br /><br /> 데이터 계약 형식 특성이 XML과 JSON 간 매핑에 표시되면 추가 멤버 레코드가 처음에 삽입됩니다. 해당 이름은 데이터 계약 형식 특성 ("\_\_형식")의 [로컬 이름] 이며, 해당 값은 특성의 [정규화 된 값]입니다. 반대로, JSON과 XML 간 매핑에서 첫 번째 멤버 레코드의 이름이 데이터 계약 형식 특성의 [local name] (즉, "\_\_형식") 이면 매핑된 XML에 해당 하는 데이터 계약 형식 특성이 있지만 해당 EII는 존재 하지 않습니다. 이 멤버 레코드는 이러한 특수한 매핑이 적용되는 JSON 개체에서 먼저 발생되어야 합니다. 이는 멤버 레코드의 순서가 중요하지 않은 일반 JSON 처리에서 출발 지점을 나타냅니다.<br /><br /> 예:<br /><br /> 다음 JSON 조각은 XML에 매핑됩니다.<br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> 다음 코드는 XML입니다.<br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> \_\_형식 AII가 있지만 EII \_\_형식이 없습니다.<br /><br /> 그러나 다음 예제에서처럼 JSON에서 순서는 반대입니다.<br /><br /> `{"name":"John","\_\_type":"Person"}`<br /><br /> 해당 XML이 표시됩니다.<br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> 즉, \__type은 특별 한 의미를 갖지 않으며 AII가 아니라 일반적인 방식으로 EII에 매핑됩니다.<br /><br /> JSON 값에 매핑될 때 AII의 [normalized value]에 대한 이스케이프/이스케이프 취소 규칙은 이 테이블의 "string" 행에 지정된 JSON 문자열에 대한 규칙과 같습니다.<br /><br /> 예:<br /><br /> `<root type="object" __type="\abc" />`<br /><br /> 앞의 예제가 다음 JSON에 매핑될 수 있습니다.<br /><br /> `{"__type":"\\abc"}`<br /><br /> XML과 JSON 간 매핑에서 첫 번째 EII의 [local name]은 "\_\_type"이 아니어야 합니다.<br /><br /> 공백 (`ws`)은 개체에 대 한 XML과 JSON 간 매핑에서 생성 되지 않으며 JSON에서 XML로의 매핑에서 무시 됩니다.<br /><br /> 예제: 다음 JSON 조각은 XML 요소에 매핑됩니다.<br /><br /> `{ "ccc" : "aaa", "ddd" :"bbb"}`<br /><br /> 다음 코드에서는 XML 요소를 보여 줍니다.<br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|
|배열입니다.|0개 이상의 EII|JSON RFC 섹션 2.3의 시작 배열(왼쪽 대괄호)입니다. 이 값 다음에는 아래에서 설명하는 것처럼 각 EII에 대한 배열 레코드가 옵니다. EII가 두 개 이상 있을 경우 배열 레코드 사이에 값 구분 기호(쉼표)가 있습니다. 그 다음에 끝 배열이 옵니다.<br /><br /> 예제: 다음 XML 요소는 JSON 조각에 매핑됩니다.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> JSON 조각이 `["aaa","bbb"]` 되었습니다.<br /><br /> 공백 (`ws`)은 배열에 대 한 XML과 JSON 간 매핑에서 생성 되지 않으며 JSON에서 XML로의 매핑에서 무시 됩니다.<br /><br /> 예: JSON 조각<br /><br />`["aaa", "bbb"]`<br /><br /> 매핑할 XML 요소입니다.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|

멤버 레코드는 다음과 같이 작동합니다.

- 내부 요소의 [local name]은 JSON RFC의 섹션 2.2에 정의된 대로 `string`의 `member` 일부에 매핑됩니다.

예제: 다음 요소는 JSON 조각에 매핑됩니다.

```xml
<root type="object"/>
<myLocalName type="string">aaa</myLocalName>
</root >
```

다음 JSON 조각이 표시됩니다.

```json
{"myLocalName":"aaa"}
```

- XML과 JSON 간 매핑에서는 JSON에서 이스케이프해야 하는 문자가 이스케이프되고 그외 다른 문자는 이스케이프되지 않습니다. "/" 문자는 이스케이프해야 하는 문자가 아니지만 이스케이프됩니다(이 문자는 JSON과 XML 간 매핑에서는 이스케이프하지 않아도 됨). 이것은 JSON에서 `DateTime` 데이터에 대한 ASP.NET AJAX 형식을 지원해야 합니다.

- JSON과 XML 간 매핑에서 필요한 경우 이스케이프되지 않은 문자를 포함하여 모든 문자가 [local name]을 생성하는 `string`을 형성합니다.

- 내부 요소 [children]은 `JSON Type Attribute`와 마찬가지로 `Root JSON Element`에 따라 섹션 2.2의 값에 매핑됩니다. 여러 수준의 EII 중첩(배열 내의 중첩 포함)이 가능합니다.

예제: 다음 요소는 JSON 조각에 매핑됩니다.

```xml
<root type="object">
    <myLocalName1 type="string">myValue1</myLocalName1>
    <myLocalName2 type="number">2</myLocalName2>
    <myLocalName3 type="object">
        <myNestedName1 type="boolean">true</myNestedName1>
        <myNestedName2 type="null"/>
    </myLocalName3>
</root >
```

다음 JSON 조각은 매핑할 JSON 조각입니다.

```json
{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}
```

> [!NOTE]
> 앞의 매핑에는 XML 인코딩 단계가 없습니다. 따라서 WCF는 키 이름의 모든 문자가 XML 요소 이름의 유효한 문자인 JSON 문서만 지원 합니다. 예를 들어, <는 XML 요소의 올바른 이름이 아니므로 JSON 문서 {"<": "a"}은 (는) 지원 되지 않습니다.

반대 상황(XML에서 유효하지만 JSON에서는 유효하지 않은 문자)의 경우 앞의 매핑에 JSON 이스케이프/이스케이프 취소 단계가 포함되므로 문제가 발생하지 않습니다.

배열 레코드는 다음과 같이 작동합니다.

- 내부 요소의 [local name]은 "item"입니다.

- 내부 요소의 [children]은 루트 JSON 요소에 대해 매핑되는 것과 마찬가지로 JSON 형식 특성에 따라 섹션 2.3의 값에 매핑됩니다. 여러 수준의 EII 중첩(개체 내의 중첩 포함)이 가능합니다.

예제: 다음 요소는 JSON 조각에 매핑됩니다.

```xml
<root type="array"/>
    <item type="string">myValue1</item>
    <item type="number">2</item>
    <item type="array">
    <item type="boolean">true</item>
    <item type="null"/></item>
</root >
```

JSON 조각은 다음과 같습니다.

```json
["myValue1",2,[true,null]]
```

## <a name="see-also"></a>참조

- <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>
- [독립 실행형 JSON Serialization](stand-alone-json-serialization.md)
