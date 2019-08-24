---
title: F#을 사용하여 Azure File 스토리지 시작
description: Azure File Storage를 사용하여 클라우드에 파일 데이터를 저장하고 Azure 가상 머신(VM) 또는 Windows를 실행하는 온-프레미스 애플리케이션에서 클라우드 파일 공유를 탑재합니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a0e3cab56ba0f3db27335822616b4976a5d9de62
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630500"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="9d76a-103">F #을 사용 하 여 Azure File storage 시작\#</span><span class="sxs-lookup"><span data-stu-id="9d76a-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="9d76a-104">Azure File storage는 표준 [SMB (서버 메시지 블록) 프로토콜](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)을 사용 하 여 클라우드에서 파일 공유를 제공 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="9d76a-105">SMB 2.1 및 SMB 3.0이 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="9d76a-106">Azure File Storage를 사용하여 파일 공유에 의존하는 레거시 애플리케이션을 비경제적인 다시 쓰기 작업 없이 빠르게 Azure로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="9d76a-107">Azure 가상 머신 또는 클라우드 서비스 또는 온-프레미스 클라이언트에서 실행 되는 응용 프로그램은 데스크톱 응용 프로그램이 일반적인 SMB 공유를 탑재 하는 것 처럼 클라우드에 파일 공유를 탑재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="9d76a-108">File Storage 공유를 동시에 탑재하고 액세스할 수 있는 애플리케이션 구성 요소 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="9d76a-109">파일 저장소에 대 한 개념적 개요는 [파일 저장소에 대 한 .net 가이드](/azure/storage/storage-dotnet-how-to-use-files)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d76a-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d76a-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9d76a-110">Prerequisites</span></span>

<span data-ttu-id="9d76a-111">이 가이드를 사용 하려면 먼저 [Azure storage 계정을 만들어야](/azure/storage/storage-create-storage-account)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="9d76a-112">이 계정에 대 한 저장소 액세스 키도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="9d76a-113">F# 스크립트 만들기 및 대화형 시작 F#</span><span class="sxs-lookup"><span data-stu-id="9d76a-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="9d76a-114">이 문서의 샘플은 F# 응용 프로그램 또는 F# 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="9d76a-115">F# 스크립트를 만들려면 `.fsx` F# 개발 환경에서 `files.fsx`확장명을 사용 하 여 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="9d76a-116">그런 다음 [Paket](https://fsprojects.github.io/Paket/) 또는 `WindowsAzure.Storage` [NuGet](https://www.nuget.org/) 과 같은 [패키지 관리자](package-management.md) 를 사용 하 여 `#r` 패키지를 설치 하 `WindowsAzure.Storage.dll` 고 지시어를 사용 하 여 스크립트에 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="9d76a-117">네임 스페이스 선언 추가</span><span class="sxs-lookup"><span data-stu-id="9d76a-117">Add namespace declarations</span></span>

<span data-ttu-id="9d76a-118">파일의 맨 `open` 위에 다음 문을 추가 합니다. `files.fsx`</span><span class="sxs-lookup"><span data-stu-id="9d76a-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="9d76a-119">연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="9d76a-119">Get your connection string</span></span>

<span data-ttu-id="9d76a-120">이 자습서에 대 한 Azure Storage 연결 문자열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="9d76a-121">연결 문자열에 대 한 자세한 내용은 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d76a-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="9d76a-122">자습서의 경우 다음과 같이 스크립트에 연결 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="9d76a-123">그러나 실제 프로젝트에는이 방법이 **권장 되지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="9d76a-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="9d76a-124">스토리지 계정 키는 스토리지 계정의 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="9d76a-125">항상 스토리지 계정 키를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="9d76a-126">다른 사용자에 게 배포 하거나 하드 코딩 하거나 다른 사용자가 액세스할 수 있는 일반 텍스트 파일로 저장 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="9d76a-127">손상 된 것으로 생각 되는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="9d76a-128">실제 응용 프로그램의 경우 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="9d76a-129">구성 파일에서 연결 문자열을 가져오려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="9d76a-130">Azure Configuration Manager 사용은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="9d76a-131">.NET Framework의 `ConfigurationManager` 형식과 같은 API를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="9d76a-132">연결 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="9d76a-132">Parse the connection string</span></span>

<span data-ttu-id="9d76a-133">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="9d76a-134">그러면이 반환 `CloudStorageAccount`됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="9d76a-135">파일 서비스 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="9d76a-135">Create the File service client</span></span>

<span data-ttu-id="9d76a-136">`CloudFileClient` 형식을 사용 하면 파일 저장소에 저장 된 파일을 프로그래밍 방식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="9d76a-137">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="9d76a-138">이제 데이터를 읽고 파일 저장소에 데이터를 쓰는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="9d76a-139">파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="9d76a-139">Create a file share</span></span>

<span data-ttu-id="9d76a-140">이 예제에서는 파일 공유를 만드는 방법을 보여 줍니다 (아직 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="9d76a-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="9d76a-141">루트 디렉터리 및 하위 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="9d76a-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="9d76a-142">여기서 루트 디렉터리를 가져오고 루트의 하위 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="9d76a-143">이미 존재 하지 않는 경우 둘 다 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="9d76a-144">파일로 텍스트 업로드</span><span class="sxs-lookup"><span data-stu-id="9d76a-144">Upload text as a file</span></span>

<span data-ttu-id="9d76a-145">이 예제에서는 텍스트를 파일로 업로드 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="9d76a-146">파일의 로컬 복사본에 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="9d76a-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="9d76a-147">여기서는 방금 만든 파일을 다운로드 하 여 콘텐츠를 로컬 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="9d76a-148">파일 공유의 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="9d76a-149">아래 예제에서는 공유의 현재 사용량을 확인 하는 방법과 공유에 대 한 할당량을 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="9d76a-150">`FetchAttributes`공유의 `Properties` `SetProperties` 를 채우고 로컬 변경 내용을 Azure File storage에 전파 하려면를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="9d76a-151">파일 또는 파일 공유에 대 한 공유 액세스 서명 생성</span><span class="sxs-lookup"><span data-stu-id="9d76a-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="9d76a-152">파일 공유 또는 개별 파일에 대 한 SAS (공유 액세스 서명)를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="9d76a-153">또한 공유 액세스 서명을 관리 하는 파일 공유에 대 한 공유 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="9d76a-154">공유 액세스 정책을 만드는 것은 SAS가 손상 되어야 하는 경우 SAS를 해지 하는 수단을 제공 하기 때문에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="9d76a-155">여기에서 공유에 대 한 공유 액세스 정책을 만든 다음 해당 정책을 사용 하 여 공유의 파일에 대 한 SAS 제약 조건을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="9d76a-156">공유 액세스 서명을 만들고 사용 하는 방법에 대 한 자세한 내용은 [sas (공유 액세스 서명) 사용](/azure/storage/storage-dotnet-shared-access-signature-part-1) 및 [Blob 저장소를 사용 하 여 sas 만들기 및 사용](/azure/storage/storage-dotnet-shared-access-signature-part-2)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d76a-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="9d76a-157">파일 복사</span><span class="sxs-lookup"><span data-stu-id="9d76a-157">Copy files</span></span>

<span data-ttu-id="9d76a-158">파일을 다른 파일이 나 blob 또는 파일에 blob으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="9d76a-159">Blob을 파일에 복사 하거나 파일을 blob에 복사 하는 경우 동일한 저장소 계정 내에서 복사 하는 경우에도 SAS (공유 액세스 서명)를 사용 하 여 원본 개체를 인증 *해야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="9d76a-160">다른 파일에 파일 복사</span><span class="sxs-lookup"><span data-stu-id="9d76a-160">Copy a file to another file</span></span>

<span data-ttu-id="9d76a-161">여기서는 동일한 공유의 다른 파일에 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="9d76a-162">이 복사 작업은 동일한 스토리지 계정의 파일 간에 복사를 수행하므로 공유 키 인증을 사용하여 복사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="9d76a-163">Blob에 파일 복사</span><span class="sxs-lookup"><span data-stu-id="9d76a-163">Copy a file to a blob</span></span>

<span data-ttu-id="9d76a-164">여기에서는 파일을 만들고 동일한 저장소 계정 내의 blob에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="9d76a-165">원본 파일에 대 한 SAS를 만듭니다 .이는 서비스에서 복사 작업을 수행 하는 동안 소스 파일에 대 한 액세스를 인증 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="9d76a-166">동일한 방식으로 blob을 파일에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="9d76a-167">원본 개체가 blob 인 경우 복사 작업 중에 해당 blob에 대 한 액세스를 인증 하는 SAS를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="9d76a-168">메트릭을 사용 하 여 파일 저장소 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9d76a-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="9d76a-169">Azure 스토리지 분석는 파일 저장소에 대 한 메트릭을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="9d76a-170">메트릭 데이터를 사용 하 여 요청을 추적 하 고 문제를 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="9d76a-171">[Azure Portal](https://portal.azure.com)에서 파일 저장소에 대 한 메트릭을 사용 하도록 설정 하거나, 다음과 F# 같이이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="9d76a-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9d76a-172">Next steps</span></span>

<span data-ttu-id="9d76a-173">Azure File storage에 대 한 자세한 내용은 다음 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d76a-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="9d76a-174">개념 문서 및 비디오</span><span class="sxs-lookup"><span data-stu-id="9d76a-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="9d76a-175">Azure Files 저장소: Windows 및 Linux 용 원활한 클라우드 SMB 파일 시스템</span><span class="sxs-lookup"><span data-stu-id="9d76a-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="9d76a-176">Linux에서 Azure File Storage를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="9d76a-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="9d76a-177">파일 저장소에 대 한 도구 지원</span><span class="sxs-lookup"><span data-stu-id="9d76a-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="9d76a-178">Azure Storage에서 Azure PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="9d76a-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="9d76a-179">Microsoft Azure Storage와 함께 AzCopy를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="9d76a-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="9d76a-180">Azure Storage에서 Azure CLI 사용</span><span class="sxs-lookup"><span data-stu-id="9d76a-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="9d76a-181">참조</span><span class="sxs-lookup"><span data-stu-id="9d76a-181">Reference</span></span>

- [<span data-ttu-id="9d76a-182">.NET 용 저장소 클라이언트 라이브러리 참조</span><span class="sxs-lookup"><span data-stu-id="9d76a-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="9d76a-183">파일 서비스 REST API 참조</span><span class="sxs-lookup"><span data-stu-id="9d76a-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="9d76a-184">블로그 게시물</span><span class="sxs-lookup"><span data-stu-id="9d76a-184">Blog posts</span></span>

- [<span data-ttu-id="9d76a-185">Azure File storage는 이제 일반 공급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d76a-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="9d76a-186">Azure File Storage 내</span><span class="sxs-lookup"><span data-stu-id="9d76a-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="9d76a-187">Microsoft Azure 파일 서비스 소개</span><span class="sxs-lookup"><span data-stu-id="9d76a-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="9d76a-188">Microsoft Azure 파일에 대 한 연결 유지</span><span class="sxs-lookup"><span data-stu-id="9d76a-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
