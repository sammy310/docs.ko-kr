---
title: 형식 공급자
description: F# 형식 공급자가 프로그램에서 사용할 형식, 속성 및 메서드를 제공 하는 구성 요소에 대해 알아봅니다.
ms.date: 04/02/2018
ms.openlocfilehash: 7fa0ff6b5f2b0bc978df2988f22b2042acc22320
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552911"
---
# <a name="type-providers"></a>형식 공급자

F# 형식 공급자는 사용자 프로그램에서 사용할 형식, 속성 및 메서드를 제공하는 구성 요소입니다. 형식 공급자는 컴파일러에 F# 의해 생성 되 고 외부 데이터 원본을 기반으로 하는 제공 된 **형식**으로 알려진 항목을 생성 합니다.

예를 들어 SQL F# 의 유형 공급자는 관계형 데이터베이스의 테이블 및 열을 나타내는 유형을 생성할 수 있습니다. 실제로 [sqlprovider](https://fsprojects.github.io/SQLProvider/) 형식 공급자는이 작업을 수행 합니다.

제공 된 형식은 형식 공급자의 입력 매개 변수에 따라 달라 집니다. 이러한 입력은 샘플 데이터 소스 (예: JSON 스키마 파일), 외부 서비스에 직접 가리키는 URL 또는 데이터 원본에 대 한 연결 문자열 일 수 있습니다. 형식 공급자는 필요에 따라 형식 그룹에만 확장 되도록 할 수도 있습니다. 즉, 프로그램에서 형식을 실제로 참조 하는 경우 확장 됩니다. 따라서 강력한 형식으로 온라인 데이터 시장과 같은 대규모 정보 공간의 직접적인 주문형 통합을 허용합니다.

## <a name="generative-and-erased-type-providers"></a>인기 및 지워진 형식 공급자

형식 공급자는 인기 및 지워진 두 가지 형식으로 제공 됩니다.

인기 형식 공급자는 생성 되는 어셈블리에 .NET 형식으로 작성할 수 있는 형식을 생성 합니다. 이렇게 하면 다른 어셈블리의 코드에서 사용 될 수 있습니다. 즉, 데이터 원본에 대 한 형식화 된 표현은 일반적으로 .NET 형식을 사용 하 여 나타낼 수 있는 것 이어야 합니다.

형식 공급자를 지우면 생성 된 어셈블리 또는 프로젝트 에서만 사용 될 수 있는 형식이 생성 됩니다. 형식은 삭제 됩니다. 즉, 어셈블리는 어셈블리에 기록 되지 않으며 다른 어셈블리의 코드에서 사용할 수 없습니다. *지연* 된 멤버를 포함할 수 있으므로 잠재적으로 무한 한 정보 공간에서 제공 된 형식을 사용할 수 있습니다. 이는 크고 상호 연결 된 데이터 원본의 작은 하위 집합을 사용 하는 데 유용 합니다.

## <a name="commonly-used-type-providers"></a>일반적으로 사용 되는 형식 공급자

다음과 같이 널리 사용 되는 라이브러리에는 다양 한 용도에 대 한 형식 공급자가 포함 되어 있습니다.

- [Fsharp.core](https://fsharp.github.io/FSharp.Data/) 에는 JSON, XML, CSV 및 HTML 문서 형식 및 리소스에 대 한 형식 공급자가 포함 되어 있습니다.
- [Sqlprovider](https://fsprojects.github.io/SQLProvider/) 는 이러한 데이터 원본에 대 한 개체 매핑 및 F# LINQ 쿼리를 통해 관계 데이터베이스에 대해 강력한 형식의 액세스를 제공 합니다.
- [Fsharp.core](https://fsprojects.github.io/FSharp.Data.SqlClient/) 에는의 F#t-sql을 확인 하는 컴파일 시간에 대 한 형식 공급자 집합이 있습니다.
- [Azure Storage 형식 공급자](https://fsprojects.github.io/AzureStorageTypeProvider/) 는 Azure Blob, 테이블 및 큐에 대 한 형식을 제공 하 여 프로그램 전체에서 리소스 이름을 문자열로 지정 하지 않고도 이러한 리소스에 액세스할 수 있도록 합니다.
- [Fsharp.core GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) 는 URL로 지정 된 GraphQL 서버를 기반으로 형식을 제공 하는 **GraphQLProvider**를 포함 합니다.

필요한 경우 [고유한 사용자 지정 형식 공급자를 만들거나 다른 사용자](creating-a-type-provider.md)가 만든 형식 공급자를 참조할 수 있습니다. 예를 들어 조직에 규모가 크고 점점 더 수가 증가하는 명명된 데이터 집합(각각 자체적으로 안정적인 데이터 스키마 포함)을 제공하는 데이터 서비스가 있다고 가정합니다. 강력한 방식으로 스키마를 읽고 프로그래머에 설정된 사용할 수 있는 최신 데이터 집합을 제공하는 형식 공급자를 만들도록 선택할 수 있습니다.

## <a name="see-also"></a>참조

- [자습서: 형식 공급자 만들기](creating-a-type-provider.md)
- [F# 언어 참조](../../language-reference/index.md)
