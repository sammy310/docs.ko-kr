---
title: 형식 공급자
description: F# 형식 공급자는 사용자 프로그램에서 사용할 형식, 속성 및 메서드를 제공하는 구성 요소인 이유를 알아봅니다.
ms.date: 04/02/2018
ms.openlocfilehash: f01e207407b2282005d5722bed798df1d49d3ef6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468228"
---
# <a name="type-providers"></a>형식 공급자

F# 형식 공급자는 사용자 프로그램에서 사용할 형식, 속성 및 메서드를 제공하는 구성 요소입니다. 형식 공급자는 F# 컴파일러에 의해 생성되고 외부 데이터 원본을 기반으로 하는 **제공된 형식** 을 생성합니다.

예를 들어 SQL용 F# 형식 공급자는 관계형 데이터베이스의 테이블과 열을 나타내는 형식을 생성할 수 있습니다. 실제로 이는 [SQLProvider](https://fsprojects.github.io/SQLProvider/) 형식 공급자에서 수행되는 작업입니다.

제공된 형식은 형식 공급자의 입력 매개 변수에 따라 달라집니다. 입력은 샘플 데이터 원본(예: JSON 스키마 파일), 외부 서비스를 직접 가리키는 URL 또는 데이터 원본에 대한 연결 문자열일 수 있습니다. 형식 공급자는 형식의 그룹이 필요할 때만 확장되도록 할 수도 있습니다. 즉, 프로그램에서 형식을 실제로 참조하는 경우 확장됩니다. 따라서 강력한 형식으로 온라인 데이터 시장과 같은 대규모 정보 공간의 직접적인 주문형 통합을 허용합니다.

## <a name="generative-and-erased-type-providers"></a>생성 및 지워진 형식 공급자

형식 공급자는 다음과 같은 두 가지 형식으로 제공됩니다. 생성 및 지워진 형식 공급자.

생성 형식 공급자는 생성되는 어셈블리에 .NET 형식으로 기록될 수 있는 형식을 생성합니다. 따라서 다른 어셈블리의 코드에서 생성 형식 공급자를 사용할 수 있습니다. 즉, 데이터 원본의 형식화된 표현은 일반적으로 .NET 형식으로 나타낼 수 있는 것이어야 합니다.

형식 공급자를 지우면 생성된 어셈블리 또는 프로젝트에서만 사용될 수 있는 형식이 생성됩니다. 형식은 사용 후 삭제됩니다. 즉, 형식이 어셈블리에 기록되지 않고 다른 어셈블리의 코드에서 사용할 수 없습니다. ‘지연된’ 멤버를 포함하여 잠재적으로 무한한 정보 공간에서 제공된 형식을 사용할 수 있습니다. 형식이 크고 상호 연결된 데이터 원본의 작은 하위 집합을 사용하는 데 유용합니다.

## <a name="commonly-used-type-providers"></a>일반적으로 사용되는 형식 공급자

다음과 같이 널리 사용되는 라이브러리에는 다양한 용도의 형식 공급자가 포함되어 있습니다.

- FSharp.Data에는 JSON, XML, CSV, HTML 문서 형식 및 리소스에 대한 형식 공급자가 포함되어 있습니다.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/)는 이러한 데이터 원본에 대한 개체 매핑 및 F# LINQ 쿼리를 통해 관계 데이터베이스에 강력한 형식으로 액세스합니다.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/)에는 F#에서 컴파일 시간에 확인하여 포함되는 T-SQL에 대한 형식 공급자가 있습니다.
- [Azure Storage 형식 공급자](https://fsprojects.github.io/AzureStorageTypeProvider/)는 Azure Blob, 테이블 및 큐에 대한 형식을 제공하므로, 프로그램 전체에서 리소스 이름을 문자열로 지정하지 않고도 이러한 리소스에 액세스할 수 있습니다.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html)에는 URL로 지정된 GraphQL 서버를 기반으로 형식을 제공하는 **GraphQLProvider** 가 포함되어 있습니다.

필요한 경우 [고유한 사용자 지정 형식 공급자를 만들거나](creating-a-type-provider.md) 다른 사람이 만든 형식 공급자를 참조할 수 있습니다. 예를 들어 조직에 규모가 크고 점점 더 수가 증가하는 명명된 데이터 집합(각각 자체적으로 안정적인 데이터 스키마 포함)을 제공하는 데이터 서비스가 있다고 가정합니다. 강력한 방식으로 스키마를 읽고 프로그래머에 설정된 사용할 수 있는 최신 데이터 집합을 제공하는 형식 공급자를 만들도록 선택할 수 있습니다.

## <a name="see-also"></a>참조

- [자습서: 형식 공급자 만들기](creating-a-type-provider.md)
- [F# 언어 참조](../../language-reference/index.md)
