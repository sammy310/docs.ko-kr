---
title: XML 파일 처리 - C# 프로그래밍 가이드
description: C# 프로그래밍에서 XML 파일을 처리하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: 5ce0f311ccc16b4eca8d499578c217d93cc93165
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477868"
---
# <a name="process-the-xml-file-c-programming-guide"></a>XML 파일 처리(C# 프로그래밍 가이드)

컴파일러는 문서 생성을 위해 태그가 지정되는 코드의 각 구문에 대해 ID 문자열을 생성합니다. 코드에 태그를 지정하는 방법에 대한 자세한 내용은 [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)를 참조하세요. ID 문자열은 구문을 고유하게 식별합니다. XML 파일을 처리하는 프로그램은 ID 문자열을 사용하여 문서가 적용되는 해당 .NET 메타데이터 또는 리플렉션 항목을 식별할 수 있습니다.

## <a name="id-strings"></a>ID 문자열

XML 파일은 코드의 계층적 표현이 아닙니다. 각 요소에 대해 생성된 ID가 포함된 단순 목록입니다.

컴파일러는 ID 문자열을 생성할 때 다음 규칙을 관찰합니다.

- 문자열에 공백이 없음.

- 문자열의 첫 부분이 뒤에 콜론이 붙은 한 글자를 사용해 멤버의 종류를 식별합니다. 사용되는 멤버 유형은 다음과 같습니다.

    |문자|멤버 형식|참고|
    |---------------|-----------------|-|
    |N|namespace|네임스페이스에 문서 주석을 추가할 수는 없지만 지원되는 경우 문서 주석에 대한 cref 참조를 만들 수는 있습니다.|
    |T|type|클래스, 인터페이스, 구조체, 열거형 또는 대리자일 수 있습니다.|
    |F|필드(field)|
    |P|속성(property)|인덱서 또는 기타 인덱싱된 속성을 포함합니다.|
    |M|메서드|생성자 및 연산자와 같은 특수 메서드를 포함합니다.|
    |E|event|
    |!|오류 문자열|문자열의 나머지 부분은 오류에 대한 정보를 제공합니다. C# 컴파일러는 확인할 수 없는 링크에 대해 오류 정보를 생성합니다.|

- 문자열의 두 번째 부분은 네임스페이스의 루트부터 시작되는 항목의 정규화된 이름입니다. 항목의 이름과 바깥쪽 형식 및 네임스페이스는 마침표로 구분됩니다. 항목 자체의 이름에 마침표가 있으면 이러한 요소를 구분하는 마침표가 해시 기호('#')로 바뀝니다. 항목 이름에는 해시 기호가 직접적으로 포함되지 않는다고 가정합니다. 예를 들어 String 생성자의 정규화된 이름은 “System.String.#ctor”입니다.

- 속성 및 메서드의 경우 괄호로 묶은 매개 변수 목록이 뒤에 나옵니다. 매개 변수가 없으면 괄호도 없습니다. 매개 변수는 쉼표로 구분됩니다. 각 매개 변수의 인코딩은 .NET 시그니처에서 매개 변수가 인코딩되는 방식을 그대로 따릅니다.

  - 기본 형식. 일반 형식(ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE)은 해당 형식의 정규화된 이름으로 표시됩니다.

  - 내장 형식(예: ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF 및 ELEMENT_TYPE_VOID)은 해당 전체 형식의 정규화된 이름으로 표시됩니다. 예를 들면 System.Int32 또는 System.TypedReference와 같습니다.

  - ELEMENT_TYPE_PTR은 수정된 형식 뒤에 ‘\*’로 표시됩니다.

  - ELEMENT_TYPE_BYREF는 수정된 형식 뒤에 ‘\@’으로 표시됩니다.

  - ELEMENT_TYPE_PINNED는 수정된 형식 뒤에 '^'로 표시됩니다. C# 컴파일러에서는 이 인수가 생성되지 않습니다.

  - ELEMENT_TYPE_CMOD_REQ는 수정된 형식 뒤에 '&#124;' 및 한정자 클래스의 정규화된 이름으로 표시됩니다. C# 컴파일러에서는 이 인수가 생성되지 않습니다.

  - ELEMENT_TYPE_CMOD_OPT는 수정된 형식 뒤에 '!' 및 한정자 클래스의 정규화된 이름으로 표시됩니다.

  - ELEMENT_TYPE_SZARRAY는 배열의 요소 형식 뒤에 "[]"로 표시됩니다.

  - ELEMENT_TYPE_GENERICARRAY는 배열의 요소 형식 뒤에 "[?]"로 표시됩니다. C# 컴파일러에서는 이 인수가 생성되지 않습니다.

  - ELEMENT_TYPE_ARRAY는 [*lowerbound*:`size`,*lowerbound*:`size`]로 표시됩니다. 여기서 쉼표 수는 순위 - 1에 해당하는 값이고, 각 차원의 하한과 크기(확인된 경우)는 10진수로 표시됩니다. 하한이나 크기가 지정되지 않은 경우에는 생략됩니다. 특정 차원의 하한과 크기를 생략하면 ':'도 생략됩니다. 예를 들어 하한이 1이고 크기가 지정되지 않은 2차원 배열은 [1:,1:]로 표시됩니다.

  - ELEMENT_TYPE_FNPTR은 "=FUNC:`type`(*signature*)"로 표시됩니다. 여기서 `type`은 반환 형식이고 *signature* 는 메서드의 인수입니다. 인수가 없으면 괄호는 생략됩니다. C# 컴파일러에서는 이 인수가 생성되지 않습니다.

  다음 시그니처 구성 요소는 오버로드된 메서드를 구분하는 데 사용되지 않으므로 표시되지 않습니다.

  - 호출 규칙

  - 반환 형식

  - ELEMENT_TYPE_SENTINEL

- 변환 연산자(`op_Implicit` 및 `op_Explicit`)에 한해 메서드의 반환 값은 뒤에 반환 형식이 붙은 ‘~’로 인코딩됩니다.

- 제네릭 형식의 경우에는 형식 이름 뒤에 억음 악센트 기호와 제네릭 형식 매개 변수의 수를 나타내는 숫자가 차례로 붙습니다. 예를 들어:

     ``<member name="T:SampleClass`2">``는 `public class SampleClass<T, U>`로 정의된 형식의 태그입니다.

     제네릭 형식을 매개 변수로 사용하는 메서드의 경우 제네릭 형식 매개 변수는 \`0,\`1과 같이 앞에 억음 악센트 기호가 붙은 숫자로 지정됩니다. 각 숫자는 해당 형식의 제네릭 매개 변수에 대한 0부터 시작되는 배열 표기법을 나타냅니다.

## <a name="examples"></a>예

다음 예제에서는 클래스와 해당 멤버의 ID 문자열이 생성되는 방식을 보여 줍니다.

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [**DocumentationFile**(C# 컴파일러 옵션)](../../language-reference/compiler-options/output.md#documentationfile)
- [XML 문서 주석](./index.md)
