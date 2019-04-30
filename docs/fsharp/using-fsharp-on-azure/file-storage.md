---
title: 사용 하 여 Azure File storage 시작F#
description: Azure File storage 사용 하 여 클라우드에 파일 데이터를 저장 하 고 Azure 가상 머신 (VM)에서 클라우드 파일 공유를 탑재 또는 온-프레미스 응용 프로그램에서 Windows를 실행 합니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fa6dadc863bb9116cfac5afd7cd22a724bc7afe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031228"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>F를 사용 하 여 Azure File storage 시작\#

Azure File storage는 표준을 사용 하 여 클라우드에서 파일 공유를 제공 하는 서비스 [서버 메시지 블록 (SMB) 프로토콜](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)합니다. SMB 2.1과 SMB 3.0을 모두 지원 됩니다. Azure File storage를 사용 하 여 신속 하 고 비용이 많이 드는 재작성 없이 azure 파일 공유에 의존 하는 레거시 응용 프로그램을 마이그레이션할 수 있습니다. Azure virtual machines 또는 cloud services 또는 온-프레미스 클라이언트에서 실행 중인 응용 프로그램은 데스크톱 응용 프로그램이 일반적인 SMB 공유를 탑재 하는 것 처럼 클라우드에 파일 공유를 탑재할 수 있습니다. 응용 프로그램 구성 요소를 개수에 관계 없이 탑재 고 File storage 공유를 동시에 액세스할 수 있습니다.

File storage의 개념적인 개요를 참조 하세요 [file storage 용.NET 가이드](/azure/storage/storage-dotnet-how-to-use-files)합니다.

## <a name="prerequisites"></a>전제 조건

이 가이드를 사용 하려면 먼저 [Azure storage 계정 만들기](/azure/storage/storage-create-storage-account)합니다.
또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>만들기는 F# 스크립트 및 시작 F# 대화형

이 문서의 샘플에서 사용할 수는 F# 응용 프로그램 또는 F# 스크립트입니다. 만들려는 F# 스크립트를 사용 하 여 파일을 만듭니다는 `.fsx` 예를 들어 확장 `files.fsx`에서 F# 개발 환경입니다.

다음을 사용 하 여는 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 설치 하는 `WindowsAzure.Storage` 패키지 및 참조 `WindowsAzure.Storage.dll` 를사용하여스크립트에서`#r`지시문입니다.

### <a name="add-namespace-declarations"></a>네임 스페이스 선언을 추가합니다

다음을 추가 합니다 `open` 의 맨 위에 문을 `files.fsx` 파일:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서에 대 한 Azure Storage 연결 문자열을 해야 합니다. 연결 문자열에 대 한 자세한 내용은 참조 하세요. [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.

자습서의 경우 다음과 같은 스크립트에서 연결 문자열을 입력 있습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

그러나 이것이 **좋지** 실제 프로젝트입니다. 저장소 계정 키는 저장소 계정의 루트 암호와 비슷합니다. 항상 저장소 계정 키를 보호 해야 합니다. 다른 사용자에 하드 코딩 하거나 다른 사용자에 게 액세스할 수 있는 일반 텍스트 파일을 저장 하 게 배포 하지 마세요. 손상 되었다고 생각 하는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에서 됩니다. 구성 파일에서 연결 문자열을 가져올,이 수행할 수 있습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Azure 구성 관리자를 사용 하는 것은 선택 사항입니다. .NET Framework의 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 형식입니다.

### <a name="parse-the-connection-string"></a>연결 문자열을 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

이 반환 된 `CloudStorageAccount`합니다.

### <a name="create-the-file-service-client"></a>파일 서비스 클라이언트 만들기

`CloudFileClient` 형식을 사용 하면 프로그래밍 방식으로 File storage에 저장 된 파일을 사용할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

이제 데이터를 읽어 오고 File storage로 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-file-share"></a>파일 공유 만들기

이 예제에는 아직 존재 하지 않는 경우 파일 공유를 만드는 방법을 보여 줍니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>루트 디렉터리 및 하위 디렉터리 만들기

루트 디렉터리를 가져오려면 여기를 가져오고, 루트의 하위 디렉터리입니다. 아직 없는 경우 둘 다 만듭니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>텍스트 파일로 업로드

이 예제에서는 텍스트 파일로 업로드 하는 방법을 보여 줍니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>파일의 로컬 복사본에 파일을 다운로드 합니다.

여기서 파일을 다운로드 방금 만든 로컬 파일에 내용을 추가 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>파일 공유의 최대 크기를 설정 합니다.

아래 예제에서는 공유에 대 한 현재 사용량을 확인 하는 방법과 공유에 대 한 할당량을 설정 하는 방법을 보여 줍니다. `FetchAttributes` 공유를 채우는 데 호출 해야 합니다 `Properties`, 및 `SetProperties` Azure File storage에 로컬 변경 내용을 전파 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>파일 또는 파일 공유에 대 한 공유 액세스 서명 생성

개별 파일 또는 파일 공유에 대 한 공유 액세스 서명 (SAS)을 생성할 수 있습니다. 또한 공유 액세스 서명을 관리할 파일 공유에서 공유 액세스 정책을 만들 수 있습니다. 공유 액세스 정책을 만드는 것이 좋습니다, 손상 될 경우 SAS를 해지할 수 있습니다.

공유를 만들면 여기에서 액세스 정책 공유에 다음 정책을 사용 하는 공유에서 파일을 SAS에 대 한 제약 조건을 제공 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

공유 액세스 서명을 만들고 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [를 사용 하 여 공유 액세스 서명 (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) 하 고 [만들기 및 Blob storage 사용 하 여 SAS 사용 하 여](/azure/storage/storage-dotnet-shared-access-signature-part-2)입니다.

### <a name="copy-files"></a>파일 복사

파일에 파일을 다른 파일이 나 blob 또는 blob에 복사할 수 있습니다. Blob 파일 또는 blob에 파일을 복사 하는 경우 있습니다 *해야* 동일한 저장소 계정 내에서 복사 하는 경우에 원본 개체를 인증 하는 공유 액세스 서명 (SAS)을 사용 합니다.

### <a name="copy-a-file-to-another-file"></a>다른 파일에 파일을 복사 합니다.

여기에서 동일한 공유의 다른 파일로 파일을 복사 합니다. 이 복사 작업을 동일한 저장소 계정의 파일 간에 복사 되므로 복사를 수행 하려면 공유 키 인증을 사용할 수 있습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Blob에 파일을 복사 합니다.

파일을 만든 다음, 동일한 저장소 계정 내의 blob에 복사 합니다. 복사 작업 동안 원본 파일에 대 한 액세스를 인증 하는 서비스를 사용 하는 소스 파일에 대 한 SAS를 만들어야 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

동일한 방식으로 blob을 파일로 복사할 수 있습니다. 원본 개체가 blob 인 경우 복사 작업 중 해당 blob에 대 한 액세스를 인증에 SAS를 만듭니다.

## <a name="troubleshooting-file-storage-using-metrics"></a>메트릭을 사용 하 여 File storage 문제 해결

Azure Storage 분석에서는 File storage에 대 한 메트릭을 지원합니다. 메트릭 데이터를 사용 하 여 요청을 추적할 수 있으며 문제를 진단할 수 있습니다.

File storage에 대 한 메트릭을 설정할 수 있습니다.는 [Azure Portal](https://portal.azure.com), 또는 수행할 수 있습니다 F# 같이:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>다음 단계

Azure File storage에 대 한 자세한 내용은 다음이 링크를 참조 합니다.

### <a name="conceptual-articles-and-videos"></a>개념 문서 및 비디오

- [Azure File Storage: 원활한 클라우드 SMB 파일 시스템에 Windows 및 Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Linux를 사용 하 여 Azure File Storage를 사용 하는 방법](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>File storage 용 도구 지원

- [Azure PowerShell을 사용 하 여 Azure Storage를 사용 하 여](/azure/storage/storage-powershell-guide-full)
- [Microsoft Azure Storage를 사용 하 여 AzCopy를 사용 하는 방법](/azure/storage/storage-use-azcopy)
- [Azure CLI를 사용 하 여 Azure Storage를 사용 하 여](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>참조

- [.NET 용 storage 클라이언트 라이브러리](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [파일 서비스 REST API 참조](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>블로그 게시물

- [Azure File storage는 이제 일반 공급](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [내부 Azure File Storage](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Microsoft Azure 파일 서비스 소개](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Microsoft Azure Files에 대 한 연결 유지](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
