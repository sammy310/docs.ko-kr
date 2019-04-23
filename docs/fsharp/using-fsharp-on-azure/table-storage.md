---
title: 사용 하 여 Azure Table storage 시작F#
description: Azure Table storage 또는 Azure Cosmos DB를 사용 하 여 클라우드에 구조화 된 데이터를 저장 합니다.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 54c777acd454e4f675175b814675c185e41ad9a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086704"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Azure Table storage와 F를 사용 하 여 Azure Cosmos DB Table API 시작\#

Azure Table storage는 클라우드에 구조화 된 NoSQL 데이터를 저장 하는 서비스입니다. Table storage는 스키마 없이 디자인을 사용 하 여 키/특성 저장소입니다. 테이블 저장소는 스키마 때문에 응용 프로그램 진화에 필요에 따라 데이터에 맞게 쉽습니다. 데이터 액세스가 빠르고 비용 효율적으로 모든 종류의 응용 프로그램입니다. 테이블 저장소는 일반적으로 전통적인 SQL 비슷한 양의 데이터에 비해 비용이 매우 낮습니다.

웹 응용 프로그램, 주소록, 장치 정보 및 다른 유형의 서비스에 필요한 메타 데이터에 대 한 사용자 데이터와 같은 유연한 데이터 집합을 저장할 Table storage를 사용할 수 있습니다. 테이블의 엔터티 수를 저장할 수 있습니다 하 고 저장소 계정에는 임의 개수의 테이블을 저장소 계정의 용량 제한까지 포함 될 수 있습니다.

Azure Cosmos DB는 Azure Table storage 용으로 작성 및와 같은 프리미엄 기능이 필요한 응용 프로그램에 대 한 Table API를 제공 합니다.

- 턴키 전역 배포
- 전 세계 전용된 처리량입니다.
- 99 번째 백분위 수에서 1 자리 밀리초 대기 시간입니다.
- 고가용성을 보장 합니다.
- 자동 보조 인덱싱입니다.

Azure Table storage 용으로 작성 된 응용 프로그램 코드 변경 없이 Table API를 사용 하 여 Azure Cosmos DB에 마이그레이션 하 고 프리미엄 기능을 활용할 수 있습니다. Table API는.NET, Java, Python 및 Node.js에 대 한 사용할 수 있는 클라이언트 Sdk에 있습니다.

자세한 내용은 [Azure Cosmos DB Table API 소개](https://docs.microsoft.com/azure/cosmos-db/table-introduction)합니다.

## <a name="about-this-tutorial"></a>이 자습서 정보

이 자습서에서는 작성 하는 방법을 보여 줍니다. F# Azure Table storage 또는 Azure Cosmos DB 테이블 API를, 만들기 및 테이블을 삭제 및 삽입, 업데이트, 삭제 및 테이블 데이터 쿼리를 포함 하 여 사용 하 여 몇 가지 일반적인 작업을 수행 하는 코드입니다.

## <a name="prerequisites"></a>전제 조건

이 가이드를 사용 하려면 먼저 [Azure storage 계정 만들기](/azure/storage/storage-create-storage-account) 하거나 [Azure Cosmos DB 계정](https://azure.microsoft.com/try/cosmosdb/)합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>만들기는 F# 스크립트 및 시작 F# 대화형

이 문서의 샘플에서 사용할 수는 F# 응용 프로그램 또는 F# 스크립트입니다. 만들려는 F# 스크립트를 사용 하 여 파일을 만듭니다는 `.fsx` 예를 들어 확장 `tables.fsx`에서 F# 개발 환경입니다.

다음을 사용 하 여는 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 설치 하는 `WindowsAzure.Storage` 패키지 및 참조 `WindowsAzure.Storage.dll` 를사용하여스크립트에서`#r`지시문입니다. 에 대해 다시 수행 `Microsoft.WindowsAzure.ConfigurationManager` Microsoft.Azure 네임 스페이스를 가져오기 위해.

### <a name="add-namespace-declarations"></a>네임 스페이스 선언을 추가합니다

다음을 추가 합니다 `open` 의 맨 위에 문을 `tables.fsx` 파일:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Azure Storage 연결 문자열 가져오기

Azure Storage Table service에 연결 하는 경우이 자습서에 대 한 연결 문자열을 해야 합니다. Azure portal에서 연결 문자열을 복사할 수 있습니다. 연결 문자열에 대 한 자세한 내용은 참조 하세요. [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.

### <a name="get-your-azure-cosmos-db-connection-string"></a>Azure Cosmos DB 연결 문자열 가져오기

Azure Cosmos DB에 연결 하는 경우이 자습서에 대 한 연결 문자열을 해야 합니다. Azure portal에서 연결 문자열을 복사할 수 있습니다. Cosmos DB 계정에 Azure portal로 이동 **설정을** > **연결 문자열**를 클릭 합니다 **복사** 기본 연결을 복사 하는 단추 문자열입니다. 

자습서의 경우 다음 예제와 같이 스크립트에서 연결 문자열을 입력:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

그러나 이것이 **좋지** 실제 프로젝트입니다. 저장소 계정 키는 저장소 계정의 루트 암호와 비슷합니다. 항상 저장소 계정 키를 보호 해야 합니다. 다른 사용자에 하드 코딩 하거나 다른 사용자에 게 액세스할 수 있는 일반 텍스트 파일을 저장 하 게 배포 하지 마세요. 손상 되었다고 생각 하는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에서 됩니다. 구성 파일에서 연결 문자열을 가져올,이 수행할 수 있습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Azure 구성 관리자를 사용 하는 것은 선택 사항입니다. .NET Framework의 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 형식입니다.

### <a name="parse-the-connection-string"></a>연결 문자열을 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

반환 된 `CloudStorageAccount`합니다.

### <a name="create-the-table-service-client"></a>Table service 클라이언트 만들기

`CloudTableClient` 클래스를 사용 하면 테이블 및 Table storage의 엔터티를 검색할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

이제 데이터를 읽어 오고 테이블 저장소에 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.

### <a name="create-a-table"></a>테이블 생성하기

이 예제에는 아직 존재 하지 않는 경우 테이블을 만드는 방법을 보여 줍니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>테이블에 엔터티 추가

상속 되는 형식에 엔터티 `TableEntity`합니다. 확장할 수 있습니다 `TableEntity` 원하는 어떤 방식으로든 형식 에서만 *해야* 매개 변수가 없는 생성자가 있습니다. 둘 다 있는 속성만 `get` 고 `set` Azure 테이블에 저장 됩니다.

엔터티의 파티션과 행 키 테이블에서 엔터티를 고유 하 게 식별 합니다. 동일한 파티션 키를 가진 엔터티는 다른 파티션 키를 사용 하는 것 보다 더 빠르게 쿼리할 수 있지만 다양 한 파티션 키를 사용 하 여 병렬 작업 확장성을 높일 수 있습니다.

예로 `Customer` 를 사용 하는 `lastName` 파티션 키로 및 `firstName` 행 키로 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

이제 추가 `Customer` 테이블입니다. 이렇게 하려면 만들기를 `TableOperation` 테이블에서 실행 하는 합니다. 만든이 경우에 `Insert` 작업 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>엔터티 일괄 삽입

단일 쓰기 작업을 사용 하 여 테이블에 엔터티를 일괄을 삽입할 수 있습니다. 일괄 처리 작업을 사용 하면 단일 실행에 대 한 작업을 결합 하 하지만 몇 가지 제한 사항이 있습니다.

- 업데이트를 수행할 수 있습니다, 삭제 하 고 동일한 일괄 처리 작업에서 삽입 합니다.
- 일괄 처리 작업을 최대 100 개의 엔터티가 포함 될 수 있습니다.
- 일괄 처리 작업의 모든 엔터티에 동일한 파티션 키에 있어야 합니다.
- 일괄 처리 작업에서 쿼리를 수행할 수 있지만, 일괄 처리의 유일한 작업 이어야 합니다.

두 삽입 일괄 처리 작업으로 결합 하는 일부 코드는 다음과 같습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>파티션의 모든 엔터티 검색

테이블 파티션의 모든 엔터티를 쿼리하려면 사용을 `TableQuery` 개체입니다. 여기에서 필터링 할 엔터티에 대 한 "Smith" 인 파티션 키.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

이제 결과 인쇄 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a>파티션의 엔터티 범위 검색

파티션의 모든 엔터티를 쿼리하지 않으려면 파티션 키 필터를 행 키 필터와 결합 하 여 범위를 지정할 수 있습니다. 여기에서 두 필터를 사용 하면 "Smith" 파티션의 모든 엔터티를 가져온 행 키 (이름)로 시작 하는 문자 "M" 알파벳에서 보다 이전입니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

이제 결과 인쇄 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>단일 엔터티 검색

단일 특정 엔터티를 검색 하는 쿼리를 작성할 수 있습니다. 여기에서 사용 하 여는 `TableOperation` 고객 "Ben Smith"를 지정 합니다. 컬렉션 대신 받게는 `Customer`합니다. Table service에서 단일 엔터티를 검색 하는 가장 빠른 방법은 쿼리에서 파티션 키와 행 키를 지정 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

이제 결과 인쇄 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a>엔터티 바꾸기

엔터티를 업데이트 하려면 Table service에서 검색, 엔터티 개체를 수정한 다음 변경 내용을 다시 사용해 서 Table service에 저장 된 `Replace` 작업 합니다. 이렇게 하면 작업이 실패 하는 경우, 검색 된 이후 서버에서 엔터티가 변경 되지 않은 엔터티를 서버에서 완전히 바뀝니다. 다른 원본의 변경 내용을 실수로 덮어쓰는에서 응용 프로그램을 방지 하기 위해이 오류는입니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>삽입 또는 바꾸기 엔터티

경우에 따라 엔터티를 테이블에 있는지 여부를 모르는 경우 및에 저장 된 현재 값을 더 이상 필요 없는 경우. 사용할 수 있습니다 `InsertOrReplace` 엔터티를 만들거나 해당 상태에 관계 없이 존재 하는 경우 이름을 바꿉니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>엔터티 속성 하위 집합 쿼리

테이블 쿼리 전체가 아닌 엔터티에서 일부 속성만 검색할 수 있습니다. 프로젝션 이라고 하는이 기술은 특히 큰 엔터티에 대의 쿼리 성능을 향상 시킬 수 있습니다. 이때 돌아가게만 전자 메일 주소를 사용 하 여 `DynamicTableEntity` 고 `EntityResolver`입니다. 이 코드는 테이블 서비스의 계정을 사용 하는 경우에 실행 되도록 프로젝션 로컬 저장소 에뮬레이터에서 지원 되지 않습니다는 참고 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>페이지에서 엔터티를 비동기적으로 검색

많은 수의 엔터티를 읽는 처리할 때 검색 될 때 기다리지 않고 이러한 모든 반환 하는 경우에 분할 된 쿼리를 사용할 수 있습니다. 여기서 돌아가게 결과 페이지에서 반환할 결과의 큰 집합을 기다리는 동안 실행이 차단 되지 않도록 하는 비동기 워크플로 사용 하 여 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

하면 이제이 계산 동기적으로 실행 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>엔터티 삭제

검색 한 후 엔터티를 삭제할 수 있습니다. 엔터티 업데이트와 마찬가지로 엔터티 것을 검색 한 후 변경 된 경우 실패 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>테이블 삭제

저장소 계정에서 테이블을 삭제할 수 있습니다. 삭제 된 테이블을 삭제 후 기간에 대 한 다시 만들어야 사용할 수 없게 됩니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>다음 단계

이제 테이블 저장소의 기본 사항을 배웠으므로 다음 링크를 더 복잡 한 저장소 작업 및 Azure Cosmos DB Table API에 대해 알아봅니다.

- [Azure Cosmos DB Table API 소개](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [.NET 용 storage 클라이언트 라이브러리](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [Azure Storage 형식 공급자](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure Storage 팀 블로그](https://blogs.msdn.com/b/windowsazurestorage/)
- [연결 문자열 구성](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [.NET에서 Azure Table Storage 시작](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
