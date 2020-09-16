---
title: F#을 사용하여 Azure Queue 스토리지 시작
description: Azure 큐는 애플리케이션 구성 요소 간에 안정적인 비동기 메시징을 제공합니다. 클라우드 메시징을 사용하면 애플리케이션 구성 요소를 독립적으로 조정할 수 있습니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 0b360348ce6966ce49a2ac0abd839844bdbe55f2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548366"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>F #을 사용 하 여 Azure Queue storage 시작\#

Azure Queue Storage는 애플리케이션 구성 요소 간에 클라우드 메시징을 제공합니다. 규모를 고려하여 애플리케이션을 디자인할 때는 애플리케이션 구성 요소를 개별적으로 확장할 수 있도록 각 구성 요소를 분리하는 경우가 많습니다. Queue Storage는 클라우드, 데스크톱, 온-프레미스 서버 또는 모바일 디바이스에서 실행 중인지와 관계 없이 애플리케이션 구성 요소 간에 통신을 위한 비동기 메시징을 제공합니다. Queue Storage는 또한 비동기 작업 관리와 프로세스 워크플로 작성을 지원합니다.

### <a name="about-this-tutorial"></a>이 자습서 정보

이 자습서에서는 Azure Queue storage를 사용 하 여 몇 가지 일반적인 작업을 위해 F # 코드를 작성 하는 방법을 보여 줍니다. 큐 만들기 및 삭제, 큐 메시지 추가, 읽기 및 삭제 등의 작업을 다룹니다.

큐 저장소에 대 한 개념적 개요는 [queue storage에 대 한 .net 가이드](/azure/storage/storage-dotnet-how-to-use-queues)를 참조 하세요.

## <a name="prerequisites"></a>필수 구성 요소

이 가이드를 사용 하려면 먼저 [Azure storage 계정을 만들어야](/azure/storage/storage-create-storage-account)합니다.
이 계정에 대 한 저장소 액세스 키도 필요 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>F # 스크립트를 만들고 F# 대화형를 시작 합니다.

이 문서의 샘플은 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다. F # 스크립트를 만들려면 `.fsx` `queues.fsx` f # 개발 환경에서 확장명을 사용 하 여 파일을 만듭니다.

그런 다음 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 과 같은 [패키지 관리자](package-management.md) 를 사용 하 여 패키지를 설치 하 `WindowsAzure.Storage` 고 `WindowsAzure.Storage.dll` 지시어를 사용 하 여 스크립트에 참조 합니다 `#r` .

### <a name="add-namespace-declarations"></a>네임스페이스 선언 추가

`queues.fsx` 파일 맨 위에 다음 `open` 문을 추가합니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서에 대 한 Azure Storage 연결 문자열이 필요 합니다. 연결 문자열에 대 한 자세한 내용은 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)을 참조 하세요.

자습서의 경우 다음과 같이 스크립트에 연결 문자열을 입력 합니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

그러나 실제 프로젝트에는이 방법이 **권장 되지 않습니다** . 스토리지 계정 키는 스토리지 계정의 루트 암호와 비슷합니다. 항상 스토리지 계정 키를 보호해야 합니다. 다른 사용자에게 배포하거나 하드 코딩하거나 다른 사람이 액세스할 수 있는 일반 텍스트 파일에 저장하지 마십시오. 손상 된 것으로 생각 되는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램의 경우 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에 있습니다. 구성 파일에서 연결 문자열을 가져오려면 다음을 수행할 수 있습니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Azure 구성 관리자 사용은 선택 사항입니다. .NET Framework의 형식과 같은 API를 사용할 수도 있습니다 `ConfigurationManager` .

### <a name="parse-the-connection-string"></a>연결 문자열 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

그러면이 반환 됩니다 `CloudStorageAccount` .

### <a name="create-the-queue-service-client"></a>큐 서비스 클라이언트 만들기

`CloudQueueClient`클래스를 사용 하면 Queue storage에 저장 된 큐를 검색할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

이제 데이터를 읽어 오고 Queue Storage에 데이터를 기록하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-queue"></a>큐 만들기

이 예제에서는 큐가 없는 경우 큐를 만드는 방법을 보여 줍니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>큐에 메시지 삽입

기존 큐에 메시지를 삽입 하려면 먼저 새를 만듭니다 `CloudQueueMessage` . 그런 다음 메서드를 호출 `AddMessage` 합니다. 는 `CloudQueueMessage` 다음과 같이 문자열 (utf-8 형식) 또는 배열에서 만들 수 있습니다 `byte` .

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>다음 메시지 보기

큐에서 메시지를 제거 하지 않고 메서드를 호출 하 여 큐의 맨 앞에 있는 메시지를 피킹할 수 있습니다 `PeekMessage` .

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>처리할 다음 메시지 가져오기

메서드를 호출 하 여 큐의 맨 앞에 있는 메시지를 검색 하 여 처리할 수 있습니다 `GetMessage` .

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

나중에를 사용 하 여 성공적으로 메시지 처리를 표시 `DeleteMessage` 합니다.

## <a name="change-the-contents-of-a-queued-message"></a>대기 중인 메시지의 콘텐츠 변경

큐에서 검색 된 메시지의 콘텐츠를 즉시 변경할 수 있습니다. 메시지가 작업을 나타내는 경우 이 기능을 사용하여 작업의 상태를 업데이트할 수 있습니다. 다음 코드는 큐 메시지를 새로운 콘텐츠로 업데이트하고 표시 제한 시간이 60초 더 늘어나도록 설정합니다. 그러면 메시지와 연결된 작업의 상태가 저장되고 클라이언트에서 메시지에 대한 작업을 계속할 수 있는 시간이 1분 더 허용됩니다. 이 기술을 사용하여 처리 단계가 하드웨어 또는 소프트웨어 오류로 인해 실패하는 경우 처음부터 시작하지 않고도 큐 메시지에 대한 여러 단계의 워크플로를 추적할 수 있습니다. 일반적으로 다시 시도 수를 유지 하 고, 메시지를 몇 번 이상 다시 시도 하는 경우 삭제 합니다. 이 기능은 처리될 때마다 애플리케이션 오류를 트리거하는 메시지를 차단하여 보호해 줍니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>큐에서 다음 메시지 제거

다음 코드는 2단계를 거쳐 큐에서 메시지를 제거합니다. 를 호출 하면 `GetMessage` 큐에서 다음 메시지를 가져옵니다. `GetMessage`에서 반환된 메시지는 이 큐의 메시지를 읽는 다른 코드에는 표시되지 않습니다. 기본적으로, 이 메시지는 30초간 표시되지 않습니다. 큐에서 메시지 제거를 완료 하려면도 호출 해야 `DeleteMessage` 합니다. 메시지를 제거하는 이 2단계 프로세스는 코드가 하드웨어 또는 소프트웨어 오류로 인해 메시지를 처리하지 못하는 경우 코드의 다른 인스턴스가 동일한 메시지를 가져와서 다시 시도할 수 있도록 보장합니다. 코드 `DeleteMessage` 는 메시지가 처리 된 직후에 호출 됩니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>공통 큐 저장소 Api와 함께 비동기 워크플로 사용

이 예제에서는 공통 큐 저장소 Api와 함께 비동기 워크플로를 사용 하는 방법을 보여 줍니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>큐에서 메시지를 제거하기 위한 추가적인 옵션

큐에서 메시지 검색을 사용자 지정할 수 있는 방법으로는 두 가지가 있습니다.
먼저, 메시지의 배치(최대 32개)를 가져올 수 있습니다. 두 번째로, 표시하지 않는 제한 시간을 더 길거나 더 짧게 설정하여 코드에서 각 메시지를 완전히 처리하는 시간을 늘리거나 줄일 수 있습니다. 다음 코드 예제에서는 `GetMessages` 를 사용 하 여 한 번 호출에 20 개의 메시지를 가져온 다음 각 메시지를 처리 합니다. 또한 각 메시지에 대해 표시하지 않는 제한 시간을 5분으로 설정합니다. 5 분은 모든 메시지에 대해 동시에 시작 되므로,에 대 한 호출 이후로 5 분이 경과 된 후에는 `GetMessages` 삭제 되지 않은 모든 메시지가 다시 표시 됩니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>큐 길이 가져오기

큐에 있는 메시지의 추정된 개수를 가져올 수 있습니다. `FetchAttributes`메서드는 메시지 수를 포함 하 여 큐 특성을 검색 하도록 큐 서비스에 요청 합니다. `ApproximateMessageCount`속성은 `FetchAttributes` 큐 서비스를 호출 하지 않고 메서드에서 검색 된 마지막 값을 반환 합니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>큐 삭제

큐 및 해당 큐에 포함 된 모든 메시지를 삭제 하려면 `Delete` 큐 개체에서 메서드를 호출 합니다.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>다음 단계

이제 Queue Storage의 기본 사항을 배웠으므로 다음 링크를 따라 좀 더 복잡한 스토리지 작업에 대해 알아보세요.

- [.NET용 Azure Storage API](/dotnet/api/overview/azure/storage)
- [Azure Storage 형식 공급자](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure Storage 팀 블로그](/archive/blogs/windowsazurestorage/)
- [Azure Storage 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage 서비스 REST API 참조](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
