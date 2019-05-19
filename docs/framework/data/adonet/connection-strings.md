---
title: ADO.NET의 연결 문자열
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 3b7cb0ab061da8364a9fecc3868ba9aaf7501577
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881155"
---
# <a name="connection-strings-in-adonet"></a>ADO.NET의 연결 문자열

연결 문자열에는 데이터 공급자에서 데이터 소스에 매개 변수로 전달되는 초기화 정보가 있습니다. 값으로 연결 문자열을 수신 하는 데이터 공급자는 <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> 속성입니다. 공급자 연결 문자열을 구문 분석 및 구문이 올바르고 키워드를 지원 하는지 확인 합니다. 그런 다음 <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> 메서드는 데이터 원본에 구문 분석 된 연결 매개 변수를 전달 합니다. 데이터 원본 추가 유효성 검사를 수행 하 고 연결을 설정 합니다.

## <a name="connection-string-syntax"></a>연결 문자열 구문

연결 문자열은 키/값 매개 변수 쌍의 세미콜론으로 구분 된 목록:

```
keyword1=value; keyword2=value;
```

키워드는 대/소문자 구분 하지 않습니다. 그러나 값을 않을 대/소문자 구분, 데이터 원본에 따라 합니다. 키워드와 값이 포함 될 수 있습니다 [공백 문자](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)합니다. 선행 및 후행 공백을 키워드에서 무시 되 고 따옴표가 값입니다.

값을 세미콜론을 포함 하는 경우 [유니코드 제어 문자](https://en.wikipedia.org/wiki/Unicode_control_characters), 또는 단일 또는 이중 따옴표로 묶어야 합니다 선행 또는 후행 공백을 삭제 합니다. 예를 들어:

```
Keyword=" whitespace  ";
Keyword='special;character';
```

바깥쪽 문자 값이 포함 될 수 있습니다. 따라서 큰따옴표에만 그 반대로 작은따옴표를 포함 하는 값을 묶을 수 있습니다.

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

등호 기호 뿐만 아니라 자체에 따옴표 필요 하지 않습니다, 이스케이프 다음 연결 문자열을 유효한 되므로:

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

두 번째 예의 값은 각 값은 다음 세미콜론 이나 문자열의 끝까지 내용은 이후 `a=b=c`, 최종 세미콜론 선택 사항입니다.

모든 연결 문자열에는 위에서 설명한 동일한 기본 구문을 공유 합니다. 그러나 공급자에 따라 달라 집니다 및와 같은 초기 Api 에서부터 수 년에 걸쳐 발전해 인식 된 키워드 집합 *ODBC*합니다. 합니다 *.NET Framework* 에 대 한 데이터 공급자 *SQL Server* (`SqlClient`) 이전 Api에서 여러 키워드를 지원 하지만 일반적으로 더 유연 하 고 다양 한 일반적인 연결 문자열에 대 한 동의어를 허용 키워드입니다.

실수를 입력 하면 오류가 발생할 수 있습니다. 예를 들어 `Integrated Security=true` 유효 하지만 `IntegratedSecurity=true` 오류가 발생 합니다.

런타임에 유효성이 검사 되지 않은 사용자 입력에서 수동으로 구성 된 연결 문자열은 문자열 삽입 공격에 취약 및 데이터 소스에서 보안을 위협할 합니다. 이러한 문제를 해결 하기 위해 *ADO.NET* 2.0에서는 [연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md) 마다 *.NET Framework* 데이터 공급자입니다. 이러한 연결 문자열 작성기 매개 변수를 강력한 형식의 속성을 노출 하 고 연결 문자열을 데이터 원본에 전송 되기 전에 유효성을 검사할 수 있도록 합니다.

## <a name="in-this-section"></a>섹션 내용

[연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md)\
`ConnectionStringBuilder` 클래스를 사용하여 런타임에 유효한 연결 문자열을 구성하는 방법을 보여 줍니다.

[연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\
구성 파일에서 연결 문자열을 저장하고 검색하는 방법을 보여 줍니다.

[연결 문자열 구문](../../../../docs/framework/data/adonet/connection-string-syntax.md)\
`SqlClient`, `OracleClient`, `OleDb` 및 `Odbc`에 대한 공급자별 연결 문자열을 구성하는 방법을 설명합니다.

[연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)\
데이터 소스 연결에 사용되는 정보를 보호하는 기법을 보여 줍니다.

## <a name="see-also"></a>참고자료

- [데이터 소스에 연결](/cpp/data/odbc/connecting-to-a-data-source)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
