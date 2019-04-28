---
title: 사용 하 여 Azure 큐 저장소 시작F#
description: Azure 큐는 응용 프로그램 구성 요소 간에 안정적이 고 비동기 메시징을 제공 합니다. 클라우드 메시징을 사용 하면 독립적으로 확장할 응용 프로그램 구성 요소입니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756379"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>F를 사용 하 여 Azure Queue storage 시작\#

Azure Queue storage는 응용 프로그램 구성 요소 간에 클라우드 메시징을 제공 합니다. 눈금에 대 한 응용 프로그램을 디자인, 응용 프로그램 구성 요소는 종종 분리 독립적으로 확장할 수 있도록. Queue storage는 클라우드, 데스크톱, 온-프레미스 서버를 또는 모바일 장치에서에서 실행 중인지 여부를 응용 프로그램 구성 요소 간의 통신을 위한 비동기 메시징을 제공 합니다. 큐 저장소는 비동기 작업 관리와 프로세스 워크플로 작성도 지원 합니다.

### <a name="about-this-tutorial"></a>이 자습서 정보

이 자습서에서는 작성 하는 방법을 보여 줍니다. F# Azure Queue storage를 사용 하 여 몇 가지 일반적인 작업에 대 한 코드입니다. 다루는 작업 만들기 및 큐를 삭제 하 고 추가, 읽기 및 큐 메시지를 삭제를 포함 합니다.

큐 저장소의 개념적인 개요를 참조 하세요 [큐 저장소에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-queues)합니다.

## <a name="prerequisites"></a>전제 조건

이 가이드를 사용 하려면 먼저 [Azure storage 계정 만들기](/azure/storage/storage-create-storage-account)합니다.
또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>만들기는 F# 스크립트 및 시작 F# 대화형

이 문서의 샘플에서 사용할 수는 F# 응용 프로그램 또는 F# 스크립트입니다. 만들려는 F# 스크립트를 사용 하 여 파일을 만듭니다는 `.fsx` 예를 들어 확장 `queues.fsx`에서 F# 개발 환경입니다.

다음을 사용 하 여는 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 설치 하는 `WindowsAzure.Storage` 패키지 및 참조 `WindowsAzure.Storage.dll` 를사용하여스크립트에서`#r`지시문입니다.

### <a name="add-namespace-declarations"></a>네임 스페이스 선언을 추가합니다

다음을 추가 합니다 `open` 의 맨 위에 문을 `queues.fsx` 파일:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서에 대 한 Azure Storage 연결 문자열을 해야 합니다. 연결 문자열에 대 한 자세한 내용은 참조 하세요. [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.

자습서의 경우 다음과 같은 스크립트에서 연결 문자열을 입력 있습니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

그러나 이것이 **좋지** 실제 프로젝트입니다. 저장소 계정 키는 저장소 계정의 루트 암호와 비슷합니다. 항상 저장소 계정 키를 보호 해야 합니다. 다른 사용자에 하드 코딩 하거나 다른 사용자에 게 액세스할 수 있는 일반 텍스트 파일을 저장 하 게 배포 하지 마세요. 손상 되었다고 생각 하는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에서 됩니다. 구성 파일에서 연결 문자열을 가져올,이 수행할 수 있습니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Azure 구성 관리자를 사용 하는 것은 선택 사항입니다. .NET Framework의 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 형식입니다.

### <a name="parse-the-connection-string"></a>연결 문자열을 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

이 반환 된 `CloudStorageAccount`합니다.

### <a name="create-the-queue-service-client"></a>큐 서비스 클라이언트 만들기

`CloudQueueClient` 클래스를 사용 하면 큐 저장소에 저장 된 큐를 검색할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

이제 데이터를 읽어 오고 큐 저장소로 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-queue"></a>큐 만들기

이 예제에는 이미 존재 하지 않는 경우 큐를 만드는 방법을 보여 줍니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>큐에 메시지를 삽입 합니다.

기존 큐에 메시지를 삽입, 먼저 만들려면 새 `CloudQueueMessage`합니다. 그런 다음 호출 하 여 `AddMessage` 메서드. A `CloudQueueMessage` 문자열 (utf-8 형식)에서 만들 수 있습니다 또는 `byte` 같이 배열:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>다음 메시지를 피킹하십시오

호출 하 여 큐에서 제거 하지 않고 큐 앞의 메시지를 피킹할 수 있습니다는 `PeekMessage` 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>처리를 위해 다음 메시지를 가져옵니다.

호출 하 여 처리를 위해 큐의 앞에서 메시지를 검색할 수 있습니다는 `GetMessage` 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

나중에 사용 하 여 메시지를 성공적으로 처리를 나타낼 `DeleteMessage`합니다.

## <a name="change-the-contents-of-a-queued-message"></a>대기 중인된 메시지의 내용을 변경합니다

검색된 메시지에에서 있는 큐의 내용을 변경할 수 있습니다. 메시지 작업을 나타내는 경우에 작업의 상태를 업데이트 하려면이 기능을 사용할 수 있습니다. 다음 코드는 큐 메시지를 새로운 콘텐츠로 업데이트 하 고 표시 제한 시간이 60 초 더 늘어나도록 설정 합니다. 이 메시지와 연결 된 작업의 상태를 저장 하 고 클라이언트 메시지에 작업을 계속 하려면 다른 분을 제공 합니다. 처리 단계가 하드웨어 또는 소프트웨어 오류로 인해 실패 하면 처음부터 다시 시작 하지 않고도 큐 메시지에서 다단계 워크플로 추적 하려면이 기법을 사용할 수 있습니다. 일반적으로 재시도 횟수를 유지 하 고 메시지를 몇 번 이상 다시 시도 하는 경우 파일을 삭제 합니다. 이 처리 될 때마다 응용 프로그램 오류를 트리거하는 메시지를 보호 합니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>큐에서 다음 메시지 제거

코드는 두 단계를 거쳐 큐에서 메시지를 큐에서 제거 합니다. 호출 하는 경우 `GetMessage`, 큐에서 다음 메시지를 가져옵니다. 반환 된 메시지 `GetMessage` 이 큐에서 메시지를 읽는 다른 코드에 표시 되지 않습니다. 이 메시지 기본적으로 30 초 동안 보이지 않는 유지 됩니다. 큐에서 메시지 제거를 완료 하려면 호출도 해야 `DeleteMessage`합니다. 메시지를 제거 하는이 2 단계 프로세스는 코드가 하드웨어 또는 소프트웨어 오류로 인해 메시지를 처리 하는 데 실패 하는 경우 코드의 다른 인스턴스가 수 동일한 메시지가 다시 시도 보장 합니다. 코드 호출 `DeleteMessage` 직후 메시지가 처리 되었습니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>일반적인 큐 저장소 Api와 함께 사용 하 여 비동기 워크플로

이 예제에서는 일반적인 큐 저장소 Api 사용 하 여 비동기 워크플로 사용 하는 방법을 보여 줍니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>취소 큐 메시지에 대 한 추가 옵션

두 가지 방법으로 큐에서 메시지 검색을 사용자 지정할 수 있습니다.
먼저 배치 (최대 32 개) 메시지를 가져올 수 있습니다. 둘째, 각 메시지를 완전히 처리 하는 데 시간이 덜 자세한 또는 코드를 허용 더 길거나 더 짧은 표시 안 함 시간 제한을 설정할 수 있습니다. 다음 코드 예제에서는 `GetMessages` 얻으려면 20 메시지 하나를 호출 하 고 다음 각 메시지를 처리 합니다. 또한 각 메시지에 대해 5 분 내에 표시 하지 않는 제한 시간을 설정합니다. 5 분부터 모든 메시지에 대해 동시에는 호출 후 5 분 경과 `GetMessages`, 삭제 되지 않은 모든 메시지가 다시 표시 됩니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>큐 길이 가져오기

큐의 메시지 수의 추정치를 얻을 수 있습니다. `FetchAttributes` 메서드는 메시지 수를 포함 하 여 큐 특성을 검색 하도록 큐 서비스에 요청 합니다. 합니다 `ApproximateMessageCount` 속성에서 검색 된 마지막 값을 반환 합니다 `FetchAttributes` , 큐 서비스를 호출 하지 않고 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>큐 삭제

큐 및 그 안에 포함 된 모든 메시지를 삭제 하려면 호출을 `Delete` 큐 개체의 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>다음 단계

이제 큐 저장소의 기본 사항을 배웠으므로 다음 링크를 더 복잡 한 저장소 작업에 대해 알아보세요.

- [.NET 용 azure Storage Api](/dotnet/api/overview/azure/storage)
- [Azure Storage 형식 공급자](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure Storage 팀 블로그](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Azure Storage 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage 서비스 REST API 참조](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
