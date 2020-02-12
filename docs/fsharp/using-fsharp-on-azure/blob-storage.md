---
title: F#을 사용하여 Azure Blob 스토리지 시작
description: Azure Blob storage를 사용 하 여 클라우드에 구조화 되지 않은 데이터를 저장 합니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 79f6a559ac603b0544916764126a988d3f3f43d7
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092631"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>F\#를 사용 하 여 Azure Blob storage 시작

Azure Blob Storage는 클라우드에서 구조화되지 않은 데이터를 개체/Blob으로 저장하는 서비스입니다. Blob Storage는 문서, 미디어 파일, 애플리케이션 설치 관리자 등과 같은 모든 유형의 텍스트 또는 이진 데이터를 저장할 수 있습니다. Blob 스토리지를 개체 스토리지라고도 합니다.

이 문서에서는 Blob storage를 사용 하 여 일반적인 작업을 수행 하는 방법을 보여 줍니다. 샘플은 .NET 용 Azure Storage F# 클라이언트 라이브러리를 사용 하 여 작성 되었습니다. 여기에서 설명 하는 태스크에는 blob을 업로드, 나열, 다운로드 및 삭제 하는 방법이 포함 됩니다.

Blob 저장소에 대 한 개념적 개요는 [blob 저장소에 대 한 .net 가이드](/azure/storage/blobs/storage-quickstart-blobs-dotnet)를 참조 하세요.

## <a name="prerequisites"></a>필수 구성 요소

이 가이드를 사용 하려면 먼저 [Azure storage 계정을 만들어야](/azure/storage/common/storage-account-create)합니다. 이 계정에 대 한 저장소 액세스 키도 필요 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>F# 스크립트 만들기 및 대화형 시작 F#

이 문서의 샘플은 F# 응용 프로그램 또는 F# 스크립트에서 사용할 수 있습니다. F# 스크립트를 만들려면 F# 개발 환경에서 `blobs.fsx`같은 `.fsx` 확장명을 사용 하 여 파일을 만듭니다.

그런 다음 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 과 같은 [패키지 관리자](package-management.md) 를 사용 하 여 `WindowsAzure.Storage`를 설치 하 고 `#r` 지시문을 사용 하 여 스크립트에 `WindowsAzure.Storage.dll` 및 `Microsoft.WindowsAzure.Configuration.dll`를 `Microsoft.WindowsAzure.ConfigurationManager` 합니다.

### <a name="add-namespace-declarations"></a>네임스페이스 선언 추가

`open` 파일 맨 위에 다음 `blobs.fsx` 문을 추가합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서에서는 Azure Storage 연결 문자열이 필요 합니다. 연결 문자열에 대 한 자세한 내용은 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)을 참조 하세요.

자습서의 경우 다음과 같이 스크립트에 연결 문자열을 입력 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

그러나 실제 프로젝트에는이 방법이 **권장 되지 않습니다** . 스토리지 계정 키는 스토리지 계정의 루트 암호와 비슷합니다. 항상 스토리지 계정 키를 보호해야 합니다. 다른 사용자에게 배포하거나 하드 코딩하거나 다른 사람이 액세스할 수 있는 일반 텍스트 파일에 저장하지 마십시오. 손상 된 것으로 생각 되는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램의 경우 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에 있습니다. 구성 파일에서 연결 문자열을 가져오려면 다음을 수행할 수 있습니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Azure 구성 관리자 사용은 선택 사항입니다. .NET Framework의 `ConfigurationManager` 형식과 같은 API를 사용할 수도 있습니다.

### <a name="parse-the-connection-string"></a>연결 문자열 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

그러면 `CloudStorageAccount`반환 됩니다.

### <a name="create-some-local-dummy-data"></a>로컬 더미 데이터 만들기

시작 하기 전에 스크립트의 디렉터리에 더미 로컬 데이터를 만듭니다. 나중에이 데이터를 업로드 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Blob service 클라이언트 만들기

`CloudBlobClient` 형식을 사용 하면 Blob 저장소에 저장 된 컨테이너 및 blob을 검색할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

이제 데이터를 읽어 오고 Blob Storage에 데이터를 기록하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-container"></a>컨테이너 만들기

이 예제에서는 컨테이너가 없는 경우 만드는 방법을 보여 줍니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

기본적으로 새 컨테이너는 프라이빗입니다. 즉, 이 컨테이너에서 Blob을 다운로드하려면 스토리지 액세스 키를 지정해야 합니다. 컨테이너 내의 파일을 모든 사용자가 사용할 수 있게 하려는 경우 다음 코드를 사용하여 컨테이너를 공용으로 설정할 수 있습니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

인터넷상의 누구든지 공용 컨테이너의 Blob을 볼 수 있지만 적절한 계정 선택키 또는 공유 액세스 서명이 있는 경우에만 수정하거나 삭제할 수 있습니다.

## <a name="upload-a-blob-into-a-container"></a>컨테이너에 Blob 업로드

Azure Blob Storage는 블록 Blob 및 페이지 Blob을 지원합니다. 대부분의 경우 블록 blob은 사용 하기에 권장 되는 형식입니다.

블록 Blob에 파일을 업로드하려면 컨테이너 참조를 가져온 다음 이 참조를 사용하여 블록 Blob 참조를 가져옵니다. Blob 참조가 있으면 `UploadFromFile` 메서드를 호출 하 여 데이터 스트림을 업로드할 수 있습니다. 이 작업은 blob이 없는 경우 새로 만들고, blob이 있는 경우 덮어씁니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>컨테이너의 Blob 나열

컨테이너의 Blob을 나열하려면 먼저 컨테이너 참조를 가져옵니다. 그런 다음 컨테이너의 `ListBlobs` 메서드를 사용 하 여 컨테이너 내의 blob 및/또는 디렉터리를 검색할 수 있습니다. 반환 된 `IListBlobItem`에 대 한 다양 한 속성 및 메서드 집합에 액세스 하려면이를 `CloudBlockBlob`, `CloudPageBlob`또는 `CloudBlobDirectory` 개체로 캐스팅 해야 합니다. 형식을 알 수 없는 경우 형식 검사를 사용하여 캐스트할 형식을 확인할 수 있습니다. 다음 코드는 `mydata` 컨테이너에 있는 각 항목의 URI를 검색하고 출력하는 방법을 보여 줍니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

이름에 경로 정보를 사용 하 여 blob의 이름을 지정할 수도 있습니다. 이렇게 하면 기존 파일 시스템과 같이 구성 및 트래버스할 수 있는 가상 디렉터리 구조를 만듭니다. 디렉터리 구조는 가상만 해당됩니다. Blob Storage에서 사용할 수 있는 리소스만 컨테이너 및 Blob입니다. 그러나 저장소 클라이언트 라이브러리는 가상 디렉터리를 참조 하는 `CloudBlobDirectory` 개체를 제공 하 고 이러한 방식으로 구성 된 blob을 사용 하 여 작업 하는 프로세스를 간소화 합니다.

예를 들어 `photos`컨테이너에 있는 다음 블록 Blob 집합을 고려합니다.

*photo1*\
*2015/아키텍처/설명 .txt*\
*2015/architecture/photo3*\
*2015/architecture/photo4*\
*2016/architecture/photo5*\
*2016/architecture/photo6*\
*2016/아키텍처/설명 .txt*\
*2016/photo7*\

위의 샘플과 같이 컨테이너에서 `ListBlobs`를 호출 하면 계층적 목록이 반환 됩니다. 컨테이너의 디렉터리와 blob을 각각 나타내는 `CloudBlobDirectory` 및 `CloudBlockBlob` 개체를 모두 포함 하는 경우 결과 출력은 다음과 유사 합니다.

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

필요에 따라 `ListBlobs` 메서드의 `UseFlatBlobListing` 매개 변수를 `true`로 설정할 수 있습니다. 이 경우 컨테이너의 모든 blob은 `CloudBlockBlob` 개체로 반환 됩니다. 플랫 목록을 반환 하는 `ListBlobs`에 대 한 호출은 다음과 같습니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

컨테이너의 현재 내용에 따라 결과는 다음과 같습니다.

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a>Blob 다운로드

Blob을 다운로드 하려면 먼저 blob 참조를 검색 한 다음 `DownloadToStream` 메서드를 호출 합니다. 다음 예제에서는 `DownloadToStream` 메서드를 사용 하 여 blob 콘텐츠를 스트림 개체로 전송한 다음이 개체를 로컬 파일에 유지할 수 있습니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

`DownloadToStream` 메서드를 사용 하 여 blob 콘텐츠를 텍스트 문자열로 다운로드할 수도 있습니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Blob 삭제

Blob을 삭제 하려면 먼저 blob 참조를 가져온 다음이 참조에 대 한 `Delete` 메서드를 호출 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>여러 페이지에서 비동기식으로 Blob 나열

많은 수의 Blob을 나열하거나 한 번의 나열 작업에서 반환되는 결과 수를 제어하려는 경우에는 여러 결과 페이지에 Blob을 나열할 수 있습니다. 이 예제에서는 여러 페이지에서 비동기식으로 결과를 반환하는 방법을 보여 주므로 큰 결과 집합이 반환되도록 기다리는 동안 실행이 차단되지 않습니다.

이 예에서는 플랫 blob 목록을 표시 하지만 `ListBlobsSegmentedAsync` 메서드의 `useFlatBlobListing` 매개 변수를 `false`로 설정 하 여 계층적 목록을 수행할 수도 있습니다.

이 샘플에서는 `async` 블록을 사용 하 여 비동기 메서드를 정의 합니다. ``let!`` 키워드는 나열 작업이 완료 될 때까지 샘플 메서드의 실행을 일시 중단 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

이제 다음과 같이이 비동기 루틴을 사용할 수 있습니다. 먼저이 자습서의 앞부분에서 만든 로컬 파일을 사용 하 여 더미 데이터를 업로드 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

이제 루틴을 호출 합니다. `Async.RunSynchronously`를 사용 하 여 비동기 작업을 강제로 실행 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>추가 Blob에 쓰기

추가 Blob은 로깅 등의 추가 작업에 최적화되어 있습니다. 블록 Blob과 마찬가지로 추가 Blob은 블록으로 구성되지만 추가 Blob에 새 블록을 추가할 때 항상 Blob 끝에 추가됩니다. 추가 Blob의 기존 블록을 업데이트하거나 삭제할 수는 없습니다. 블록 Blob과 달리 추가 Blob의 블록 ID는 노출되지 않습니다.

추가 Blob의 각 블록은 최대 4MB까지 다양한 크기일 수 있으며, 추가 Blob 하나에 최대 50,000개의 블록이 포함될 수 있습니다. 따라서 추가 Blob의 최대 크기는 195GB(4MB X 50,000개 블록)보다 약간 더 큽니다.

다음 예에서는 새 추가 blob을 만들고 일부 데이터를 추가 하 여 간단한 로깅 작업을 시뮬레이션 합니다.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

세 가지 Blob 유형의 차이점에 대한 자세한 내용은 [블록 Blob, 페이지 Blob 및 추가 Blob 이해](https://msdn.microsoft.com/library/azure/ee691964.aspx) 를 참조하세요.

## <a name="concurrent-access"></a>동시 액세스

여러 클라이언트 또는 여러 프로세스 인스턴스에서 Blob에 대한 동시 액세스를 지원하려면 **ETags** 또는 **임대**를 사용할 수 있습니다.

- **Etag** - Blob이나 컨테이너를 다른 프로세스에서 수정했는지 감지할 수 있습니다.

- **임대** - Blob에 대해 일정 기간 동안 단독, 갱신 가능, 쓰기 또는 삭제 권한을 얻을 수 있습니다.

자세한 내용은 [Microsoft Azure Storage에서 동시성 관리](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)를 참조 하세요.

## <a name="naming-containers"></a>컨테이너 이름 지정

Azure Storage의 모든 Blob은 컨테이너에 있어야 합니다. 컨테이너는 Blob 이름의 일부를 형성합니다. 예를 들어 `mydata` 은(는) 이러한 샘플 Blob URI에서 컨테이너의 이름입니다.

- `https://storagesample.blob.core.windows.net/mydata/blob1.txt`
- `https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg`

컨테이너 이름은 유효한 DNS 이름이어야 하고 다음 명명 규칙을 따라야 합니다.

1. 컨테이너 이름은 문자 또는 숫자로 시작해야 하며 문자, 숫자 및 대시(-) 문자를 포함할 수 있습니다.
1. 컨테이너 이름에서 모든 대시(-) 문자는 문자 또는 숫자 바로 앞뒤에 와야 하며 연속 대시를 사용할 수 없습니다.
1. 컨테이너 이름의 모든 문자는 소문자여야 합니다.
1. 컨테이너 이름의 길이는 3자 이상, 63자 이하여야 합니다.

컨테이너의 이름은 항상 소문자여야 합니다. 컨테이너 이름에 대문자를 포함하거나 컨테이너 명명 규칙을 위반하는 경우에 400 오류(잘못된 요청) 메시지를 받을 수 있습니다.

## <a name="managing-security-for-blobs"></a>Blob 보안 관리

기본적으로 Azure Storage는 데이터 액세스를 계정 액세스 키를 보유한 계정 소유자로 제한하여 데이터를 보호합니다. 스토리지 계정의 Blob 데이터를 공유해야 할 경우 계정 액세스 키의 보안을 손상시키지 않고 공유하는 것이 중요합니다. 또한 Blob 데이터를 암호화하여 유선 및 Azure Storage에서 데이터가 안전하게 이동하게 할 수 있습니다.

### <a name="controlling-access-to-blob-data"></a>Blob 데이터에 대한 액세스 제어

기본적으로 스토리지 계정의 Blob 데이터는 스토리지 계정 소유자만 액세스할 수 있습니다. 기본적으로 Blob Storage에 대한 요청을 인증할 때는 계정 액세스 키가 필요합니다. 그러나 특정 blob 데이터를 다른 사용자가 사용할 수 있도록 설정할 수 있습니다.

### <a name="encrypting-blob-data"></a>Blob 데이터 암호화

Azure Storage은 클라이언트와 서버 모두에서 blob 데이터를 암호화 하는 것을 지원 합니다.

## <a name="next-steps"></a>다음 단계

이제 Blob Storage의 기본 사항을 배웠으므로 다음 링크를 따라 자세히 알아보세요.

### <a name="tools"></a>도구

- [ F# Azurestorag및 공급자](https://fsprojects.github.io/AzureStorageTypeProvider/)\
Blob F# , 테이블 및 큐 Azure Storage 자산을 탐색 하 고이에 대 한 CRUD 작업을 쉽게 적용 하는 데 사용할 수 있는 형식 공급자입니다.

- [Fsharp.core](https://github.com/fsprojects/FSharp.Azure.Storage)\
Microsoft Azure F# Table Storage 서비스를 사용 하는 API

- [Microsoft Azure Storage 탐색기 (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
Windows, OS X 및 Linux에서 Azure Storage 데이터로 시각적으로 작업할 수 있도록 해 주는 Microsoft의 독립 실행형 무료 앱입니다.

### <a name="blob-storage-reference"></a>Blob Storage 참조

- [.NET 용 Azure Storage Api](/dotnet/api/overview/azure/storage)
- [Azure Storage 서비스 REST API 참조](/rest/api/storageservices/)

### <a name="related-guides"></a>관련 가이드

- [.NET용 Azure Blob Storage 샘플](https://docs.microsoft.com/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/)
- [AzCopy 시작](/azure/storage/common/storage-use-azcopy-v10)
- [Azure Storage 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage 팀 블로그](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [빠른 시작: .NET을 사용 하 여 개체 저장소에 blob 만들기](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
